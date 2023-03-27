FROM alpine:3.17

#install necessary packages
RUN apk add fish git neovim make g++ wget

#setup neovim config
WORKDIR /root/.config
RUN git clone https://github.com/moshiur-bd/nvim.git
WORKDIR ./nvim
RUN git checkout m1-linux-cpp

#setup clangd - custom compiled binary for m1 mac.
WORKDIR /usr/bin
RUN wget https://github.com/moshiur-bd/clangd-binary-for-alpine-linux-m1-chip/raw/master/clangd
RUN chmod +x clangd

#setup cpp repo
WORKDIR /root/repos
RUN git clone https://github.com/moshiur-bd/contest-submissions-cpp.git

#enable custom cpp compile config for clangd to properly understand headers
WORKDIR contest-submissions-cpp
RUN mv compile_flags.txt.disabled compile_flags.txt

#default work directory
WORKDIR /root/repos
RUN echo "setup complete!"
