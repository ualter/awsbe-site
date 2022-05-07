<div id="top"></div>

## :cloud: **AwsBe**

A tool to help handle **AWS Session** connections on terminals, using your configured AWS Shared Config and Credentials files. It manages **Roles to Assume**, **MFA Token** requests, **AWS SSO Sign-in**, **AWS SSO Tokens** and the **expiration** of opened sessions.

![AwsBe](./docs/img/gif_04.gif)
*Click on image to see it larger*

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#pushpin-getting-started">Getting Started</a>
      <ul>
        <li><a href="#hammer-prerequisites">Prerequisites</a></li>
        <li>
          <a href="#floppy_disk-installation">Installation</a>
          <ul>
            <li><a href="#computer-linux">Linux</a></li>
            <li><a href="#computer-windows">Windows</a></li>
          </ul>
        </li>
      </ul>
    </li>
    <li><a href="#running-usage">Usage</a></li>
    <li><a href="#pencil2-autocompletion-script"> Autocompletion Script</a>
    <li><a href="#mailbox-contact">Contact</a></li>
    <li><a href="#construction-working-in-progress">WIP</a>
      <ul>
        <li><a href="#changelog">ChangeLog</a></li>
      </ul>
    </li>
  </ol>
</details>

---

## :pushpin: **Getting Started**

### :hammer: **Prerequisites**
- AWS Shared Config and Credentials files
  - The awsbe use the AWS Shared Config and Credentials files to handle the AWS Sessions. For this tool to work properly (and to take full advantage of it), you must have all the information well configured on the ```credentials``` and ```config``` [files](https://docs.aws.amazon.com/sdkref/latest/guide/file-format.html) (like: Profiles, Source Profiles, Region, MFA Serial, Sso_Start_URL, Sso_Role_Name, etc.), for all details check their documentation [here](https://docs.aws.amazon.com/sdkref/latest/guide/creds-config-files.html).
<p align="right">(<a href="#top">back to top</a>)</p>

### :floppy_disk: **Installation**

:cd: Download:
- https://github.com/ualter/awsbe-site/releases
  - [awsbe-v0.3.8-linuxAmd64.tar.gz](https://github.com/ualter/awsbe-site/releases/download/v0.3.8/awsbe-v0.3.8-linuxAmd64.tar.gz)
  - [awsbe-v0.3.8-windowsAmd64.tar.gz](https://github.com/ualter/awsbe-site/releases/download/v0.3.8/awsbe-v0.3.8-windowsAmd64.tar.gz)
  - [awsbe-v0.3.8-darwinAmd64.tar.gz](https://github.com/ualter/awsbe-site/releases/download/v0.3.8/awsbe-v0.3.8-darwinAmd64.tar.gz)

#### :computer: **LINUX** and **MAC**
```bash
tar -xvf awsbe-${VERSION}-linuxAmd64.tar.gz 
# Use the provided script
sh install.sh # Notice! The script must have permission to move files to folder /usr/local/bin

### OR

# DIY...
tar -xvf awsbe-${VERSION}-linuxAmd64.tar.gz
chmod +x awsbe
mv awsbe /usr/local/bin/
mv awsbebin-${VERSION} /usr/local/bin/
echo "alias awsbe='source awsbe'" >> ~/.bashrc
echo "alias awsbe='source awsbe'" >> ~/.zshrc
alias awsbe='source awsbe'  # To work properly in the opened terminal already

# IMPORTANT! 
# In any of installation method, make it sure that in your ~/.bashrc (or ~/.zshrc) file
# you have an alias for awsbe properly configured. This line must be there:
alias awsbe='source awsbe'

```

#### :computer: **WINDOWS**
```bash
# Unpack the tar file and put the two files in your PATH Environment Variable
# They must be kept together, in the same folder
awsbe.bat
awsbebin-${VERSION}.exe
# Always call awsbe to work properly, not the .exe directly
```
<p align="right">(<a href="#top">back to top</a>)</p>

## :running: **Usage**
```bash
# Execute without parameters to open an User Interface to manage your AWS Sessions:
awsbe

# Execute passing as a parameter the AWS Profile to be started
# The terminal will be configured directly without open the AwsBe User Interface
# awsbe [PROFILE-NAME]
awsbe dev
awsbe prod

# To show the current AWS Session opened in terminal 
awsbe -s

# List all my profiles
awsbe -l

# To see all available options:
awsbe -h
```
<p align="right">(<a href="#top">back to top</a>)</p>

## :pencil2: **Auto*completion* Script**
Generate the autocompletion script for awsbe for the specified shell.
```bash
### BASH
source <(awsbe completion bash)
## Linux:
awsbe completion bash > /etc/bash_completion.d/awsbe
## macOS:
awsbe completion bash > /usr/local/etc/bash_completion.d/awsbe


### ZSH
echo "autoload -U compinit; compinit" >> ~/.zshrc
awsbe completion zsh > "${fpath[1]}/_awsbe"
# You will need to start a new shell for this setup to take effect.

```
<p align="right">(<a href="#top">back to top</a>)</p>

## :mailbox: **Contact**
**[Ualter Otoni](https://github.com/ualter)**
<p align="right">(<a href="#top">back to top</a>)</p>


## :construction: **Working in progress...**

:construction_worker: Having some fun in my spare time...  this is the real goal here :stuck_out_tongue_winking_eye:
- Tested so far...
  - :heavy_check_mark: [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701#activetab=pivot:overviewtab) :fast_forward: WSL2 Ubuntu
  - :heavy_check_mark: [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701#activetab=pivot:overviewtab) :fast_forward: Command Prompt
  - :heavy_check_mark: [WSL2](https://docs.microsoft.com/en-us/windows/wsl/about) Ubuntu *(works with no unicode characters support)*
  - :heavy_check_mark: Windows Command Prompt *(works with no unicode characters support)*
  - :heavy_check_mark: EC2 Amazon Linux

### [**ChangeLog**](./CHANGELOG.md)
<p align="right">(<a href="#top">back to top</a>)</p>
