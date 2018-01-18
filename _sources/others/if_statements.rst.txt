IF 语句
======================

如何写好代码是永不过时的话题，if 作为代码中不可缺少的部分，也是将代码写优雅必须要掌握的。

在写 if 语句的时候，通常遵循一下原则：

* 首先写常见的情况，在处理补常见的。
  常见情况的代码清晰，代码可读性要高

* 确保等量分支正确
  类似 > >= 混用的情况

* 正常的情况放在 if 的后面，异常情况放在 else 后面。

.. code:: go

          if ifSuccess {
          // do something
          } else {
          // do something
          }


* if 子句后面应该有意义

.. code:: go

          if Success {
          } else {
          // do something
          }

上面例子里面，if 的子句里面没有任何逻辑，这种代码看起来有点怪，可以修改成

.. code:: go

          if !Success {
          // do something
          }

* 考虑 else 子句

上面的例子里面只写了 if 语句，后面并没有跟 else，这种情况下需要确认自己是否考虑周全，并且在注释里面说明为什么没有 else 语句
