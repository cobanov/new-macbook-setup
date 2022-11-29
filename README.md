# New Macbook Setup

## Install XCode
```
sudo xcode-select --install
```
## Install Brew.
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
## Brew Services
```
brew install tree wget vim fig git htop imagemagick ffmpeg tmux
```
```
brew install --cask iterm2 visual-studio-code
```

## Install ZSH Plugins. 

```
sudo apt install zsh

# Optional: you can use fig extensions also. (I think they're better btw)
sudo apt install zsh-autosuggestions zsh-syntax-highlighting
```

## Install Oh my ZSH.
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## iTerm2 Settings
> Preferences > Profiles > Keys > Presets > Natural Text Editing

## Install Python Dev Environment
Install Anaconda
```
curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh
sh Miniconda3-latest-MacOSX-arm64.sh
```
Initialize on Terminal if needed
```
conda init
source ~/.zshrc
```
Install popular libraries
```
python -m pip install --upgrade pip
pip install pandas numpy matplotlib seaborn scikit-learn requests
```


## PyTorch Env
Create environment for PyTorch
```
conda create --name torchenv python=3.9
activate torchenv
```

Install Dependencies
```
brew install gcc

conda install astunparse numpy ninja pyyaml setuptools cmake cffi typing_extensions future six requests dataclasses
conda install pkg-config libuv
```

MPS acceleration is available on MacOS 12.3+
```
conda install pytorch torchvision torchaudio -c pytorch-nightly
```
if you get error
```
conda install pytorch -c pytorch-nightly
pip install --pre torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/nightly/cpu
```
Check if everyting is okay
```python
python
import torch; torch.backends.mps.is_available()
# True
```
