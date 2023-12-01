# codellama (AI that generate code)
This repository will have all my code to use codelama for code complition capabilties for code dev environment
## Configuering my RTX3050 on ubuntu 22
     sudo ubuntu-drivers autoinstall
then check if drivers is installed

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





