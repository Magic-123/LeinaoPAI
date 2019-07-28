FROM 10.11.3.8:5000/pai-images/deepo:v2.0

RUN rm -rf /var/lib/apt/lists/* \
           /etc/apt/sources.list.d/cuda.list \
           /etc/apt/sources.list.d/nvidia-ml.list && \
    sed -i 's/archive.ubuntu.com/mirrors.ustc.edu.cn/g' /etc/apt/sources.list && \
    apt-get update -y && \
    apt-get install -y python3-pip python3-dev openssh-client openssh-server && \
    apt-get install -y python3-tk unrar git && \
    pip3 install numpy scipy matplotlib SimpleITK pillow pypng tifffile rarfile pandas && \
    pip3 install https://download.pytorch.org/whl/cpu/torch-1.0.1.post2-cp35-cp35m-linux_x86_64.whl &&\
    pip3 install torchvision tensorboardX opencv-python yacs torchsummary nibabel&& \
    apt-get update -y && \
    # apt-get install -y --allow-downgrades --no-install-recommends libcudnn7=7.0.5.15-1+cuda9.0 libcudnn7-dev=7.0.5.15-1+cuda9.0 && \
    rm -rf /var/lib/apt/lists/*  
    # apt-get update -y