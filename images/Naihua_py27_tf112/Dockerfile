FROM ufoym/deepo:py27

RUN sed -i 's/archive.ubuntu.com/mirrors.ustc.edu.cn/g' /etc/apt/sources.list && \
    apt update && \
    apt install -y openssh-server openssh-client && \
    apt install -y swig && \
	apt-get install -y python-tk && \
    pip install --upgrade pip && \
    pip install opencv-python && \
    pip install easydict && \
    pip install shapely && \
	pip install tflearn && \
	pip install tensorflow-gpu==1.12.0 && \
    apt-get clean && \
    apt-get autoremove