# Use Ubuntu as the base image
FROM ubuntu:23.10

RUN apt-get update && apt-get install -y \
   wget \
   gnupg \
   git \
   apt-utils \
   lsb-release \ 
   software-properties-common 

RUN rm -rf /var/lib/apt/lists/*
RUN wget -qO- https://packages.lunarg.com/lunarg-signing-key-pub.asc | tee /etc/apt/trusted.gpg.d/lunarg.asc
RUN wget -qO /etc/apt/sources.list.d/lunarg-vulkan-1.3.275-jammy.list https://packages.lunarg.com/vulkan/1.3.275/lunarg-vulkan-1.3.275-jammy.list

#clang-17
RUN wget -qO - https://apt.llvm.org/llvm.sh | bash -s -- 17

RUN apt-get update
RUN apt-get install -y \
   python3 \
   pip \
   g++-13 \
   clang-17 \
   pkg-config \
   libwayland-dev \
   libxrandr-dev \
   libxinerama-dev \
   libxcursor-dev \
   libxi-dev \
   vulkan-sdk

RUN python3 -m pip install cmake==3.28.3 ninja==1.11.1 --break-system-packages 


WORKDIR /work

