# pydbgpproxy

This is [DBGp](https://xdebug.org/docs/dbgp)-compatible proxy (like [dbgpProxy](https://xdebug.org/docs/dbgpProxy))
that can be used to allow multi-user debugging. This fork adds `-p|--ide-key-port` option to select IDE talk-back port
from IDE key instead of picking it randomly, which solves SSH tunneling issues.

## Install

* cd /opt
* wget https://github.com/eduard-sukharev/pydbgpproxy-idekey-port/archive/master.zip ./
* unzip master.zip -d
* mv pydbgpproxy-idekey-port-master pydbgpproxy
* ln -s $(pwd)/pydbgpproxy /usr/local/bin/pydbgpproxy

## Troubleshooting

If you encounter following error:

```
Traceback (most recent call last):
  File "/usr/local/bin/pydbgpproxy", line 106, in <module>
    import dbgp.serverBase
ImportError: No module named dbgp.serverBase
```

then append `pythonlib` dir to your `PYTHONPATH` env variable:  

``` sh
echo "export PYTHONPATH=\${PYTHONPATH}:${PWD}/pydbgpproxy/pythonlib" >> ~/.bashrc
```
