# simple_elastix_mac_m1_install_notes
I encountered many errors following the steps to build the library, here's the summary and hope it helps people!
<br /> I'm on the "develop" branch due to potential compiling error in the master branch experienced by some users
<br /> To clone develop branch, do "git clone --branch develop https:......"


## Can't find Ruby, Ruby_EXECUTABLE_LIBRARY etc
If you're only using Python, you can change Wrap Ruby to False
<br /> The place to change can be found in the cmake cache txt in the build directory after cmake

## Can't find Python.h
This occurs somewhere near the end of the make process
use this: export CPLUS_INCLUDE_PATH=/opt/homebrew/Cellar/**python@3.10**/**3.10.8**/Frameworks/Python.framework/Versions/**3.10**/include/python**3.10**
<br /> Note the python version depends on your system

## Setup.py.in instead of Setup.py
I followed the answer in their github, which simply removed the .in suffix

## @SimpleITK_BINARY_MODULE@': doesn't exist or not a regular file
I followed the solution here, changing the part "@SimpleITK_BINARY_MODULE@" to "__SimpleITK.so_" https://github.com/SuperElastix/SimpleElastix/issues/438

## Don't forget to pip3 install SimpleITK-SimpleElastix
