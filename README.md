# TensorflowServer_Setup
[1] 	Install ubuntu 18.04 from USB stick
[2] 	Set computer as server: 
sudo apt-get install openssh-server (Ref: http://ubuntuhandbook.org/index.php/2016/04/enable-ssh-ubuntu-16-04-lts/ )
Trouble-shooting (Ref: https://stackoverflow.com/questions/20840012/ssh-remote-host-identification-has-changed  )
[3]	Install drivers
sudo ubuntu-drivers autoinstall (Ref: https://linuxconfig.org/how-to-install-the-nvidia-drivers-on-ubuntu-18-04-bionic-beaver-linux)
sudo reboot
[4] 	Install cuda
(Ref: https://medium.com/@kekayan/step-by-step-guide-to-install-tensorflow-gpu-on-ubuntu-18-04-lts-6feceb0df5c0, Step 2)
(1) 	Download CUDA Toolkit 9.0
(2) 	sudo chmod +x cuda_9.0.176_384.81_linux.run
./cuda_9.0.176_384.81_linux.run --override
(No to “Install NVIDIA Accelerated Graphics Driver for Linux-x86_64 384.81?”)
(3) 	(Ref: https://github.com/williamFalcon/tensorflow-gpu-install-ubuntu-16.04)
export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/usr/local/cuda/lib64:/usr/local/cuda/extras/CUPTI/lib64"
export CUDA_HOME=/usr/local/cuda
source ~/.bashrc
[5]	Install Tensorflow
(Ref: https://www.tensorflow.org/install/install_linux)
sudo apt-get install python-pip
sudo pip install --upgrade pip
(Fix bug of pip 10.0.0: https://stackoverflow.com/questions/28210269/importerror-cannot-import-name-main-when-running-pip-version-command-in-windo)
sudo  pip install --upgrade tensorflow 
(Fix GPU problem if needed:   sudo apt-get install nvidia-modprobe)
[6]	Install Bazel: 	
https://docs.bazel.build/versions/master/install-ubuntu.html
