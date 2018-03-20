# Yunitator
Diarization of child / adult speech using a Pytorch classifier

Debugging/TODO:

* add git clone of this (or one cloned to aclew) repository to Vagrantfile
* needs fileutils.htk - add `../anaconda/bin/pip install htk_io` to Vagrantfile? didn't work

```
vagrant@vagrant-ubuntu-trusty-64:~/Yunitator$ ~/anaconda/bin/python diarize.py 
Traceback (most recent call last): 
  File "diarize.py", line 2, in <module>
    from fileutils.htk import *
ImportError: No module named fileutils.htk
```
