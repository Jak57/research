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

## Running Python in cmd
* ``python3 code.py``
  
## Dataset
* MixSet: https://llm-coauthor.github.io/

## Other
* RAID is the largest and most challenging benchmark for AI-generated text detection. (ACL 2024): https://github.com/liamdugan/raid
* LLM-as-a-Coauthor: Can Mixed Human-Written and Machine-Generated Text Be Detected?: https://arxiv.org/pdf/2401.05952
