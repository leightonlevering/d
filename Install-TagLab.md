# Installing TagLab

### Step 0: Dependencies

Before installing TagLab, be sure to have installed __a 64 bit version of Python 3.8.x, 3.9.x, or 3.10.x__, and __NVIDIA CUDA Toolkit__ on Linux or Windows.

NVIDIA CUDA Toolkits can be downloaded at the following links:

* [CUDA Toolkit 10.2](https://developer.nvidia.com/cuda-10.2-download-archive)<br>
* [CUDA Toolkit 11.3](https://developer.nvidia.com/cuda-11.3.0-download-archive)<br>
* [CUDA Toolkit 11.6](https://developer.nvidia.com/cuda-11-6-0-download-archive) (Recommended)<br>
* [CUDA Toolkit 11.7](https://developer.nvidia.com/cuda-11-7-0-download-archive)<br>

__IMPORTANT NOTE: When you install Python under Windows pay attention to add it to the PATH and to click on Disable PATH Limit Length__ before leaving the setup (see the screenshots below). 

<p align="center"">
<img src="https://github.com/cnr-isti-vclab/TagLab/blob/main/docs/python-installation-add-to-PATH.png" width=600px>
<img src="https://github.com/cnr-isti-vclab/TagLab/blob/main/docs/python-disable-path-length-limit.png" width=600px>
</p>

You can check if Python and CUDA are properly installed by running the following commands in a shell (bash on Linux, poweshell on Windows; for MacOS just check the Python version):

```
python3 --version
nvcc --version
```
If python and cuda are properly installed, both commands will print their versions.

#### Windows

Under Windows, you need also to install the Visual Studio Redistributable. Download them from this [link](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170). 

#### Linux

Under Linux, if you use a debian-based distribution (e.g. Ubuntu), except for python and nvcc, there are no other real requirements: the installer will take care of get and install all the dependencies. If you don't use the APT package manager (not ubuntu or debian derived distros), you'll need to install manually the gdal library (the command `gdal-config --version` should output the gdal library version), and `cmake`. Check out for your distribution how to install these two packages!

#### MacOS

On MacOS, the only real requirement (besides python) is the HomeBrew package manager: be sure to have it installed before running the installer. You can check [here](https://brew.sh/) the instructions on how to install it. If you don't want to install the HomeBrew package manager, be sure to install the gdal library manually (the command `gdal-config --version` should output the gdal library version), and `cmake`.

### Step 1: Clone the repository
Just click on the "Clone or Download" button at the top of this page and unzip the whole package in a folder of your choice.

### Step 2: Install all the dependencies

- open a terminal (not python prompt!);
- change directory to the TagLab main directory: type `cd ` (be sure to type the space after `cd`) and then drag and drop into the terminal the TagLab folder; then click `enter`;
- type the following command in the terminal:

```
python3 install.py
```
or, on Windows:

```
python.exe install.py
```

The script will automatically install the remaining libraries required by TagLab and download the network weights.
If NVIDIA CUDA Toolkit is not supported by your machine, the script will ask to install the cpu version.
You can bypass this step and force to install the cpu version directly by running
```
python3 install.py cpu
```
or, on Windows:

```
python.exe install.py cpu
```

### Step 3: Run
Just start `TagLab.py` from a command shell or your preferred Python IDE.

From a terminal simply write:

```
python3 TagLab.py
```
or, on Windows:

```
python.exe taglab.py
```

To test if TagLab works correctly, try to open the sample project available in the `projects` folder.


### Known problems and how to solve them

* The update of the 7th of October 2022 introduce a dependency from `pycocotools` to export dataset in COCO format. After this update you need
to install Microsoft Visual C++ Build Tools from this link [link](https://visualstudio.microsoft.com/visual-cpp-build-tools) (for Windows) and re-run install.py (for all systems). 

* If PyQt not work properly under WIndows (e.g. import problems when TagLab is launched) perhaps the Microsoft Visual C++ Redistributable is not installed on your machine. Download and install it using this [link](https://aka.ms/vs/17/release/vc_redist.x64.exe) .



