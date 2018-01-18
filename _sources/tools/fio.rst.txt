*****
fio
*****

磁盘测试工具，可以拿来测试磁盘的随机读写性能。地址 fio_

里面有很多参数可以调整，可以通过命令行参数的形式来启动，也可以指定一个配置文件。


随机读
_____________

比如我想测硬盘的随机读的性能, 可以用下面的配置 ``random-read-test.fio``

.. code:: bash

    [random-read]
    rw=randread
    size=4G
    directory=/data1/readtest
    iodepth=16
    bs=500B
    thread
    runtime=60
    numjobs=16
    rate_iops=22



然后执行:

.. code:: bash

    fio ./random-read-test.fio


.. _fio: https://github.com/axboe/fio/blob/master/HOWTO
