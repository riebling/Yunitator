# Yunitator
Diarization of child / adult speech using a Pytorch classifier

Debugging/TODO:

* add git clone of this (or one cloned to aclew) repository to Vagrantfile
* needs fileutils.htk - add `../anaconda/bin/pip install htk_io` to Vagrantfile? didn't work

```
vagrant@vagrant-ubuntu-trusty-64:~/Yunitator$ ./runYunitator.sh /vagrant/test2.wav 
Extracting features for test2.wav ...
(MSG) [2] in SMILExtract : openSMILE starting!
(MSG) [2] in SMILExtract : config file is: /vagrant/MED_2s_100ms_htk.conf
(MSG) [2] in cComponentManager : successfully registered 95 component types.
(MSG) [2] in cComponentManager : successfully finished createInstances
                                 (19 component instances were finalised, 1 data memories were finalised)
(MSG) [2] in cComponentManager : starting single thread processing loop
(MSG) [2] in cComponentManager : Processing finished! System ran for 1460 ticks.
DONE!
# python diarize.py /vagrant/Yunitemp/test2.htk 
Traceback (most recent call last):
  File "diarize.py", line 14, in <module>
    net.load_state_dict(torch.load('model.pt'))
  File "/home/vagrant/anaconda/lib/python2.7/site-packages/torch/serialization.py", line 267, in load
    return _load(f, map_location, pickle_module)
  File "/home/vagrant/anaconda/lib/python2.7/site-packages/torch/serialization.py", line 420, in _load
    result = unpickler.load()
  File "/home/vagrant/anaconda/lib/python2.7/site-packages/torch/serialization.py", line 389, in persistent_load
    data_type(size), location)
  File "/home/vagrant/anaconda/lib/python2.7/site-packages/torch/serialization.py", line 87, in default_restore_location
    result = fn(storage, location)
  File "/home/vagrant/anaconda/lib/python2.7/site-packages/torch/serialization.py", line 69, in _cuda_deserialize
    return obj.cuda(device)
  File "/home/vagrant/anaconda/lib/python2.7/site-packages/torch/_utils.py", line 61, in _cuda
    with torch.cuda.device(device):
  File "/home/vagrant/anaconda/lib/python2.7/site-packages/torch/cuda/__init__.py", line 207, in __enter__
    self.prev_idx = torch._C._cuda_getDevice()
AttributeError: 'module' object has no attribute '_cuda_getDevice'
vagrant@vagrant-ubuntu-trusty-64:~/Yunitator$ 
```

* add preliminary run script `runYunitator.sh`
* run script first needs to produce HTK format features using OpenSmile - use the same config as OpenSAT: `/vagrant/MED_2s_100ms_htk.conf`
* add `extract-htk-vm2.sh` to do this
* Need to install also pytorch in the VM, with: `conda install cudatoolkit
conda install pytorch-cpu -c pytorch`

