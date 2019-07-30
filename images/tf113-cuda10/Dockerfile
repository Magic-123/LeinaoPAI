FROM tensorflow/tensorflow:1.13.0rc1-gpu-py3
USER root
RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak \
    && echo deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial main restricted universe multiverse > /etc/apt/sources.list \
    && echo deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-updates main restricted universe multiverse >> /etc/apt/sources.list \
    && echo deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-backports main restricted universe multiverse >> /etc/apt/sources.list \
    && echo deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-security main restricted universe multiverse >> /etc/apt/sources.list \
    && apt update
RUN buildDeps='gcc libsm6 libxext6 vim tmux screen' \
    && apt-get install -y $buildDeps --fix-missing

USER root
RUN pythonPkg='numpy opencv-python lmdb tensorboardX tqdm' \
    && pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple \
    && pip install $pythonPkg
