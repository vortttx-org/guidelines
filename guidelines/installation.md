# Installation

Git is a version control system that helps you track changes in your code and collaborate with others. This guide will walk you through installing Git on your machine, with instructions for Windows, Mac, and Linux.

### Quick Note!

Remember to verify if you already have Git installed on your machine before attempting an installation by typing this command in your terminal:

```bash
git --version
```

If Git is already installed, it will show the installed version.

## Windows

First of all, remember to verify if you already have Git installed on your machine:

**1. Download the Installer:**

- Go to [Git's](https://git-scm.com/) official website and click `Download for Windows`;
- The download should start automatically;

**2. Run the Installer:**

- Open the `.exe` file you downloaded and follow the installation instructions;
- During installation, it's recommended to leave the default settings unless you have specific preferences;

**3. Set Git Bash as the Default Terminal (_Optional_):**

- When prompted, choose `Git Bash` as your default terminal, which provides a more user-friendly environment for running Git commands;

**4. Verify the Installation:**

- Open `Git Bash` (or `Command Prompt / PowerShell`) and type:

```bash
git --version
```

If Git is installed correctly, it will show the installed version.

## Mac

**1. Use Homebrew (_Recommended_):**

- If you have `Homebrew` installed, the easiest way to install Git is to use this command in the terminal:

```bash
brew install git
```

**2. Install via Xcode Command Line Tools:**

- Open the terminal and type:

```bash
git --version
```

- If Git is not installed, you'll be prompted to install `Xcode Command Line Tools`. Follow the instructions to complete the installation;

**3. Verify the Installation:**

- After installation, verify if Git is working by typing:

```bash
git --version
```

If Git is installed correctly, it will show the installed version.

## Linux

**1. Open your terminal and update the package list:**

```bash
sudo apt update
sudo apt install git
```

If you're using other distribution that is not `Debian / Ubuntu`, run the correct command for that distribution to update the package list.

**2. Verify the Installation:**

- After installation, verify if Git is working by typing:

```bash
git --version
```

If Git is installed correctly, it will show the installed version.
