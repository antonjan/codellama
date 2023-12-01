# codellama (AI that generate code)
This repository will have all my code to use codelama for code complition capabilties for code dev environment
## Configuering my RTX3050 on ubuntu 22
     sudo apt-get remove --purge '^nvidia-.*'
     sudo apt-get remove --purge '^libnvidia-.*'
     sudo apt-get remove --purge '^cuda-.*'
     sudo apt-get remove --purge '^nvidia-.*'
     sudo apt-get remove --purge '^libnvidia-.*'
     sudo apt-get remove --purge '^cuda-.*'
     sudo apt autoremove
     sudo apt-get install linux-headers-$(uname -r)
     sudo add-apt-repository ppa:graphics-drivers/ppa --yes
     sudo apt update
     sudo ubuntu-drivers devices
     sudo ubuntu-drivers autoinstall
     sudo shutdown -r 0
now check if you can see the GPU     
     
     nvidia-smi
     Fri Dec  1 12:21:59 2023       
    +---------------------------------------------------------------------------------------+
    | NVIDIA-SMI 545.29.06              Driver Version: 545.29.06    CUDA Version: 12.3     |
    |-----------------------------------------+----------------------+----------------------+
    | GPU  Name                 Persistence-M | Bus-Id        Disp.A | Volatile Uncorr. ECC |
    | Fan  Temp   Perf          Pwr:Usage/Cap |         Memory-Usage | GPU-Util  Compute M. |
    |                                         |                      |               MIG M. |
    |=========================================+======================+======================|
    |   0  NVIDIA GeForce RTX 3050        Off | 00000000:01:00.0 Off |                  N/A |
    |  0%   39C    P8               7W / 140W |     18MiB /  8192MiB |      0%      Default |
    |                                         |                      |                  N/A |
    +-----------------------------------------+----------------------+----------------------+
                                                                                             
    +---------------------------------------------------------------------------------------+
    | Processes:                                                                            |
    |  GPU   GI   CI        PID   Type   Process name                            GPU Memory |
    |        ID   ID                                                             Usage      |
    |=======================================================================================|
    |    0   N/A  N/A      1813      G   /usr/lib/xorg/Xorg                            9MiB |
    |    0   N/A  N/A      2455      G   /usr/bin/gnome-shell                          2MiB |
    +---------------------------------------------------------------------------------------+

       ubuntu-drivers devices
All the available drivers are already installed.
anton@anton-MS-7D46:~$ ubuntu-drivers devices
== /sys/devices/pci0000:00/0000:00:01.0/0000:01:00.0 ==
modalias : pci:v000010DEd00002507sv000010DEsd00002507bc03sc00i00
vendor   : NVIDIA Corporation
driver   : nvidia-driver-545 - third-party non-free
driver   : nvidia-driver-520 - third-party non-free
driver   : nvidia-driver-525 - third-party non-free
driver   : nvidia-driver-515 - third-party non-free
driver   : nvidia-driver-530 - third-party non-free
driver   : nvidia-driver-510 - distro non-free recommended
driver   : nvidia-driver-510-server - distro non-free
driver   : nvidia-driver-535 - third-party non-free
driver   : xserver-xorg-video-nouveau - distro free builtin
reboot
Check if you RTX device is seen by ubuntu

    lshw -numeric -C display
    
  *-display                 
       description: VGA compatible controller
       product: GA106 [Geforce RTX 3050] [10DE:2507]
       vendor: NVIDIA Corporation [10DE]
       physical id: 0
       bus info: pci@0000:01:00.0
       logical name: /dev/fb0
       version: a1
       width: 64 bits
       clock: 33MHz
       capabilities: pm msi pciexpress vga_controller cap_list fb
       configuration: depth=32 latency=0 mode=1600x900 visual=truecolor xres=1600 yres=900
       resources: iomemory:600-5ff iomemory:600-5ff memory:81000000-81ffffff memory:6000000000-600fffffff memory:6010000000-6011ffffff ioport:3000(size=128) memory:c0000-dffff
  *-display
       description: Display controller
       product: Alder Lake-S GT1 [UHD Graphics 770] [8086:4690]
       vendor: Intel Corporation [8086]
       physical id: 2
       bus info: pci@0000:00:02.0
       logical name: /dev/fb0
       version: 0c
       width: 64 bits
       clock: 33MHz
       capabilities: pciexpress msi pm bus_master cap_list fb
       configuration: depth=32 driver=i915 latency=0 resolution=1600,900
       resources: iomemory:600-5ff iomemory:400-3ff irq:137 memory:6012000000-6012ffffff memory:4000000000-400fffffff ioport:4000(size=64) memory:4010000000-4016ffffff memory:4020000000-40ffffffff
     


## Instelation of codellama models from Meta
First have anove disk apace tpo download the models you are interested
run the download.sh script and add the licence url receved by email from meta
request a new download link from metha https://ai.meta.com/resources/models-and-libraries/llama-downloads/
compleet the form and then enter the url that you have receved by email into the download script whet asked. EG. Enter the URL from email: https://download2.llamameta.net/*?Policy=eyJTdGF0ZW1.......
Then select the Modles you want to download from the list by entering them with comma delimited and press enter

      Enter the list of models to download without spaces (7b,13b,34b,7b-Python,13b-Python,34b-Python,7b-Instruct,13b-Instruct,34b-Instruct), or press Enter for all: 13b,13b-Python,13b-Insruct 

Down load will start and it could take a long time to compleetdepending on the models you have selected

If you want to download from huggyface that is already precompiled you can download here https://huggingface.co/TheBloke/CodeLlama-34B-Instruct-GGUF
selectthe gguf file you need
### How do I select the correct compiled vertion
More parameters will be better, even if at a lower precision. Its definitely worth it.
The rule of thumb is to always get a model with a higher number of parameters even lower precision, over a model with less parameters and higher precision. However, there are exceptions to the rule.
See selection below<br>
![Alt text](codellama_hugyface_download.png?raw=true "codellamma selection")<br>
I selected https://huggingface.co/TheBloke/CodeLlama-34B-Instruct-GGUF/resolve/main/codellama-34b-instruct.Q2_K.gguf?download=true
my GPU RTX3050<br>
NVIDIA CUDA Cores	2560 / 2304<br>
Boost Clock (GHz)	1.78 / 1.76<br>
Memory Size	8 GB<br>
Memory Type	GDDR6<br>

     wget https://huggingface.co/TheBloke/CodeLlama-34B-Instruct-GGUF/resolve/main/codellama-34b-instruct.Q2_K.gguf?download=true





