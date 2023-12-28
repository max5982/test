

Llama2 - https://github.com/facebookresearch/llama
```
https://github.com/facebookresearch/llama.git
cd llama
python3 -m venv venv_llama
source venv_llama/bin/activate
pip install -U pip wheel
pip install -e .
```
### Access on Hugging Face

We are also providing downloads on [Hugging Face](https://huggingface.co/meta-llama). You must first request a download from the Meta website using the same email address as your Hugging Face account. After doing so, you can request access to any of the models on Hugging Face and within 1-2 days your account will be granted access to all versions.

## Quick Start

You can follow the steps below to quickly get up and running with Llama 2 models. These steps will let you run quick inference locally. For more examples, see the [Llama 2 recipes repository](https://github.com/facebookresearch/llama-recipes).

1. In a conda env with PyTorch / CUDA available clone and download this repository.

2. In the top level directory run:
    ```bash
    pip install -e .
    ```
3. Visit the [Meta website](https://ai.meta.com/resources/models-and-libraries/llama-downloads/) and register to download the model/s.

4. Once registered, you will get an email with a URL to download the models. You will need this URL when you run the download.sh script.

5. Once you get the email, navigate to your downloaded llama repository and run the download.sh script.
    - Make sure to grant execution permissions to the download.sh script
    - During this process, you will be prompted to enter the URL from the email.
    - Do not use the “Copy Link” option but rather make sure to manually copy the link from the email.

6. Once the model/s you want have been downloaded, you can run the model locally using the command below:
```bash
torchrun --nproc_per_node 1 example_chat_completion.py \
    --ckpt_dir llama-2-7b-chat/ \
    --tokenizer_path tokenizer.model \
    --max_seq_len 512 --max_batch_size 6
```






https://github.com/facebookresearch/llama-recipes/

https://huggingface.co/meta-llama
