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
## Changing the Defalut Shell (echo $SHELL) to a more Friendly Tool
