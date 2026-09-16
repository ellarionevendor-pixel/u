sudo pacman -Sy --needed zsh curl git zsh-completions && \
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" "" --unattended && \
chsh -s "$(which zsh)" "$USER" && \
ZSH_CUSTOM="${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}" && \
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM}/plugins/zsh-autosuggestions && \
git clone https://github.com/zsh-users/zsh-syntax-highlighting ${ZSH_CUSTOM}/plugins/zsh-syntax-highlighting && \
git clone https://github.com/djui/alias-tips ${ZSH_CUSTOM}/plugins/alias-tips && \
git clone https://github.com/MichaelAquilina/zsh-auto-notify ${ZSH_CUSTOM}/plugins/auto-notify && \
cat << 'EOF' > ~/.zshrc
export ZSH="$HOME/.oh-my-zsh"
ZSH_THEME="sunrise"

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

# Quality of Life Tweaks
HISTSIZE=10000
SAVEHIST=10000
setopt SHARE_HISTORY
setopt HIST_IGNORE_ALL_DUPS
EOF
exec zsh
