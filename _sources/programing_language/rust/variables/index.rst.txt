************
Rust 变量
************


.. code:: rust

   fn main() {
       let x: i32 = 20;
       println!(x);
   }


用 let 来声明一个变量，可以显示的声明类型，也可以不直接初始化声明类型，但是需要注意的是，声明类型之后，必须要显式的初始化这个变量。
比如这么做是错的

.. code:: rust

   let x: i32
   println!(x)

错在没有初始化变量


还有一点需要注意，Rust 里面变量是 `immutable` 的，如果想要赋一个新的值，就需要先把这个变量显示的声明为可变的，如下：

.. code:: rust

   let mut x = 2;
   println!(x)
   x=5;
   println!(x)

