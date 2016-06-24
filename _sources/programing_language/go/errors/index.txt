************
Go 错误处理
************

通常情况下，我们都是这么来处理 Go 里面返回的错误：

.. code:: go

          if err != nil {
              return err
          }

这么写起来稍微有点麻烦，可以用下面两种方法来做：

.. code:: go

    func example1() {
        var (
            o   = Object{}
            err error
        )

        if err = o.Do1(1); err != nil {
            log.Fatal("ERROR 1", err)
        }

        if err = o.Do2(2); err != nil {
            log.Fatal("ERROR 2", err)
        }

        if err = o.Do3(3); err != nil {
            log.Fatal("ERROR 3", err)
        }

        log.Println("Ok")
    }


或者:

.. code:: go

    func must(err error) {
        if err != nil {
            log.Fatal(err)
        }
    }

    func example2() {
        o := Object{}

        must(o.Do1(1))
        must(o.Do2(2))
        must(o.Do3(3))

        log.Println("Ok")
    }


参考：errors-are-values_

.. _errors-are-values: https://blog.golang.org/errors-are-values
