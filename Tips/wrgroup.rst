Water Resource Group
====================

This document will list tips for WRgroup

Computers
---------
- Linux Server, 128.118.212.69
- Small Linux, 130.203.207.218
- Windows Work Station, 130.203.207.223
- My Computer, 130.203.208.181

tight VNC
---------

`tightVNC tutorial`_ to setup

Start local VNC::

    # small Linux
    ssh -L 5901:127.0.0.1:5901 -N -f -l kxf227 130.203.207.218
    # Linux Server
    ssh -L 5902:127.0.0.1:5902 -N -f -l kxf227 128.118.212.69

Restart local VNC::

    netstat -ntlp
    kill -9 PID

Restart server VNC::

    vncserver -kill :1
    vncserver :1
    sudo systemctl daemon-reload
    sudo systemctl enable vncserver@1.service
    sudo systemctl start vncserver@1

hack to fix VScode / Atom display::

    mkdir ~/lib
    cp /usr/lib/x86_64-linux-gnu/libxcb.so.1 ~/lib
    cp /usr/lib/x86_64-linux-gnu/libxcb.so.1.1.0 ~/lib
    sed -i 's/BIG-REQUESTS/_IG-REQUESTS/' /usr/lib/x86_64-linux-gnu/libxcb.so.1.1.0


Memory Manage
-------------

1. cgroup 可以限制用户的内存. Steps:

- 更改::

    /etc/cgconfig.conf  #内存大小
    /etc/cgrules.conf  #限制用户

- 执行下面的命令::

    cgconfigparser -l /etc/cgconfig.conf
    cgrulesengd

- `cgroup tutorial`_

2. 更改 /etc/security/limits.conf 然后重启
这个我没太搞明白。但应该是限制单个process的。


Mount Drives
------------

- find uuid::

    sudo blkid

- modify /etc/fstab

    just follow this example::

        UUID=b4aefb54-e1c7-4378-9380-13eea35ad943   /mnt/sdc/   ext4    defaults    2   2

- restart or mount -a


CUDA
----

Add path::

	export PATH=/usr/local/cuda-8.0/bin${PATH:+:${PATH}}
	export LD_LIBRARY_PATH=/usr/local/cuda-8.0/lib64\ $LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}



.. _tightVNC tutorial: https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-vnc-on-ubuntu-16-04
.. _cgroup tutorial: http://www.fernandoalmeida.net/blog/how-to-limit-cpu-and-memory-usage-with-cgroups-on-debian-ubuntu/


Jupyter Notebook
----------------

Remote notebook:

- terminal 1::

    ssh kxf227@130.203.207.218
    jupyter notebook --no-browser --port=8889

- terminal 2::

    ssh -N -L localhost:8888:localhost:8889 kxf227@130.203.207.218

- browser::

    localhost:8888