mockito-without-hardcoded-distribute-version
============================================


The mockito people thought it was a good idea to use a distribute bootstrapping script that downloads
distribute-0.6.10.tar.gz from PyPI and then tries to use that for the setup.

_They were wrong._


Mockito is unusable on python3 because of this and pip installs will fail with 
```
error: invalid command 'bdist_egg'
```

There is a pull request pending at bitbucket (yes the sources are on bitbucket, not on code.google.com like the metadata on PyPI pretends) but there's been no activity up until now.

https://bitbucket.org/szczepiq/mockito-python/pull-request/2/dont-download-distribute/diff


You can use this project (which is on PyPI) until the pull request is merged.
Just replace

```
pip install mockito
```

with

```
pip install mockito-without-hardcoded-distribute-version
```

You don't need to change anything else. This will work on python 2 and 3.
