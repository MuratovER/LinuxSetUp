# LinuxSetUp
## Basic setup 
```
sudo apt-get update

sudo apt-get upgrade

sudo apt-get install -y neovim wget git curl make zsh 
```
## Upgrating python
### Changing Python from 3.8 to 3.10
```
sudo add-apt-repository ppa:deadsnakes/ppa

sudo apt update

apt list | grep python3.10

sudo apt install python3.10

sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.8 1

sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.10 2

sudo update-alternatives --config python3

sudo apt remove python3.8

sudo apt autoremove
```
### Fixing problms with disutils and pip
```
sudo apt install python3.10-distutils

curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py

python3.10 get-pip.py

sudo apt install python3.10-venv

sudo apt remove --purge python3-apt

sudo apt autoremove
```
## Installing Oh-My-Zsh
```
-$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
## Installing Poetry 
```
-$ curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python -
```
# Installing Docker 
```
sudo apt-get update
sudo apt-get upgrade 

sudo apt install docker.io

sudo systemctl start docker
sudo systemctl enable docker
sudo systemctl status docker
```
### Reboot your system
```
sudo docker run hello-world

sudo apt install docker-compose

docker-compose version
```
### Givin docker permission 
```
sudo groupadd docker
sudo gpasswd -a ${USER} docker
su - $USER
```
### Reboot your system
```
docker container ls
```
# Updating Neovim config
```
mkdir ~/.config/nvim
nvim ~/.config/nvim/init.vim
```
### copy this basic config
```
set mouse=a  " enable mouse
set encoding=utf-8
set number
set noswapfile
set scrolloff=7

set tabstop=4
set softtabstop=4
set shiftwidth=4
set expandtab
set autoindent
set fileformat=unix
filetype indent on      " load filetype-specific indent files

inoremap jk <esc>

call plug#begin('~/.vim/plugged')
Plug 'morhetz/gruvbox'  " colorscheme gruvbox
call plug#end()

colorscheme gruvbox

" turn off search highlight
nnoremap ,<space> :nohlsearch<CR>
```
## Installing vim-plug
```
sh -c 'curl -fLo "${XDG_DATA_HOME:-$HOME/.local/share}"/nvim/site/autoload/plug.vim --create-dirs \
       https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim'
```
## Updating pluggins with command in neovim :PlugInstall
