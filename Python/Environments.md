
# Conda

Activating/Deactivating:
```shell
# activates base environment
conda activate

# deactivate environment
conda deactivate
```

Creating/deleting environment:
```shell
# create environment
conda create -n <env_name>
# create environment with specified python version
conda create -n <env_name> python=<version>

# place environment elsewhere
conda create -n <path/env_name> 

# remove environment
conda remove -n <env_name> --all

```



Listing, showing environments, packages infos:
```shell
# conda info
conda info

# conda version
conda --version


# list conda environments
conda env list

# list packages
conda list

# specific package version
conda list <package_name>
```
