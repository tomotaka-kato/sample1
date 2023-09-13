FROM rust:latest

WORKDIR /app


RUN apt-get update \
  && apt-get install -y sudo
# dockerユーザーだとcargo lambdaが権限無くて叩けない
# /tmp/.tmpxxxxの作成ができないっぽい

# ARG USERNAME=docker
# ARG USER_UID=1000
# ARG USER_GID=1000
#
# # Create the user
# RUN groupadd --gid $USER_GID $USERNAME \
#     && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
#     # [Optional] Add sudo support. Omit if you don't need to install software after connecting.
#     && apt-get update \
#     && apt-get install -y sudo \
#     && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
#     && chmod 0440 /etc/sudoers.d/$USERNAME
#
# USER $USERNAME

# install libraries
# RUN sudo apt install -y \
RUN apt install -y \
     curl \
     wget \
     file

# install packages
RUN cargo install --locked cargo-lambda
