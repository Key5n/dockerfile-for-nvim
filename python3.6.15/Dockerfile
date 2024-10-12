FROM python:3.6.15

RUN wget https://github.com/neovim/neovim/releases/download/v0.9.5/nvim-linux64.tar.gz && \
  tar -zxvf nvim-linux64.tar.gz && \
  mv nvim-linux64/bin/nvim /usr/bin/nvim && \
  mv nvim-linux64/lib/nvim /usr/lib/nvim && \
  mv nvim-linux64/share/nvim/ /usr/share/nvim && \
  rm -rf nvim-linux64 && \
  rm nvim-linux64.tar.gz

RUN git clone https://github.com/Key5n/dotfiles-nix && \
  rm -rf ~/.config/ && \
  mkdir -p ~/.config/nvim && \
  mv dotfiles-nix/home/base/neovim/nvim ~/.config && \
  rm -rf dotfiles-nix

RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash - && \
  apt install -y nodejs && \
  npm -v && \
  npm install -g pyright
