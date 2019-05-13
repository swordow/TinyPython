# Tiny Python
Base on Python2.7.16

# Why?
I like python, but dont like indent/dedent for code block package. 
In fact, some cases, indent makes a mass.., 
so modify the grammar a little.

# Difference
Code Block lies between '{' '}' as well as c/c++ language.

Python:
  
    if True:
      print "If True"
      
Tiny Python:

    if True
    {
      print "If True";
    }
    
# Build & Install
Build is based on python-cmake-buildsystem, after checking out the repo, update the python-cmake-buildsystem submodule, and switch to **ForTPY** Branch.

    cd TinyPython
    git submodule update --init python-cmake-buildsystem
    cd python-cmake-buildsystem
    git pull origin ForTPY
    git checkout ForTPY
    cd .. 
    mkdir build
    mkdir install
    cd build 
    cmake -DCMAKE_INSTALL_PREFIX=/path/to/install ./python-cmake-buildsystem
    make && make install
    
    
    
