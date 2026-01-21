# R and RStudio Installation Guide

This guide walks you through installing R and RStudio on Windows, macOS, and Linux.

## What are R and RStudio?

**R** is a programming language and environment for statistical computing and graphics. It's widely used for data analysis, statistical modeling, and visualization.

**RStudio** is an integrated development environment (IDE) for R that makes it easier to write R code, visualize data, and manage projects.

**Important:** You must install R first, then RStudio. RStudio requires R to be installed to function.

---

## Windows Installation

### Part 1: Installing R

#### Requirements
- Windows 10 or newer
- At least 500 MB of free disk space

#### Installation Steps

1. **Download R**
   - Visit https://cran.r-project.org/
   - Click "Download R for Windows"
   - Click "base"
   - Click the download link for the latest version (e.g., "Download R-4.x.x for Windows")

2. **Run the installer**
   - Double-click the downloaded `.exe` file (e.g., `R-4.x.x-win.exe`)
   - Click "Next" to begin installation

3. **Choose language**
   - Select your preferred language
   - Click "OK"

4. **Accept the license**
   - Read the GNU General Public License
   - Click "Next"

5. **Select installation location**
   - Use the default location (recommended): `C:\Program Files\R\R-4.x.x`
   - Click "Next"

6. **Select components**
   - Keep the default components selected (Core Files, 32-bit Files if applicable, 64-bit Files)
   - Click "Next"

7. **Startup options**
   - Choose "No (accept defaults)" for customized startup
   - Click "Next"

8. **Start Menu folder**
   - Accept the default folder name
   - Click "Next"

9. **Additional tasks**
   - Check the options you want:
     - Create a desktop shortcut (optional)
     - Save version number in registry (recommended)
   - Click "Next"

10. **Complete installation**
    - Wait for files to be copied
    - Click "Finish"

#### Verify R Installation

1. Open the Start Menu and search for "R"
2. Click on "R x64 4.x.x" (or similar)
3. The R console should open
4. Type `version` and press Enter to see R version information
5. Type `q()` to quit R

### Part 2: Installing RStudio

#### Installation Steps

1. **Download RStudio**
   - Visit https://posit.co/download/rstudio-desktop/
   - Scroll to "All Installers and Tarballs"
   - Download "RStudio-202x.xx.x-xxx.exe" for Windows 10/11

2. **Run the installer**
   - Double-click the downloaded `.exe` file
   - Click "Next"

3. **Choose installation location**
   - Accept the default location
   - Click "Next"

4. **Select Start Menu folder**
   - Accept the default
   - Click "Install"

5. **Complete installation**
   - Wait for installation to finish
   - Click "Finish"

#### Verify RStudio Installation

1. Open RStudio from the Start Menu
2. You should see the RStudio interface with four panes
3. In the Console pane (usually bottom-left), type `1 + 1` and press Enter
4. You should see `[1] 2` as output

---

## macOS Installation

### Part 1: Installing R

#### Requirements
- macOS 11 (Big Sur) or newer
- At least 500 MB of free disk space

#### Installation Steps

1. **Download R**
   - Visit https://cran.r-project.org/
   - Click "Download R for macOS"
   - Choose the appropriate version:
     - **Apple Silicon (M1/M2/M3)**: Download the "R-4.x.x-arm64.pkg"
     - **Intel Macs**: Download the "R-4.x.x-x86_64.pkg"

2. **Run the installer**
   - Double-click the downloaded `.pkg` file
   - Click "Continue"

3. **Follow the installation wizard**
   - Read the introduction and click "Continue"
   - Read the license and click "Continue", then "Agree"
   - Select the destination disk
   - Click "Install"

4. **Authenticate**
   - Enter your Mac password when prompted
   - Click "Install Software"

5. **Complete installation**
   - Wait for installation to finish
   - Click "Close"
   - You can move the installer to Trash if prompted

#### Verify R Installation

1. Open **Terminal** (Applications → Utilities → Terminal)
2. Type `R` and press Enter
3. The R console should start
4. Type `version` and press Enter to see version information
5. Type `q()` and then `n` to quit R

Alternatively:
1. Open **Finder**
2. Go to Applications
3. Double-click the "R" application
4. The R GUI should open

### Part 2: Installing RStudio

#### Installation Steps

1. **Download RStudio**
   - Visit https://posit.co/download/rstudio-desktop/
   - Scroll to "All Installers and Tarballs"
   - Download "RStudio-202x.xx.x-xxx.dmg" for macOS 12+

2. **Install RStudio**
   - Double-click the downloaded `.dmg` file
   - Drag the RStudio icon to the Applications folder
   - Eject the RStudio disk image

3. **Open RStudio**
   - Go to Applications
   - Double-click RStudio
   - If you see a security warning, click "Open"

#### Verify RStudio Installation

1. RStudio should open with its four-pane interface
2. In the Console pane, type `1 + 1` and press Enter
3. You should see `[1] 2` as output

---

## Linux Installation

### Part 1: Installing R

The installation method varies by Linux distribution. Below are instructions for the most common distributions.

#### Ubuntu / Debian

1. **Update package list**
   ```bash
   sudo apt update
   ```

2. **Install R**
   ```bash
   sudo apt install r-base r-base-dev
   ```

3. **Verify installation**
   ```bash
   R --version
   ```

#### For the latest R version on Ubuntu:

1. **Add CRAN repository**
   ```bash
   # Add the CRAN GPG key
   wget -qO- https://cloud.r-project.org/bin/linux/ubuntu/marutter_pubkey.asc | sudo gpg --dearmor -o /usr/share/keyrings/r-project.gpg
   
   # Add the R repository (replace 'jammy' with your Ubuntu version codename)
   echo "deb [signed-by=/usr/share/keyrings/r-project.gpg] https://cloud.r-project.org/bin/linux/ubuntu jammy-cran40/" | sudo tee /etc/apt/sources.list.d/r-project.list
   ```

2. **Update and install**
   ```bash
   sudo apt update
   sudo apt install r-base r-base-dev
   ```

#### Fedora / RHEL / CentOS

1. **Install R**
   ```bash
   sudo dnf install R
   ```
   
   Or for older versions:
   ```bash
   sudo yum install R
   ```

2. **Verify installation**
   ```bash
   R --version
   ```

#### Arch Linux

1. **Install R**
   ```bash
   sudo pacman -S r
   ```

2. **Verify installation**
   ```bash
   R --version
   ```

#### Test R Installation (All Linux Distributions)

1. **Start R**
   ```bash
   R
   ```

2. **Test in R console**
   - Type `version` and press Enter
   - Type `q()` and then `n` to quit

### Part 2: Installing RStudio

#### Ubuntu / Debian

1. **Download RStudio**
   - Visit https://posit.co/download/rstudio-desktop/
   - Scroll to "All Installers and Tarballs"
   - Download the appropriate `.deb` file for your Ubuntu/Debian version
   - Example: `rstudio-202x.xx.x-xxx-amd64.deb`

2. **Install dependencies** (if needed)
   ```bash
   sudo apt install libclang-dev libjpeg62
   ```

3. **Install RStudio**
   ```bash
   sudo dpkg -i rstudio-202x.xx.x-xxx-amd64.deb
   
   # If you encounter dependency errors, run:
   sudo apt-get install -f
   ```

4. **Launch RStudio**
   ```bash
   rstudio
   ```
   Or find it in your applications menu.

#### Fedora / RHEL / CentOS

1. **Download RStudio**
   - Visit https://posit.co/download/rstudio-desktop/
   - Download the `.rpm` file
   - Example: `rstudio-202x.xx.x-xxx-x86_64.rpm`

2. **Install RStudio**
   ```bash
   sudo dnf install rstudio-202x.xx.x-xxx-x86_64.rpm
   ```
   
   Or for older versions:
   ```bash
   sudo yum install rstudio-202x.xx.x-xxx-x86_64.rpm
   ```

3. **Launch RStudio**
   ```bash
   rstudio
   ```

#### Arch Linux

RStudio is available in the AUR (Arch User Repository).

1. **Using an AUR helper (e.g., yay)**
   ```bash
   yay -S rstudio-desktop
   ```

2. **Or manually**
   ```bash
   git clone https://aur.archlinux.org/rstudio-desktop.git
   cd rstudio-desktop
   makepkg -si
   ```

#### Verify RStudio Installation (All Linux)

1. Launch RStudio from your applications menu or terminal
2. The RStudio IDE should open
3. In the Console pane, type `1 + 1` and press Enter
4. You should see `[1] 2` as output

---

## Post-Installation Steps (All Platforms)

### Configure RStudio

When you first open RStudio, you might want to configure some settings:

1. **Tools → Global Options**
   - **Appearance**: Choose a theme (light or dark)
   - **Code**: Set up code style preferences
   - **R General**: Configure R session settings

### Install Essential Packages

R's power comes from its packages. Here are some commonly used packages:

```r
# Install the tidyverse (collection of data science packages)
install.packages("tidyverse")

# Install other popular packages
install.packages(c("ggplot2", "dplyr", "readr", "tidyr", "stringr"))

# For data manipulation
install.packages("data.table")

# For visualization
install.packages("plotly")

# For statistical modeling
install.packages("caret")

# For working with dates
install.packages("lubridate")
```

### Update R Packages

Keep your packages up to date:

```r
# Update all packages
update.packages(ask = FALSE)

# Check for outdated packages
old.packages()
```

### Set Up a Working Directory

It's good practice to organize your R projects:

```r
# Check current working directory
getwd()

# Set working directory
setwd("/path/to/your/project")

# Or better yet, use RStudio Projects:
# File → New Project → New Directory → New Project
```

### Learn R Basics

Try these commands in the R console:

```r
# Basic arithmetic
2 + 2
10 * 5
sqrt(16)

# Create variables
x <- 5
y <- 10
x + y

# Create a vector
numbers <- c(1, 2, 3, 4, 5)
mean(numbers)

# Get help
?mean
help(plot)

# View installed packages
installed.packages()

# Load a package
library(ggplot2)
```

---

## RStudio Interface Overview

When you open RStudio, you'll see four main panes:

1. **Source Pane** (top-left): Where you write and edit R scripts
2. **Console Pane** (bottom-left): Where R code is executed and output appears
3. **Environment/History Pane** (top-right): Shows variables, data, and command history
4. **Files/Plots/Packages/Help Pane** (bottom-right): File browser, plot viewer, package manager, and help documentation

### Useful RStudio Shortcuts

- **Ctrl/Cmd + Enter**: Run current line or selection
- **Ctrl/Cmd + Shift + C**: Comment/uncomment code
- **Ctrl/Cmd + S**: Save current file
- **Ctrl/Cmd + Shift + N**: New R script
- **Tab**: Auto-complete code
- **Ctrl/Cmd + L**: Clear console
- **Alt + -**: Insert assignment operator `<-`

---

## Common Issues and Solutions

### Windows: R or RStudio won't open

- Make sure you installed R before RStudio
- Right-click and "Run as Administrator"
- Check if antivirus is blocking the application

### macOS: "RStudio is damaged and can't be opened"

- This is a Gatekeeper security issue
- Go to System Settings → Privacy & Security
- Click "Open Anyway" next to the RStudio warning
- Or in Terminal: `xattr -d com.apple.quarantine /Applications/RStudio.app`

### Linux: Missing dependencies

- Install required libraries:
  ```bash
  # Ubuntu/Debian
  sudo apt install libssl-dev libcurl4-openssl-dev libxml2-dev
  
  # Fedora
  sudo dnf install openssl-devel libcurl-devel libxml2-devel
  ```

### All Platforms: Package installation fails

- Check your internet connection
- Try a different CRAN mirror:
  ```r
  chooseCRANmirror()
  ```
- Install packages with dependencies:
  ```r
  install.packages("package_name", dependencies = TRUE)
  ```

### All Platforms: "Cannot load package"

- Reinstall the package:
  ```r
  remove.packages("package_name")
  install.packages("package_name")
  ```

### Updating R (All Platforms)

When a new version of R is released, you'll need to reinstall it:

**Windows/macOS**: Download and install the new version (keeps old version by default)

**Linux**: Update through your package manager

After updating R, you may need to reinstall packages:

```r
# Get list of installed packages from old R version
old_packages <- installed.packages()[, "Package"]

# In new R version, reinstall them
install.packages(old_packages)
```

---

## Uninstalling R and RStudio

### Windows

1. **Uninstall RStudio**
   - Go to Control Panel → Programs → Uninstall a program
   - Select RStudio and click Uninstall

2. **Uninstall R**
   - In the same Programs list, select R and click Uninstall
   - Alternatively, delete the R folder: `C:\Program Files\R\`

3. **Remove user data** (optional)
   - Delete: `C:\Users\YourName\Documents\R`
   - Delete: `C:\Users\YourName\AppData\Local\RStudio`

### macOS

1. **Uninstall RStudio**
   ```bash
   sudo rm -rf /Applications/RStudio.app
   rm -rf ~/.rstudio
   ```

2. **Uninstall R**
   ```bash
   sudo rm -rf /Library/Frameworks/R.framework
   sudo rm -rf /Applications/R.app
   rm -rf ~/.R
   ```

### Linux

1. **Uninstall RStudio**
   ```bash
   # Ubuntu/Debian
   sudo apt remove rstudio
   
   # Fedora
   sudo dnf remove rstudio
   ```

2. **Uninstall R**
   ```bash
   # Ubuntu/Debian
   sudo apt remove r-base r-base-dev
   
   # Fedora
   sudo dnf remove R
   
   # Arch
   sudo pacman -R r
   ```

3. **Remove user data** (optional)
   ```bash
   rm -rf ~/.R
   rm -rf ~/.rstudio
   rm -rf ~/R
   ```

---

## Additional Resources

- **R Project Website**: https://www.r-project.org/
- **RStudio (Posit) Website**: https://posit.co/
- **CRAN**: https://cran.r-project.org/ (official R package repository)
- **R Documentation**: https://www.rdocumentation.org/
- **RStudio Cheat Sheets**: https://posit.co/resources/cheatsheets/
- **R for Data Science (free book)**: https://r4ds.had.co.nz/
- **Quick-R**: https://www.statmethods.net/
- **Stack Overflow R Tag**: https://stackoverflow.com/questions/tagged/r

---

## Next Steps

Now that you have R and RStudio installed, you can:

1. **Take an R tutorial**: Try the built-in tutorials or online courses
2. **Work through examples**: Practice with sample datasets like `mtcars`, `iris`, or `diamonds`
3. **Create your first project**: Use File → New Project in RStudio
4. **Learn data visualization**: Start with `ggplot2`
5. **Join the R community**: Participate in forums, attend meetups, or follow R blogs

---

*Last updated: January 2025*
