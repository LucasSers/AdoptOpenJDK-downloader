<h1 align="center">AdoptOpenJDK Downloader and Updater</h1>
<p align="center">
    <b>Allows you to install AdoptOpenJDK and automatically configure the environment variables.</b>
    <br />
    <b>Ability to update the JDK with each new release.</b>
    <br />
    <br />
    <a><img
            alt="badge"
            src="http://ForTheBadge.com/images/badges/built-with-love.svg"/>
    </a>
</p>


## Table of Contents 

-   [Installation ⚡](#installation-)
-   [Update 🚀](#update-)
-   [Features 📃](#features-)

The following instructions are for Windows (powershell). **An admin prompt is required.**

## Installation ⚡

1. Install chocolatey.

   ```powershell
   Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
   ```

2. Install main dependencies.

   ```powershell
   choco install 7zip.install curl git.install --params "/GitAndUnixToolsOnPath /NoGitLfs /SChannel /NoShellIntegration" -y; RefreshEnv;
   ```

3. Clone the repository and launch the installation script.

   ```powershell
   git clone https://github.com/LucasSers/AdoptOpenJDK-downloader.git "$HOME\Appdata\Local\AdoptOpenJDK"; cd "$HOME\Appdata\Local\AdoptOpenJDK"; Set-ExecutionPolicy -Scope CurrentUser Unrestricted; .\install.ps1; exit;
   ```


Use `java --version` to check for errors if any.

## Update 🚀

1. Pull changes.

    ```powershell
    cd "$HOME\Appdata\Local\AdoptOpenJDK"; git pull
    ```

2. Launch the update script:

    ```powershell
    Set-ExecutionPolicy -Scope CurrentUser Unrestricted; .\update.ps1; exit;
    ```

## Features 📃

-   Download the latest release.
-   Configures the environment variables.
-   Updates the file with a more recent version if there is one.
