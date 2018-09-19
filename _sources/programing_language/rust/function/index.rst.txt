************
Rust 函数
************


Rust 函数的默认返回值有点诡异

.. code:: rust
   fn foo(bar: i32) -> i32 {
      if bar > 10 {
          bar - 10
      } else {
          bar -3
      }
   }

还有一个需要注意的是 `expressions` 和 `statements` 的区别，
expressions 会有返回值， stattements 不会。

