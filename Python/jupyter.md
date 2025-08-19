
----
## Updating jupyter
Generally good idea to update all core packages at once:
```shell
>> jupyter --version
Selected Jupyter core packages...
IPython          : 8.12.2
ipykernel        : 6.23.1
ipywidgets       : not installed
jupyter_client   : 8.2.0
jupyter_core     : 5.3.0
jupyter_server   : 2.6.0
jupyterlab       : 4.0.1
nbclient         : 0.8.0
nbconvert        : 7.4.0
nbformat         : 5.9.0
notebook         : not installed
qtconsole        : not installed
traitlets        : 5.9.0
>> pip install --upgrade IPython ipykernel  ipywidgets jupyter_client jupyter_core jupyter_server jupyterlab nbclient nbconvert nbformat notebook qtconsole traitlets
```

----
## Adding conda environment in jupyter
If conda environment is not showing in jupyter, then probably the jupyter used is from outside the conda environment and the current environment doesnt have ipykernel.  
```shell
# inside the conda environment install ipykernel
pip install ipykernel

# configure jupyter to use this kernel
ipython kernel install --user --name=my-conda-env-kernel
```

----
