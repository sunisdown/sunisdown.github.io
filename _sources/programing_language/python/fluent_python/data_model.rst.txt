Python 的 Data Model
============================

龟爹的品味

用Python

如果你在用Python之前已经接触过别的面向对象的编程语言，你就会发现Python 中有一些奇怪的地方，比如用 ``len(collection)`` 替代了 ``collection.len()``。这个例子在 Python 中只是冰山一角，类似的写法就是 Python 的关键，我们讲它称为 `` Pythonic``。而这巨大的冰山就是 ``data model``，通过 ``data model`` 描述的 API，你可以自己的 object 与语言的特性完美的结合在一起。

你可以吧 data model 看成 Python 的一种描述，它来确定语言本身的实现。像 object，iterators，functions 等

当我们使用一个框架的时候，需要实现被框架调用的各种方法(method)，
j
