# nvidia_cuda_fedora_cheatsheet

Nvidia Cuda Fedora Cheatsheet 

```bash
dnf list installed | grep cuda
```

Cuda Toolkit
https://developer.nvidia.com/cuda-downloads


starting clean-up commands to run first
```bash
sudo dnf -y remove nvidia* --allowerasing
sudo dnf -y remove nvidia-driver
sudo dnf -y module reset nvidia-driver
sudo /usr/bin/nvidia-uninstall

sudo /usr/local/cuda-X.Y/bin/cuda-uninstall
e.g.
sudo /usr/local/cuda-12.3/bin/cuda-uninstall

sudo dnf upgrade --refresh
```

Import Nvidia CUDA Repository for Fedora ###/
```bash
sudo dnf config-manager --add-repo https://developer.download.nvidia.com/compute/cuda/repos/fedora###/x86_64/cuda-fedora###/repo
```

Install the necessary dependencies for NVIDIA Drivers:
```bash
sudo dnf install kernel-headers kernel-devel tar bzip2 make automake gcc gcc-c++ pciutils elfutils-libelf-devel libglvnd-opengl libglvnd-glx libglvnd-devel acpid pkgconfig dkms

sudo dnf module list nvidia-driver

sudo dnf -y module install nvidia-driver:latest-dkms
```

Add a path line to bashrc file:
```bash
nano ~/.bashrc
```

Add:
# User specific environment for CUDA
if ! [[ "$PATH" =~ "/usr/local/cuda/bin:" ]]
then
    PATH="/usr/local/cuda/bin:$PATH"
fi
export PATH




Check
```bash
nvidia-smi

nvcc --version

/usr/local/cuda/bin/nvcc --version

	
```



