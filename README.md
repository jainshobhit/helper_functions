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
sudo pip3 install virtualenv 
virtualenv -p python3 myenv
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
to find a pattern in all files of a directory: ` grep -rnw /path/to/directory -e "pattern" `

Check CUDA version: `cat /usr/local/cuda/version.txt`

check cuDNN version: `cat /usr/include/x86_64-linux-gnu/cudnn_v*.h | grep CUDNN_MAJOR -A 2 || cat /usr/local/cuda/include/cudnn.h | grep CUDNN_MAJOR -A 2`

Add a new variable to environment variable: `export LD_LIBRARY_PATH=/path/to/library:${LD_LIBRARY_PATH}`

Linux screen commands links: [1](https://kb.iu.edu/d/acuy) [2](https://www.tecmint.com/screen-command-examples-to-manage-linux-terminals/)
## C++
Compiling a C++ file to object file: `g++ -c foo.o -std=c++11 foo.cpp`

Linking several or one object file: `g++ foo.o foo1.o -o foo`

Running the executable: `./foo $args$`

Directly compiling and linking: `g++ -o foo -std=c++11 foo.cpp`

For a general explanation of C++ build system, refer [Here](https://gist.github.com/gubatron/32f82053596c24b6bec6)

**Static libraries**
When you have several .o files, you can put them together as a library, a static library. In Linux/Mac these static libraries are simply archive files, or .a files. To link several object files in a static library `ar -cvq foostatic.a foo1.o foo2.o foo3.o`

To verify the static libraries: `ar -t foostatic.a`  This will spit out the object files it is composed up of.

To compile using static library so that the compiler knows to link it later, use: `g++ -o output main.cpp foodstatic.a`. Or if you have several static libraries in a folder, use: `g++ -o output main.cpp -L(path of static library) -l(name of static library)`

For eg. to connect with OpenCV libraries: `g++ foo.cpp -L/path/to/opencv/lib -lopencv_core -lopencv_imgcodecs`. If you want to use further functions of OpenCV not found in these libraries, you might have to link against additional OpenCV libraries.

If it is a frequently used library, you can add the path to LD_LIBRARY_PATH and the compiler will automatically load the libraries from there.

## Git
[Merging & Branching](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)

[Overwriting local changes](https://stackoverflow.com/questions/1125968/how-do-i-force-git-pull-to-overwrite-local-files)
