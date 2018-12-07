# helper_functions
This repository contains some commonly used helper functions. It's mainly for personal use but you are welcome to utilise this repository if you don't want to spend your worthless time on worthwhile things.

## Python
**Virtualenv linux:**
- Python2
```
sudo apt-get install python-virtualenv
virtualenv *env name*
source *env name*/bin/activate
```
- Python3
```
python3 -m *env name*
source *env name*/bin/activate
```
- Jupyter
```
From inside the virtualenv: pip install ipykernel; ipython kernel install --user --name=*env name*;
To remove virtualenv: ipython kernelspec uninstall project_name
List all kernelspec: jupyter kernelspec list
```

**Conda:**
- Virtualenv
```
conda create -n test_env python=3.6.3 anaconda
conda activate testenv
```
- Jupyter
```
 python -m ipykernel install --user --name *env name* --display-name "display name"
 jupyter kernelspec uninstall *env name*
```

To install package without using cached package: `--no-cache-dir`

To import module from another directory: `os.sys.path.append('../ModelFiles/ResNet'); import resnet`

[Understanding args & kwargs](https://www.digitalocean.com/community/tutorials/how-to-use-args-and-kwargs-in-python-3)

## Shell
to find a pattern in all files of a directory
```
grep -rnw /path/to/directory -e "pattern"
```
