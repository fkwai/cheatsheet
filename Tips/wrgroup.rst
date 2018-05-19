Water Resource Group
====================

This document will list tips for WRgroup

Computers
---------
- Linux Server, 128.118.212.69
- Small Linux, 130.203.207.218
- Windows Work Station, 130.203.207.223
- My Computer, 130.203.208.181

Access tips
-----------

tight VNC
~~~~~~~~~

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

Memory Manage
~~~~~~~~~~~~~

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

.. _tightVNC tutorial: https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-vnc-on-ubuntu-16-04
.. _cgroup tutorial: http://www.fernandoalmeida.net/blog/how-to-limit-cpu-and-memory-usage-with-cgroups-on-debian-ubuntu/
