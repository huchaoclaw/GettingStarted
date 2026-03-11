# GettingStarted

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
echo 'eval "$(/usr/local/bin/brew shellenv zsh)"' >> ~/.zshrc
eval "$(/usr/local/bin/brew shellenv zsh)"
source ~/.zshrc
```

## Fast Node Manager

```bash
# https://github.com/Schniz/fnm
curl -fsSL https://fnm.vercel.app/install | bash

cat <<EOF >> ~/.zshrc
# FNM（Fast Node Manager）
eval "\$(fnm env --use-on-cd --shell zsh)"
EOF

fnm install 24.14.0 --lts
fnm use 24.14.0
fnm ls
fnm default 24.14.0
fnm uninstall 24.14.0

```

## pyenv

```bash
brew install pyenv

echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo '[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init - zsh)"' >> ~/.zshrc

# Install Python build dependencies
brew install openssl readline sqlite3 xz tcl-tk@8 libb2 zstd zlib pkgconfig

pyenv install -l
pyenv install 3.12.13

pyenv versions
pyenv version
pyenv global 3.12.13
```

## pyenv-virtualenv

```bash
brew install pyenv-virtualenv
echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.zshrc

pyenv virtualenv 3.12.13 <name>

pyenv activate <name>
pyenv deactivate

pyenv uninstall <name>
pyenv virtualenv-delete <name>
```