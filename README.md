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
RESOLVED: use the same ~/G/coconut, in same way, adding it to system path in python code

* add preliminary run script `runYunitator.sh`
* run script first needs to produce HTK format features using OpenSmile - use the same config as OpenSAT: `/vagrant/MED_2s_100ms_htk.conf`
* add `extract-htk-vm2.sh` to do this
* Need to install also pytorch in the VM, with: `conda install pytorch-cpu torchvision -c pytorch`
* this unfortunately also requires CUDA - but installing CUDA extremely bloats the VM with unnecessary packages (full Ubuntu desktop)
