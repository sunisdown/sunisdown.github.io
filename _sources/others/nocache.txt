Minimize Filesystem Caching Effects
===================================

有的时候需要判断某一个文件被 ``Linux``
缓存了多少。\ `nocache <https://github.com/Feh/nocache>`__
是一个非常不错的工具。足够小巧，无痛安装。

Install
-------

.. code:: bash

    git clone https://github.com/Feh/nocache.git

    cd nocache

    make

这样 ``nocache`` 目录下就有相应的可执行文件。\ ``cachestats``
可以插件一个文件被缓存了多少

Example
-------

.. code:: bash

    ./cachestats /test/275.000.idx.hash

    pages in cache: 0/53443 (0.0%)  [filesize=213771.4K, pagesize=4K]

结果显示没有文件被缓存了\ ``0%``
