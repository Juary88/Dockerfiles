# Nvidia TF1.9+jupyter notebook

This docker image is based on nvcr.io/nvidia/tensorflow:18.07-py3.

But it also adds jupyter notebook and some other useful packages like keras and sklearn for machine learning and deep learning.

## Its environment
Ubuntu 16.04

TensorFlow 1.9

## To use it
```sh
$ docker pull nvcr.io/nvidia/tensorflow:18.07-py3
$ git clone https://github.com/keineahnung2345/Dockerfiles.git
$ docker build . -t nvcr.io/nvidia/tensorflow:18.08-py3-jupyter
$ NV_GPU=<your_gpu_ids> nvidia-docker run --name tf-jupyter -td -p 8888:8888 -p 6006:6006 \
-v /root/tensorflow-tensorlog:/tensorlog -v /root/tensorflow-data:/notebooks \
-v /var/tensorflow-dataset:/mnt -e PASSWORD=<password_for_jupyter_notebook> \
--restart always nvcr.io/nvidia/tensorflow:18.08-py3-jupyter
```

And then open your browser and navigate to <http://your_host_ip:8888>, after keying in the password you have set, you can start to use jupyter notebook.

## To enter the docker you have built

docker exec -it tf-jupyter bash