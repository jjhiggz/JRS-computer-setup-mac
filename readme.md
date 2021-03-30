# Computer Setup ( Mac )
[Watch Some Videos To Walk You Through](https://youtu.be/IgQbOZ1i6yM)

Welcome student! Before we embark, let's turn your computer from a software _consumer_ computer to a software _developer_ computer. Follow each of these instructions _in order_. If something doesn't work, *stop* and try the step again. If it's still not working, ask an instructor for help before you move on!

Note: When you copy/paste a command from this page to your terminal, you *may need to hit enter after everything looks like its run!*. You might still have commands that need to run!

## Set up your text editor

You'll spend most of your time in the program in your text editor. If you already have a preference, keep using it! Switching text editors, even with the same file, is not a big deal. If you're looking for a suggestion, VS Code is a good place to start.

### Download from Link

Download and install [VS Code](https://code.visualstudio.com/)

## Setup your terminal

Your terminal (which sometimes you'll hear referred to as a "shell" or "the command line" or a "CLI") will be your primary means of interacting with your computer in the program. This will take the place of navigating through file folders, downloading installers, and running programs by clicking on icons.

Fortunately, you're on a Mac which is a Unix-Based operating system. This means that you will not have to install much to get your CLI working. We will however want to add some cool features to it which we will do in a bit!


## Installing Homebrew
Before we can do anything we need a package manager for your computer. Run the following command to get xcode developer tools installed. 
First we need to accept the XCode Licence by running the following command
```sh
sudo xcodebuild -license
```
If this command doesn't run, then head to the app store and download X-Code.

```sh
xcode-select --install ; /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

If this worked you should be able to run the following command without running into errors. Something like `/usr/local/bin/brew` should print to your screen

```sh
which brew
```

## Installing Some Packages

Now that you have Brew on your computer we can use Brew to install some packages. First lets install git by running the following command.

```sh
brew install git
```

We can actually install multiple packages at the same time by providing multiple space-separated words after install. Run the following command to also install zsh, gmp, gnupg, sqlite, postgres.

```sh
brew install zsh gmp gnupg sqlite postgres
```
## Set up zsh

Run:

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

When it asks you if you want to switch your shell over to zsh, type "y" and hit enter.

Then *close all open instances of your terminal*. When you reopen your terminal, your command prompt should have a colored `~` on it.

## Install `nvm` and Node

nvm or "Node Version Manager" is a package that we install on our computers that allows us to select between different versions of node. Although you won't really need to understand what is going on here right now. If you are ever curious that is it's purpose.

Because nvm is not a package that `apt` knows about we have to do a bit more complex of an install is necessary. We use a command called `curl` to hit a specific website with specific information. We are going to make a request to "https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh" which is a website that contains all of the information for this package.

To install nvm, run the following command in your terminal:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | zsh
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```

Hit enter when you're done!

If this worked, the following command should print `nvm`:

```bash
command -v nvm
```

If that worked, run the following command in your terminal:

```bash
nvm install node
nvm use node
nvm alias default node
```

Hit enter when you're done!

## Install Node Packages

Another package manager? Yep! Gem is for installing packages written in Ruby, and npm is is for installing packages written in JavaScript.

Run the following command in your terminal:

```bash
npm install -g yarn lite-server create-react-app
```

If running:

```bash
which lite-server
```

prints something to the screen, you're probably in good shape!

### Set Up Plugins

Go to the extension store and download the following plugins

- WSL (Made by Microsoft)
- Better Comments
- Wakatime
- Indent Rainbow

### Restart Your UBUNTU TERMINAL and EXIT VSCODE

After restarting, open up Ubuntu, and type in:

```
code .
```

this should open up visual studio, but using your linux OS Instead of windows

If you can't get this step working, PLEASE REACH OUT TO AN INSTRUCTOR

## Set up NVM and Node to work every time

You may have a problem with nvm when you restart your ubuntu terminal. If you do open up your zsh configuration file using the following command:


```zsh
code ~/.zshrc
```

* Scroll down to the bottom of the file.
* **Paste** *all 3* of these lines at the bottom of the file:

```zsh
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```
## Set up your github account
<!-- ! Insert Video Link Here -->


## Set up git
<!-- ! Insert Video Here -->

Run these commands, **swapping** you `you@example.com` and `Your Name` for **your actual email and name**.

```bash
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

Follow [these steps](https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh) to connect your computer to Github:

1. Check if you have an SSH key for your computer: [how to check for ssh key](https://docs.github.com/en/github/authenticating-to-github/checking-for-existing-ssh-keys)
2. **If you do not** add one by following *all* of these steps: [How to add an SSH Key](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)


### Congratulations

Yay! You're done!! 🙌 💃
Take a break, get a drink of water, and happy coding!!
