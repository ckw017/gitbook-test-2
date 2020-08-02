# Reference

## Understanding the Skeleton Code

The `index` directory contains a partial implementation of an Alternative 2 B+ tree \(`BPlusTree`\), an implementation that you will complete in this project. Every B+ tree maps keys of type `DataBox` \(a single value or "cell" in a table\) to values of type `RecordId`. A B+ tree is composed of inner nodes \(`InnerNode`\) and leaf nodes \(`LeafNode`\). Every B+ tree is persisted to disk \(through the Buffer Manager and Disk Space Manager\), and every inner node and leaf node is stored on its own page. Calls are done through `BPlusTree`, which propagate through zero or more `InnerNode`s, and eventually terminate at a `LeafNode`.

Both `LeafNode` and `InnerNode` inherit from `BPlusNode`, which has some useful methods implemented already.

You should read through all of the code in the `index` directory. Many comments contain critical information on how you must implement certain functions. For example, `BPlusNode::put` specifies how to redistribute entries after a split. You are responsible for reading these comments. If you do not obey the comments, you will lose points. Here are a few of the most notable points:

* Our implementation of B+ trees does not support duplicate keys. You will

  throw an exception whenever a duplicate key is inserted.

* Our implementation of B+ trees assumes that inner nodes and leaf nodes

  can be serialized on a single page. You do not have to support nodes that

  span multiple pages.

* Our implementation of delete does not rebalance the tree. Thus, the

  invariant that all non-root leaf nodes in a B+ tree of order `d` contain

  between `d` and `2d` entries is broken. Note that actual B+ trees **do rebalance**

  after deletion, but we will **not** be implementing rebalancing trees in this project

  for the sake of simplicity.

#### LockContext objects

There are a couple of points in this project, where a method will take in objects of the type `LockContext`. You do not need to worry too much about these objects right now; they will become more relevant in Project 4.

If there are any methods you wish to call that require these objects, use the ones passed in to the method you are implementing, or defined in the class of the method you are implementing \(`this.lockContext` for `BPlusTree` and `this.treeContext` for `InnerNode` and `LeafNode`\).

