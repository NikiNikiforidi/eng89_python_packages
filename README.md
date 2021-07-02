# Building python packages
### What is a python package and benefits
#### In my case in pycharm, eng89_Python_Packages in a package and app is a directory

**Definition:** Python packages are a way to structure python programs in a form to be reused and included in other programs 
- A link to python packages information: [Python-Packaging](https://python-packaging.readthedocs.io/en/latest/minimal.html)

- Step 1 `Create an app folder`
- Step 2 inside app folder`__init__.py` leave it empty - to initialise our package
- Step 3 inside app folder `fizzbuzz.py`- to add our functionality
- Step 4 `program.py` on dir level - to use to run file 
- `setup.py` on a dir level - to describe our module details such as version, author and content details

```
eng89_python_packages
-- app # Right click project name, open new Directory and name it app
--- __init__.py
--- fizzbuzz.py
program.py
setup.py

```
#### __init__.py
`# __init__.py is in app directory`


#### setup.py file

```
# setup.py file is not in app directory

from setuptools import setup

# Built in package to create aything and everything related to this module 
from setuptools import setup

# Lets add some information about the package

setup(name="app")
version = "1.0"
description = "Python app"
author = "Niki at Sparta Global"
author_email = "Bloop.com"
url = "http//: Something here"
```

#### fizzbuzz.py file


```

# This fizzbuzz file is in the app directory

class Fizzbuzz:

    def __init__(self, start_of_range, end_of_range):
        self.fizzrange = range(start_of_range, end_of_range)
        self.fizzbuzz_list = []
        self._fizzbuzz_iterator()

    def _divisible_by(self, num1, num2):
        if num1 % num2 == 0:
            return True
        else:
            return False

    def _fizzbuzz_iterator(self):

        for num in self.fizzrange:
            if self._divisible_by(num, 15):
                self.fizzbuzz_list.append("fizzbuzz")
            elif self._divisible_by(num, 5):
                self.fizzbuzz_list.append("buzz")
            elif self._divisible_by(num, 3):
                self.fizzbuzz_list.append("fizz")
            else:
                self.fizzbuzz_list.append(num)



#print(Fizzbuzz(1,10).fizzbuzz_list)


```

#### program.py file

```
# The program.py file is not in the app directory


from app.fizzbuzz import Fizzbuzz

obj = Fizzbuzz(1,100)
print(obj.fizzbuzz_list)
```

