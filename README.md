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
* "None" replaced with "nil"
* "True" replaced with "true"
* "False" replaced with "false"
*  function "def" replaced with "function" (from javascript)
* remove "self" as the function first arg, "self" will be insterted in compiling stage.
* "self" is replaced with "this" (from c++/javascrpit/c#)
* In class method , using **this** keyword reference to the class instance(the function first argument)
* In classmethod, using **cls** keyword reference to the class object(the function first argument)

Python:
  
    try:
      if True:
        print "If True"
    except:
      print "except could with none parameter"
      
     class Base(object):
      def __init__(self):
        print "Class Base"
        self.value = None
        
      def show(self):
        print self.value
      
Tiny Python:

    try 
    {
      if true
      {
        print "If true";
      }
    } 
    except Exception 
    {
      print "except must have one expression...";
    }
    
    class Base(object)
    {
      function __init__()
      {
        print "Class Base";
        this.value = nil;
      }
      
      function show()
      {
        print this.value;
      }
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
    
    
    
