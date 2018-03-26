# DLfotCV cloud setting
## Environments
### Google Cloud instance
#### VMs
##### Tensorflow with GPU
###### Set up environment from scratch
``` bash
'''
The following script helps you install all the dependencies for keras.
We highly recommend that you run the following code, manually, line by line
to avoid any problem.

You need to run the code in order to avoid dependency issues.
'''

# essential
sudo apt-get update
sudo apt-get upgrade  
sudo apt-get install build-essential cmake g++ gfortran 
sudo apt-get install git pkg-config python-dev 
sudo apt-get install software-properties-common wget
sudo apt-get autoremove 
sudo rm -rf /var/lib/apt/lists/*


# install driver
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt-get update
sudo apt-get install nvidia-375

# reboot your machine
Sudo reboot

# check driver is installed correctly
nvidia-smi

# install cuda
wget https://developer.nvidia.com/compute/cuda/9.0/Prod/local_installers/cuda_9.0.176_384.81_linux-run
sudo chmod +x cuda_9.0.176_384.81_linux-run
sudo sh cuda_9.0.176_384.81_linux-run
'''
Executing cuda installation
1. scoll to the bottom of the license agreement using d
2. Do you accept the previously read EULA? : accept
3. Install NVIDIA Accelerated Graphics Driver for Linux-x86_64 384.81?: NO (we've installed manually)
4. Install the CUDA 9.0 Toolkit? : yes
5. Enter Toolkit Location: use default(press enter)
6. Do you want to install a symbolic link at /usr/local/cuda?: yes
7. Install the CUDA 9.0 Samples?: no
'''

# change environment for cuda
echo 'export PATH=/usr/local/cuda-9.0/bin:$PATH' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib64:$LD_LIBRARY_PATH' >> ~/.bashrc
source ~/.bashrc 

#verify your cuda is installed correctly
nvcc -V 

# install cuDNN 
# You need to register online and download the file to local file then upload to the cloud
# https://developer.nvidia.com/cudnn
# download the newest version for CUDA 9.0 and for Ubuntu 16.04.
chmod +x libcudnn7_7.1.2.21-1+cuda9.0_amd64.deb 
sudo apt install ./libcudnn7_7.1.2.21-1+cuda9.0_amd64.deb 

# python tool
sudo apt-get update && apt-get install -y python-numpy python-scipy python-nose python-h5py python-skimage python-matplotlib python-pandas python-sklearn python-sympy
sudo apt-get clean && sudo apt-get autoremove
sudo rm -rf /var/lib/apt/lists/*


# install python stuff
sudo apt-get update
sudo apt-get install git python-dev python3-dev python-numpy python3-numpy build-essential python-pip python3-pip python-virtualenv swig python-wheel libcurl3-dev
sudo apt-get install -y libfreetype6-dev libpng12-dev
pip3 install -U matplotlib ipython[all] jupyter pandas scikit-image

# install tensorflow
pip3 install --upgrade tensorflow-gpu

# keras
sudo pip3 install keras

# helpful tools 
# tmux: keep session in the background. Keep the session running even the ssh disconnects.
# nohup: similar to tmux. Keep things running. Log the output to nohup.log
```

##### Tensorflow without GPU
```
wget https://repo.continuum.io/archive/Anaconda3-5.1.0-Linux-x86_64.sh
bash Anaconda3-5.1.0-Linux-x86_64.sh
pip install tensorflow
```
#### ML engine
In the future.
### Google Colabotory
https://colab.research.google.com/notebooks/



'''
The following script helps you install all the dependencies for keras.
We highly recommend that you run the following code, manually, line by line
to avoid any problem.

You need to run the code in order to avoid dependency issues.
'''

