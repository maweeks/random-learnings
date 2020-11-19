# zsh

Automatic NVM version switch (have `.nvmrc` file in root of repo) ([tweaked from](https://medium.com/@kinduff/automatic-version-switch-for-nvm-ff9e00ae67f3))

```zsh
# place this at end of .zshrc after nvm initialization
parent-find() {
  local file="$1"
  local dir="$2"

  test -e "$dir/$file" && echo "$dir" && return 0
  [ '/' = "$dir" ] && return 1

  parent-find "$file" "$(dirname "$dir")"
}

autoload -U add-zsh-hook
load-nvmrc() {
  if [[ -f .nvmrc && -r .nvmrc ]]; then
    nvm use
  elif parent-find .nvmrc $(pwd); then
    nvm use
  elif [[ $(nvm version) != $(nvm version default)  ]]; then
    echo "Reverting to nvm default version"
    nvm use default
  fi
}
add-zsh-hook chpwd load-nvmrc
load-nvmrc
```
