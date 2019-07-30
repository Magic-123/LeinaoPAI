# ==================================================================
# lcb-py36-cuda90
# maintrainer: Chuanbin Liu (774054270@qq.com)
# ------------------------------------------------------------------
# python        3.6    (apt)
# tensorflow    1.9.0  (pip)
# tensor2tensor 1.10.0 (pip)
# pytorch       0.4.1  (pip)
# ==================================================================

FROM 10.11.3.8:5000/nvidia/cuda:9.0-cudnn7-devel-ubuntu16.04
#FROM nvidia/cuda:9.0-cudnn7-devel-ubuntu16.04

ENV LD_LIBRARY_PATH=/usr/local/cuda/lib64:/lib/x86_64-linux-gnu:/usr/lib/x86_64-linux-gnu:$LD_LIBRARY_PATH PATH=/usr/local/cuda-9.0/bin:$PATH
ENV LC_ALL=C


RUN sed -i 's/archive.ubuntu.com/mirrors.ustc.edu.cn/g' /etc/apt/sources.list && \
    APT_INSTALL="apt-get install -y --no-install-recommends" && \
    PIP_INSTALL="python -m pip --no-cache-dir install --upgrade -i https://pypi.tuna.tsinghua.edu.cn/simple " && \
    rm -rf /var/lib/apt/lists/* \
           /etc/apt/sources.list.d/cuda.list \
           /etc/apt/sources.list.d/nvidia-ml.list && \
	apt-get update && apt-get install -y --no-install-recommends \
		build-essential \
		cmake \
		git \
		wget \
		libatlas-base-dev \
		libboost-all-dev \
		libgflags-dev \
		libgoogle-glog-dev \
		libhdf5-serial-dev \
		libleveldb-dev \
		liblmdb-dev \
		libopencv-dev \
		libprotobuf-dev \
		libsnappy-dev \
		protobuf-compiler \
		python-dev \
		python-numpy \
		python-pip \
		python-setuptools \
		python-scipy \
		nano \
		libopenblas-dev \
		liblapack-dev \
		python-tk \
		openssh-client \
		openssh-server \
        autossh \
        expect && \
	apt-get install --no-install-recommends libboost-all-dev && \
	apt-get install libopenblas-dev \
		liblapack-dev \
		libatlas-base-dev \
		libgflags-dev \
		libgoogle-glog-dev \
		liblmdb-dev \
		gfortran && \
	apt-get install -y build-essential git \
		libprotobuf-dev \
		libleveldb-dev \
		libsnappy-dev \
		libopencv-dev \
		libboost-all-dev \
		libhdf5-serial-dev \
		libgflags-dev \
		libgoogle-glog-dev \
		liblmdb-dev \
		protobuf-compiler \
		protobuf-c-compiler \
		libyaml-dev \
		libffi-dev \
		libssl-dev \
		python-dev \
		python-pip \
		python3-pip \
		python3-tk \
		python-tk \
		liblmdb-dev \
		time \
		vim \
		screen \
		tmux && \
    DEBIAN_FRONTEND=noninteractive $APT_INSTALL \
        software-properties-common \
        && \
    add-apt-repository ppa:jonathonf/python-3.6 && \
    apt-get update && \
    DEBIAN_FRONTEND=noninteractive $APT_INSTALL \
        python3.6 \
        python3.6-dev \
        && \
    wget -O ~/get-pip.py \
        https://bootstrap.pypa.io/get-pip.py && \
    python3.6 ~/get-pip.py && \
    ln -s /usr/bin/python3.6 /usr/local/bin/python3 && \
    ln -s /usr/bin/python3.6 /usr/local/bin/python && \
    $PIP_INSTALL \
        pip \
        && \
    $PIP_INSTALL \
        setuptools

RUN	mkdir ~/.pip && echo "[global]" > ~/.pip/pip.conf && \
	echo "index-url=https://pypi.tuna.tsinghua.edu.cn/simple" >> ~/.pip/pip.conf && \
	echo "format = columns" >> ~/.pip/pip.conf

Run	pip install numpy \
		leveldb \
		h5py \
		tqdm \
		fire \
		cffi \
		cython \
		ipython \
		SimpleITK \
		pydicom \
		lmdb \
		Cython \
		imageio \
		easydict \
		pandas \
		medicaltorch \
		jupyter \
		scikit-learn \
		scikit-image \
		scikit-video \
		python-gflags \
		networkx \
		pyyaml \
		pillow \
		visdom \
		protobuf \
		wheel \
		nose \
		Pillow \
		six \
		sklearn \
		imageio \
		packaging \
		urllib3 \
		numba==0.41.0 \
		seaborn==0.9.0 \
		hypertools==0.5.1 \
		fasteners \
		fjcommon==0.1.69 \
		decorator==4.3.0 \
		dominate requests \
		cffi \
		dlib \
		datetime \
		scipy \
		matplotlib \
		virtualenv \
		ipdb \
		opencv-python \
		pretrainedmodels \
		tensorflow-gpu==1.4.0 \
		tensorboard==1.11.0 \
		tensorboardX==1.4 \
		tensor2tensor==1.10.0 \
		torch==0.4.1 torchvision==0.2.1 

WORKDIR	/opt

RUN	git clone https://github.com/NVIDIA/nccl.git && cd nccl && make -j install && cd .. && rm -rf nccl

# config & cleanup
# ------------------------------------------------------------------
Run	ldconfig && \
	apt-get -y clean && \
	apt-get -y autoremove && \
	rm -rf /var/lib/apt/lists/* /tmp/* ~/*

EXPOSE 6006

WORKDIR	/

