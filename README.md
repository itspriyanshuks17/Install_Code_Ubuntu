# How to Install Visual Studio Code on Ubuntu

This guide provides a detailed, step-by-step process for installing Visual Studio Code (VS Code) on an Ubuntu system. The guide covers installation via the Microsoft repository as well as via Snap.

---

## Prerequisites

Before starting the installation, ensure that your Ubuntu system is up to date. Open a terminal and run the following command:

```bash
sudo apt update && sudo apt upgrade -y
```

This command updates the package lists for upgrades and installs the latest versions of all packages currently installed on your system.

## Method 1: Installing Visual Studio Code via the Microsoft Repository

### Step 1: Install Required Dependencies

To add the Microsoft repository, you need to install some essential packages first. These packages enable you to manage software repositories over HTTPS and handle additional software properties.

Run the following command to install these packages:

```bash
sudo apt install software-properties-common apt-transport-https wget -y
```

- `software-properties-common`: Provides an abstraction of the used apt repositories.
- `apt-transport-https`: Allows the use of HTTPS to retrieve files and packages.
- `wget`: A tool to download files from the web.

### Step 2: Import the Microsoft GPG Key

A GPG key is used to verify the authenticity of the packages provided by the repository. Import the Microsoft GPG key using the following command:

```bash
wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -
```

- `wget -q`: Downloads the key file quietly.
- `-O-`: Outputs the content to stdout.
- `sudo apt-key add -`: Adds the key to the list of trusted keys.

### Step 3: Enable the Visual Studio Code Repository

Next, you need to add the Visual Studio Code repository to your system’s sources list. This allows you to install and update VS Code directly from Microsoft.

Run the following command to add the repository:

```bash
sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"
```

- `deb [arch=amd64]`: Specifies the type of repository and architecture.
- `stable main`: Indicates the release channel (stable) and component (main) of the software.

### Step 4: Update the Package List

After adding the repository, update your package list again to include the newly added Visual Studio Code repository:

```bash
sudo apt update
```

### Step 5: Install Visual Studio Code

Finally, you can install Visual Studio Code by running the following command:

```bash
sudo apt install code -y
```

After installation, you can launch Visual Studio Code from your terminal by typing `code`, or find it in your application menu.

## Method 2: Installing Visual Studio Code via Snap

Snap is a package management system that simplifies the installation of software across different Linux distributions. If you prefer using Snap, follow these steps:

### Step 1: Install Snapd

If Snap isn't installed on your system, you'll need to install it first. Run the following command:

```bash
sudo apt install snapd -y
```

- `snapd`: The service that manages Snap packages.

### Step 2: Install Visual Studio Code via Snap

Once Snap is installed, you can easily install Visual Studio Code using the Snap store:

```bash
sudo snap install code --classic
```

- `--classic`: This flag allows VS Code to have full access to system resources, which is necessary for certain features.

After installation, you can start Visual Studio Code by typing `code` in your terminal or launching it from your application menu.

## Verification of Installation

After completing the installation through either method, you can verify that Visual Studio Code is installed by checking its version:

```bash
code --version
```

This command should output the version of Visual Studio Code that was installed.

---

## Conclusion

You have successfully installed Visual Studio Code on your Ubuntu system using either the Microsoft repository or Snap. You can now start using VS Code for your development needs.

If you encounter any issues during the installation, feel free to seek assistance or consult the official documentation at `https://code.visualstudio.com/docs/setup/linux`.

---
