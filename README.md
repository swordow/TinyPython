# Tiny Python
Base on Python2.7.16

# Why?
I like python, but dont like indent/dedent for code block package. 
In fact, some cases, indent makes a mass.., 
so modify the grammar a little.

# Difference

* Using '{' and '}', Code Block lies between '{' '}' as well as c/c++ language.
* Statement must ends with ';'
* In 'try except' statement, except must be followed with a expression

Python:
  
    try:
      if True:
        print "If True"
    except:
      print "except could with none parameter"
      
Tiny Python:

    try 
    {
      if True
      {
        print "If True";
      }
    } 
    except Exception 
    {
      print "except must have one expression...";
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
    
    
    
