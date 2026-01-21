# Anaconda Python Installation Guide

This guide walks you through installing Anaconda Python on Windows, macOS, and Linux.

## What is Anaconda?

Anaconda is a popular Python distribution that includes Python, the conda package manager, and over 250 pre-installed scientific packages. It's widely used for data science, machine learning, and scientific computing.

---

## Windows Installation

### Requirements
- Windows 10 or newer (64-bit recommended)
- At least 5 GB of free disk space

### Installation Steps

1. **Download the installer**
   - Visit https://www.anaconda.com/download
   - Click the download button for Windows
   - The installer file will be named something like `Anaconda3-2024.xx-Windows-x86_64.exe`

2. **Run the installer**
   - Double-click the downloaded `.exe` file
   - Click "Next" to begin installation

3. **Accept the license agreement**
   - Read and accept the license terms
   - Click "I Agree"

4. **Choose installation type**
   - Select "Just Me (recommended)" unless you need system-wide installation
   - Click "Next"

5. **Select installation location**
   - Use the default location or choose a custom path
   - Avoid paths with spaces or special characters
   - Click "Next"

6. **Advanced options**
   - **Do not** check "Add Anaconda to my PATH environment variable" (not recommended by Anaconda)
   - Check "Register Anaconda as my default Python" (recommended)
   - Click "Install"

7. **Complete installation**
   - Wait for the installation to finish (this may take several minutes)
   - Click "Next" and then "Finish"

### Verify Installation

1. Open **Anaconda Prompt** from the Start Menu
2. Type `conda --version` and press Enter
3. You should see the conda version number (e.g., `conda 24.x.x`)

---

## macOS Installation

### Requirements
- macOS 10.13 or newer
- At least 5 GB of free disk space

### Installation Steps

1. **Download the installer**
   - Visit https://www.anaconda.com/download
   - Click the download button for macOS
   - Choose the appropriate version:
     - Apple Silicon (M1/M2/M3): ARM64 version
     - Intel processors: x86_64 version
   - The file will be named like `Anaconda3-2024.xx-MacOSX-arm64.pkg` or `Anaconda3-2024.xx-MacOSX-x86_64.pkg`

2. **Run the installer**
   - Double-click the downloaded `.pkg` file
   - Click "Continue" to start installation

3. **Follow the installation wizard**
   - Read the introduction and click "Continue"
   - Accept the license agreement
   - Select the destination disk (usually your main hard drive)
   - Click "Install"

4. **Enter your password**
   - You may need to enter your Mac password to authorize installation

5. **Complete installation**
   - Wait for installation to finish
   - Click "Close" when complete

### Initialize Conda (Important)

After installation, you need to initialize conda for your shell:

1. Open **Terminal** (Applications → Utilities → Terminal)
2. Run the initialization command:
   ```bash
   ~/anaconda3/bin/conda init zsh
   ```
   (Use `bash` instead of `zsh` if you're using bash shell)
3. Close and reopen Terminal

### Verify Installation

1. Open a new Terminal window
2. Type `conda --version` and press Enter
3. You should see the conda version number

---

## Linux Installation

### Requirements
- 64-bit Linux distribution
- At least 5 GB of free disk space
- bash or zsh shell

### Installation Steps

1. **Download the installer**
   - Visit https://www.anaconda.com/download
   - Click the download button for Linux
   - Choose the 64-bit (x86) installer
   - The file will be named like `Anaconda3-2024.xx-Linux-x86_64.sh`

2. **Open Terminal**
   - Navigate to your downloads directory:
     ```bash
     cd ~/Downloads
     ```

3. **Verify the installer (optional but recommended)**
   - Check the SHA-256 checksum:
     ```bash
     sha256sum Anaconda3-2024.xx-Linux-x86_64.sh
     ```
   - Compare with the hash on the Anaconda download page

4. **Run the installer**
   ```bash
   bash Anaconda3-2024.xx-Linux-x86_64.sh
   ```
   (Replace with your actual filename)

5. **Follow the prompts**
   - Press Enter to review the license agreement
   - Press Space to scroll through the license
   - Type `yes` to accept the license
   - Press Enter to confirm the installation location (or specify a custom path)
   - Wait for installation to complete

6. **Initialize Conda**
   - When asked "Do you wish to update your shell profile to automatically initialize conda?", type `yes`
   - This will modify your `~/.bashrc` or `~/.zshrc` file

7. **Activate the changes**
   - Close and reopen your terminal, or run:
     ```bash
     source ~/.bashrc
     ```
     (or `source ~/.zshrc` if using zsh)

### Verify Installation

1. Open a new terminal window
2. Type `conda --version` and press Enter
3. You should see the conda version number

---

## Post-Installation Steps (All Platforms)

### Update Conda

It's good practice to update conda after installation:

```bash
conda update conda
conda update anaconda
```

### Create Your First Environment

Conda environments help you manage different projects with different dependencies:

```bash
# Create a new environment named "myenv" with Python 3.11
conda create --name myenv python=3.11

# Activate the environment
conda activate myenv

# Deactivate when done
conda deactivate
```

### Install Additional Packages

```bash
# With conda
conda install numpy pandas matplotlib

# With pip (when packages aren't available via conda)
pip install some-package
```

### Launch Jupyter Notebook

Anaconda comes with Jupyter Notebook pre-installed:

```bash
jupyter notebook
```

This will open Jupyter in your default web browser.

---

## Common Issues and Solutions

### Windows: "conda" command not recognized

- Use **Anaconda Prompt** instead of Command Prompt or PowerShell
- Alternatively, you can manually add Anaconda to your PATH (not recommended)

### macOS: "conda: command not found"

- Make sure you ran the initialization command: `~/anaconda3/bin/conda init zsh`
- Close and reopen Terminal
- Check if conda is in your PATH: `echo $PATH | grep anaconda`

### Linux: Permission denied

- Make sure the installer script is executable: `chmod +x Anaconda3-*.sh`
- Run with bash explicitly: `bash Anaconda3-*.sh`

### All Platforms: Slow package installation

- Use the `-c conda-forge` channel for faster mirrors
- Consider using `mamba` as a faster alternative to conda: `conda install -c conda-forge mamba`

---

## Uninstalling Anaconda

### Windows
1. Go to Control Panel → Programs → Uninstall a program
2. Select Anaconda and click Uninstall
3. Delete the Anaconda installation folder (usually `C:\Users\YourName\anaconda3`)

### macOS
1. Open Terminal
2. Remove the anaconda3 directory:
   ```bash
   rm -rf ~/anaconda3
   ```
3. Remove conda initialization from your shell profile:
   ```bash
   conda init --reverse --all
   ```

### Linux
1. Remove the anaconda3 directory:
   ```bash
   rm -rf ~/anaconda3
   ```
2. Remove conda initialization from `~/.bashrc` or `~/.zshrc`
3. Remove hidden conda files:
   ```bash
   rm -rf ~/.conda
   ```

---

## Additional Resources

- Official Anaconda Documentation: https://docs.anaconda.com/
- Conda Cheat Sheet: https://docs.conda.io/projects/conda/en/latest/user-guide/cheatsheet.html
- Anaconda Package List: https://docs.anaconda.com/anaconda/packages/pkg-docs/

---

*Last updated: January 2025*
