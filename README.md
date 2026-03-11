# GettingStarted

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

## Fast Node Manager

```bash
# https://github.com/Schniz/fnm
curl -fsSL https://fnm.vercel.app/install | bash

cat <<EOF >> ~/.zshrc

# FNM（Fast Node Manager）
eval "\$(fnm env --use-on-cd --shell zsh)"
EOF

fnm install 24.14.0
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

echo 'export PATH="/usr/local/opt/tcl-tk@8/bin:$PATH"' >> ~/.zshrc
export LDFLAGS="-L/usr/local/opt/tcl-tk@8/lib"
export CPPFLAGS="-I/usr/local/opt/tcl-tk@8/include"
export PKG_CONFIG_PATH="/usr/local/opt/tcl-tk@8/lib/pkgconfig"

export LDFLAGS="-L/usr/local/opt/zlib/lib"
export CPPFLAGS="-I/usr/local/opt/zlib/include"
export PKG_CONFIG_PATH="/usr/local/opt/zlib/lib/pkgconfig"

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

## Claude Code

```bash
# https://code.claude.com/docs/zh-CN/quickstart
curl -fsSL https://claude.ai/install.sh | bash
brew install --cask claude-code
```