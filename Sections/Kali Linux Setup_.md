# Kali Linux Setup:



## Brave Installation
https://brave.com/en-in/linux/

```
sudo apt install apt-transport-https curl

sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg arch=amd64] https://brave-browser-apt-release.s3.brave.com/ stable main"|sudo tee /etc/apt/sources.list.d/brave-browser-release.list

sudo apt update

sudo apt install brave-browser
```

## Download Visual Studio

https://code.visualstudio.com/docs/?dv=linux64_deb

cd Downloads
$ dpkg -i install <filename.deb>

## Installing the Rust Tool Chain

To be able to use the tools written in Rust, we need to install rust and then use cargo to install the latest version of those tools.

1. https://rustup.rs/
2. Command: `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`

Choose 1 (Default Installation)

---------------------------------------------------
### After Installation is complete:

1. Add Cargo to the environment variable so that we can use it to install the Rust tools. Command:

`source $HOME/.cargo/env`

2. Install a fast Port Mapper that allows us to assess what ports are open on a host very quickly:
`$ cargo install rustscan`

3. Installing Directory Brutforce Tool:
`cargo install feroxbuster`

------------------------------------------------------------------------------------------
## Changing the Defalut Shell (echo $SHELL) to a more Friendly Shell

[Can Be Skipped]

mkdir -p ~/Downloads/Scripts && cd ~/Downloads/Scripts

Downloading the Git Repo of Powerline Fonts -- [One with built in capabilities to Render Special Characters within the Terminal]

`git clone https://github.com/powerline/fonts`

Install all powerline fonts into the system so that they are now usable:
cd fonts
./install.sh

To be used in a custom profile in Terminator

------------------------------
Now, we have already installed the fish shell but aren't using it, Can be verified using:

```
└─$ cat /etc/shells
# /etc/shells: valid login shells
/bin/sh
/bin/bash
/usr/bin/bash
/bin/rbash
/usr/bin/rbash
/bin/dash
/usr/bin/dash
/usr/bin/pwsh
/opt/microsoft/powershell/7/pwsh
/usr/bin/tmux
/usr/bin/screen
/bin/zsh
/usr/bin/zsh
/usr/bin/fish
```

We will be using a customizer called Oh-my-fish, to make the fish shell look even better!!

To get that started before we run the Fish shell:

curl -kL https://get.oh-my.fish | fish [Something like Plugin Manager for the Fish shell and allows a lot of customization]

-> Upon Completion, it brings us to the fish shell!! Exit from the Fish shell using the `exit` command

-> However, this command breaks the Zshell, so we need to fix it

-> Installing a them for the Fish shell:
`fish -c "omf install bobthefish"`

Close the Default Terminal and Open Terminator now!!!!!!!

Use the command below:

`echo "set -x PATH \$PATH $HOME/.cargo/bin" >> ~/.config/fish/config.fish`

-> Making sure that Fish shell also knows about the Cargo binaries that we just installed - so when we run the fish shell cargo is also available there to us.

### To change the default shell to Fish shell:

`chsh -s /usr/bin/fish`

To go back to the default shell, 
`chsh -s /bin/zsh`
