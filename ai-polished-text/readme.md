# Resources for AI-polished-text Project

## Connecting Terminus with VS Code
* Install the **Remote SSH** extension from Visual Studio (VS) Code
* Press ``ctl + shift + p``; shell prompt will be opened
* Select ``Remote-SSH: Add New SSH Host`` or ``Remote-SSH: Connect to Host`` based on your requirement
* Enter the following command to add a new host
    * ``ssh -p 2025 root@148.72.133.91 -A`` (port is fixed)
       * ssh port: ``2025``
       * pass: ``lM52RHTUkg7W@2025``
    * ``ssh ipt@119.148.4.20 -A`` (default port: 22)
       * GPU access:
       * IP: ``119.148.4.20``
       * user: ipt
       * pass: ``PKRy&^`7hT8C3*sLDnz;g6``
       * Available GPU in user namespace: ``Tesla T4 16GB``

## Setup conda
* ``wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh``
* ``bash Miniconda3-latest-Linux-x86_64.sh``
* ``bash``
* ``source ~/miniconda3/etc/profile.d/conda.sh``
* ``conda activate base``
* ``conda activate apt_env``

## Project Location
* ``cd projects/ai-polished-text/ai-polished-text-jakir/data``

## Running Python in cmd
* ``python3 json_to_csv.py``
  
## Dataset
* MixSet: https://llm-coauthor.github.io/

## Loading Model from HuggingFace and Running Locally
* Getting access token - https://huggingface.co/settings/tokens
   * ``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`` (read)
* ``huggingface-cli login``
* Code for downloading and loading the model
   * Download
  ```python
   import torch
   from transformers import AutoModelForCausalLM, AutoTokenizer
   
   access_token = "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"
   model_name = "meta-llama/Llama-2-7b-chat-hf"
   
   tokenizer = AutoTokenizer.from_pretrained(model_name, token=access_token)
   model = AutoModelForCausalLM.from_pretrained(model_name, token=access_token)
   
   tokenizer.save_pretrained(f"Adversarial_LLM/tokenizers/{model_name}")
   model.save_pretrained(f"Adversarial_LLM/models/{model_name}")
   ```

   * Access the local model
   ```python
   import torch
   from transformers import AutoModelForCausalLM, AutoTokenizer
   
   model_name = "meta-llama/Llama-2-7b-chat-hf"
   tokenizer = AutoTokenizer.from_pretrained(f"Adversarial_LLM/tokenizers/{model_name}")
   model = AutoModelForCausalLM.from_pretrained(f"Adversarial_LLM/models/{model_name}")
   
   prompt = "What is the capital of Russia?"
   prompt_encodings = tokenizer(prompt, return_tensors="pt").to(model.device)
   response = model.generate(**prompt_encodings)
   print(tokenizer.decode(response[0], skip_special_tokens=True))
   ```

## Large Language Models (LLM)
* https://huggingface.co/meta-llama/Llama-2-7b-chat-hf
* https://huggingface.co/meta-llama/Meta-Llama-3-8B-Instruct

## Other
* RAID is the largest and most challenging benchmark for AI-generated text detection. (ACL 2024): https://github.com/liamdugan/raid
* LLM-as-a-Coauthor: Can Mixed Human-Written and Machine-Generated Text Be Detected?: https://arxiv.org/pdf/2401.05952
