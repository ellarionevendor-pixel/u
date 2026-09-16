# Path to your Oh My Zsh installation
export ZSH="$HOME/.oh-my-zsh"

# Theme Selection
ZSH_THEME="sunrise"

# Popular Plugins Configuration
plugins=(
  git
  archlinux
  sudo
  zsh-autosuggestions
  zsh-syntax-highlighting
  alias-tips
  auto-notify
  colored-man-pages
  extract
  command-not-found
)

source $ZSH/oh-my-zsh.sh

# History Configuration
HISTFILE=~/.zsh_history
HISTSIZE=10000
SAVEHIST=10000
setopt SHARE_HISTORY          # Share history across terminal sessions
setopt HIST_IGNORE_ALL_DUPS   # Delete old duplicate entries when new ones are added
setopt HIST_IGNORE_SPACE      # Don't record commands starting with a space

# Plugin Settings
AUTO_NOTIFY_THRESHOLD=10      # Send desktop notification for commands taking longer than 10s
ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE='fg=8' # Dim grey text for autosuggestions

