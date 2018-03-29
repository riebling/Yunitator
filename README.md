# Yunitator
Diarization of child / adult speech using a Pytorch classifier

Run script is `runYunitator.sh` which takes a .wav file as input
and produces in the temp/working folder `/vagrant/Yunitemp/` a RTTM
file with matching base name. For example:
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

vagrant@vagrant-ubuntu-trusty-64:~/Yunitator$ cat /vagrant/Yunitemp/test2.rttm
SPEAKER	test	1	0.0	0.2	<NA>	<NA>	SIL	<NA>	<NA>
SPEAKER	test	1	1.9	1.6	<NA>	<NA>	SIL	<NA>	<NA>
SPEAKER	test	1	0.2	1.7	<NA>	<NA>	CHI	<NA>	<NA>
```


