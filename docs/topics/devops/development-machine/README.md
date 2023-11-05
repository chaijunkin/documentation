## Task install
Reference: https://taskfile.dev/installation/#binary
Install Script
We also have an install script which is very useful in scenarios like CI. Many thanks to GoDownloader for enabling the easy generation of this script.

By default, it installs on the ./bin directory relative to the working directory:

sh -c "$(curl --location https://taskfile.dev/install.sh)" -- -d

sudo mv bin/task /bin

## direnv install 
Reference: https://direnv.net/docs/installation.html

curl -sfL https://direnv.net/install.sh | bash

## python venv
task deps


## brew install
Refernce: https://brew.sh/

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
(echo; echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"') >> /home/linux/.zshrc
    eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
eval "$(direnv hook zsh)" >> /home/linux/.zshrc
task brew:deps