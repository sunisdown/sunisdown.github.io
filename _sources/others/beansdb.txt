GoBeansDB
=========

Why
---

CArray

.. code:: go

    type CArray struct {
        Body []byte
        Addr uintptr
        Cap  int
    }

| A: 这里数据结构是重复的，为什么这么做？
| Q: 用C来管理内存，减少 GC 压力

.. code:: go

    // HStore

    type HStore struct {
        buckets   []*Bucket
        gcMgr     *GCMgr
        htree     *HTree
        htreeLock sync.Mutex
    }

.. code:: go

    // HTree
    type HTree struct {
        sync.Mutex

        /*
         *            Root of hstore.tree
         *               /  | ... \
         *              /   |      \
         * depth -->  ht1  ht2     htN     # root of bucket trees (also are the leafs of hstore tree)
         *             ^
         *             |
         *            pos
         *
         * #bucket (number of buckets) = 16 ^ bucket_tree.depth
         */

        // depth is level (0-based) of root Node (of this htree) in hstore.tree
        depth int

        // bucketID is position (offset) of this htree in the list of htrees at same level.
        bucketID int

        /* runtime */

        // level[0][0] is root of a htree,
        // levels[i] is a list of nodes at same level `i` of htree,
        // Node stores the summary info of its childs.
        // Height of htree = len(levels)
        levels [][]Node

        // leafs is the place to store key related info (e.g. keyhash, version, vhash etc.)
        leafs []SliceHeader

        // tmp, to avoid alloc
        ni NodeInfo
    }

.. code:: go


    type Node struct {
        // count is the number of keys (with version > 0) under this node.
        count uint32

        // hash is the summary of it's child nodes.
        hash uint16

        // isHashUpdated is true iff the hash value of node is updated.
        isHashUpdated bool
    }

    type NodeInfo struct {
        node   *Node
        level  int
        offset int
        path   []int
    }

NOTE
-----

htree.go::getLeafAndInvalidNodes // 看起来没有返回数据，但是更新了tree
的 ni
