Column Store
============

Row
---

row store

+-----+-----+-----+-----+
| 1   | 2   | 3   | 4   |
+=====+=====+=====+=====+
+-----+-----+-----+-----+

Column
------

::

    1         2       3        4
    +----+  +----+  +----+   +-----+
    |    |  |    |  |    |   |     |
    +----+  +----+  +----|   +-----+
    |    |  |    |  |    |   |     |
    |    |  |    |  |    |   |     |
    |    |  |    |  |    |   |     |
    |    |  |    |  |    |   |     |
    |    |  |    |  |    |   |     |
    |    |  |    |  |    |   |     |
    |    |  |    |  |    |   |     |
    +----+  +----+  +----+   +-----+

利用 CPU 缓存
-------------

vid value index


Could you describe your task more preciesly? Columns are determined by structure of your data (schema). ClickHouse engine try automatically choose optimal length of blocks inside own internal pipelines, but you can adjust it via max_block_size max_insert_block_size config parameters. 

Optimal values of these parameters is determined by particular task. The best strategy to choose them is to test performance of your use case on different parameters set.
