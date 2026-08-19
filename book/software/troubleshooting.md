# Troubleshooting

This page collects fixes for the problems students most often hit while setting
up the course software. Work through the section that matches your symptom. If
none of these solve it, see [Getting Help](#troubleshooting-getting-help) at the bottom.

## Accessing Conda in Windows Terminal

The most common Windows problem is that `conda` works in the **Anaconda Prompt**
but not in Windows Terminal, PowerShell, or the VS Code terminal:

```text
'conda' is not recognized as an internal or external command,
operable program or batch file.
```

This means Conda was not added to your `PATH` during installation. You can add
it manually:

1. **Open the Start Menu** and search for "Environment Variables."
2. **Click on "Edit the system environment variables."**
3. In the System Properties window, click on **"Environment Variables."**
4. Under "System Variables," find the **`Path`** variable and select it.
5. Click **"Edit"** and then **"New."**
6. Add the following paths to the list:
   - `C:\Users\<YourUsername>\miniconda3\Scripts`
   - `C:\Users\<YourUsername>\miniconda3\condabin`
7. Click **"OK"** to close all windows.

![Editing the Path environment variable on Windows](https://github.com/user-attachments/assets/427ea290-8ea8-42a5-b070-854696f71fc5)

Replace `<YourUsername>` with your actual Windows username, and adjust the paths
if you installed Miniconda somewhere other than the default location. **Close
and reopen your terminal** afterward — a running terminal does not pick up a
changed `PATH`.

Verify the fix:

```bash
conda --version
```

## `conda activate` Does Not Work

If `conda` is found but `conda activate geo` fails with a message about running
`conda init`, your shell has not been configured for Conda. Run the one-time
initialization from the Anaconda Prompt (Windows) or your terminal (macOS and
Linux):

```bash
conda init --all
```

On Windows you may need to target `cmd.exe` and PowerShell explicitly:

```bash
conda init cmd.exe
conda init powershell
```

Then close and reopen the terminal. If PowerShell now refuses to load the Conda
profile with a script-execution error, allow local scripts to run:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

## The `geo` Environment Is Missing from VS Code or Jupyter

If your environment does not appear in the VS Code interpreter picker or the
Jupyter kernel list, first confirm it actually exists:

```bash
conda env list
```

If it is listed, the tool simply has not detected it yet:

- **VS Code.** Open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`), run
  **Python: Select Interpreter**, and choose the `geo` environment. If it is not
  offered, run **Developer: Reload Window** and try again.
- **JupyterLab.** Install a kernel for the environment, then restart JupyterLab:

  ```bash
  conda activate geo
  conda install -c conda-forge ipykernel
  python -m ipykernel install --user --name geo --display-name "Python (geo)"
  ```

Always launch JupyterLab from inside the activated environment, not from `base`.

## Package Installation Is Slow or Fails to Solve

If `conda install` sits at "Solving environment" for a long time, or ends with a
conflict, use Mamba instead — it resolves the same environments far faster:

```bash
conda install -n base mamba -c conda-forge
mamba install -c conda-forge pygis
```

Two habits prevent most solver conflicts:

- **Use `conda-forge` consistently.** Mixing channels is the usual cause of
  unsolvable environments. Install geospatial packages with
  `-c conda-forge` every time.
- **Install packages together, not one at a time.** Passing all packages in a
  single command lets the solver find a combination that works.

If an environment is badly broken, it is usually faster to rebuild it than to
repair it:

```bash
conda remove -n geo --all
conda create -n geo python=3.12
conda activate geo
mamba install -c conda-forge pygis
```

## `ModuleNotFoundError` for a Package You Installed

This almost always means you installed the package into one environment and are
running Python from another. Check which Python is actually running:

```bash
conda activate geo
python -c "import sys; print(sys.executable)"
```

The path printed should be inside your `geo` environment. If it is not, the
environment is not active, or your editor is pointed at a different interpreter.
In a notebook, run the same check in a cell and confirm the selected kernel is
`Python (geo)`.

## Git Asks for a Password on Every Push

GitHub no longer accepts account passwords over HTTPS. Either authenticate with
the GitHub CLI:

```bash
gh auth login
```

or switch the remote to SSH after adding an SSH key to your GitHub account:

```bash
git remote set-url origin git@github.com:<username>/<repository>.git
```

(troubleshooting-getting-help)=
## Getting Help

When something still does not work, post in the course discussion or bring it to
office hours. Include:

- Your operating system and version
- The exact command you ran
- The **complete** error message, copied as text rather than a screenshot
- The output of `conda info` and `conda env list`

Most setup problems are quick to diagnose with that information and slow to
diagnose without it.
