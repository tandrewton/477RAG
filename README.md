Final project for Yale CPSC 477 - Natural Language Processing, authored by Andrew Ton and Yuxuan Cheng. Using Retrieval-Augmented Generation to tackle BioLaySumm 2024, BioNLP task.

<img width="518" alt="image" src="https://github.com/user-attachments/assets/83d917ea-2c05-4555-9b39-ead2b0448218">


The repo is adapted from localGPT, see more detials on setting up here: https://github.com/PromtEngineer/localGPT

# Environment Setup 🌍

1. 📥 Clone the repo using git:

```shell
[git clone https://github.com/PromtEngineer/localGPT.git](https://github.com/YUXUANCHENG/477RAG.git)
```

2. 🐍 Install [conda](https://www.anaconda.com/download) for virtual environment management. Create and activate a new virtual environment.

```shell
conda create -n localGPT python=3.10.0
conda activate localGPT
```

3. 🛠️ Install the dependencies using pip

To set up your environment to run the code, first install all requirements:

```shell
pip install -r requirements.txt
```

***Installing LLAMA-CPP :***

LocalGPT uses [LlamaCpp-Python](https://github.com/abetlen/llama-cpp-python) for GGML (you will need llama-cpp-python <=0.1.76) and GGUF (llama-cpp-python >=0.1.83) models.


If you want to use BLAS or Metal with [llama-cpp](https://github.com/abetlen/llama-cpp-python#installation-with-openblas--cublas--clblast--metal) you can set appropriate flags:

For `NVIDIA` GPUs support, use `cuBLAS`

```shell
# Example: cuBLAS
CMAKE_ARGS="-DLLAMA_CUBLAS=on" FORCE_CMAKE=1 pip install llama-cpp-python==0.1.83 --no-cache-dir
```

For Apple Metal (`M1/M2`) support, use

```shell
# Example: METAL
CMAKE_ARGS="-DLLAMA_METAL=on"  FORCE_CMAKE=1 pip install llama-cpp-python==0.1.83 --no-cache-dir
```
For more details, please refer to [llama-cpp](https://github.com/abetlen/llama-cpp-python#installation-with-openblas--cublas--clblast--metal)

To run LocalGPT: 
```shell
python run_localGPT.py
```

To embed documents: 
```shell
python ingest.py
```

To run evaluation: 
```shell
python evaluate.py
```

Final Metric score results are stored in gpt_scores.txt and llama_scores.txt

Dependencies are listed in requirements.txt
