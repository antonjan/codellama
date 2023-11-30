# codellama (AI that generate code)
This repository will have all my code to use codelama for code complition capabilties for code dev environment
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
NVIDIA CUDA Cores	2560 / 2304
Boost Clock (GHz)	1.78 / 1.76
Memory Size	8 GB
Memory Type	GDDR6

     wget https://huggingface.co/TheBloke/CodeLlama-34B-Instruct-GGUF/resolve/main/codellama-34b-instruct.Q2_K.gguf?download=true





