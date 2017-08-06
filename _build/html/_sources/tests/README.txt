Running nosetests
======================

- Requirements:
  
  >>> pip install nose

- run tests easily via (from the repository root):
  
  >>> nosetests -v


- These run tests written in /tests/
- a **.noserc** file is in the repository but must be copied to your home directory (cp .noserc ~/.noserc) to have any effect.




*****************
GENERAL NOTES:
*****************
.. note:: [May 2016, David V.] 	

* **These are not unit tests**; they test higher capabilities, like can simulate run for example and are meant to be just basic tests that 
  the repository is not broken. It is envisaged that they'll be run before git commits and pushes for example.

* Any one who wants to write actual unit tests is welcome to add these to the repository... 

* There are some odd looking python path adjustments at the start of the test_X.py files. These aren't needed in general, but tests wheren't 
  running on camdial for example without them. They look like this:
  
  >>> import os,sys
  >>> curdir = os.path.dirname(os.path.realpath(__file__))
  >>> curdir = curdir.split('/')
  >>> curdir = '/'.join(curdir[:-1]) +'/'
  >>> sys.path.append(curdir) 
	
***********************
**Other useful tools**
***********************

* The following python tools are really helpful for checking your code in various ways (well basically just *speed* and *quality*)
* **pylint**: detects outright errors but otherwise gives suggestions on code styles and conventions. Simply run, for example: 
  
  >>> pylint Simulate.py 

* **cProfile**: Full profiling of every method called in executing some python code (including imported methods from the standard library etc). 
  cProfile is part of the python std lib. Simply run, for example:
  
  >>> python -m cProfile Simulate.py -c _config/simulate_multiDomains_HDC.cfg 

* **profilehooks**: great for profiling individual methods. Uses decorators to do so. Requires installing:
  
  >>> pip install profilehooks
