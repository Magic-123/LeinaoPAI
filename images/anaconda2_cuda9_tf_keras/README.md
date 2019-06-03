#base Ubuntu16.04 CUDA9.0 Anaconda2

cuda 9.0.176
cudnn 7.0.5.15
tensorflow 1.5.0
keras 2.0.6
opencv 4.1.0

#BUILD
sudo docker build -t [Dockername:tag] .

#RUN
sudo nvidia-docker run -it [Dockername]
