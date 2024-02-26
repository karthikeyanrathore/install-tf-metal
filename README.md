## How to install tensorflow and other packages on Metal (Mac M1)?

steps
1. First you need to install miniforge3, i don't know how i previously installed this :P but i can provide you the latest way.
    
```bash
curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"
bash Miniforge3-$(uname)-$(uname -m).sh
```

2. Activate miniforge3.

```bash
source ~/miniforge3/bin/activate
```

3. restart terminal.
4. prevent conda to activate base environment by default.
```bash
conda config --set auto_activate_base False
```
5. again restart terminal.
6. export these commands
```bash
export GRPC_PYTHON_BUILD_SYSTEM_OPENSSL=1
export GRPC_PYTHON_BUILD_SYSTEM_ZLIB=1
```
7. Now is the main step to install tf and other packages (see config.yml) in a virtual env.
```bash
conda env create -f config.yml -n metal
```
8. activate metal env.
```bash
conda activate metal.
```

