# Your Tasks

Before continuing make sure you've followed the instructions in the previous section to make to get the most recent version of the skeleton code and understand what can be modified.

## Overview

You should first implement the `fromBytes` in `LeafNode`. This method reads a `LeafNode` from a page. For information on how a leaf node is serialized, see `LeafNode::toBytes`. For an example on how to read a node from disk, see `InnerNode::fromBytes`. Once you have implemented `fromBytes`, you should be passing `testToAndFromBytes`.

After implementing `fromBytes`, you will need to implement the following methods in `LeafNode`, `InnerNode`, and `BPlusTree`:

* `get`
* `getLeftmostLeaf` \(`LeafNode` and `InnerNode` only\)
* `put`
* `remove`
* `bulkLoad`

For information on what these methods should do, refer to the comments in `BPlusTree` and `BPlusNode`. Do not forget to call `sync` when implementing the three mutating methods \(`put`, `remove`, and `bulkLoad`\); it's easy to forget.

Each of these methods, although split into three different classes, can be viewed as one recursive action each - the `BPlusTree` method starts the call, the `InnerNode` method is the recursive case, and the `LeafNode` method is the base case. It's suggested that you work on one method at a time \(over all three classes\).

You will also need to implement the following methods in `BPlusTree`:

* `scanAll`
* `scanGreaterEqual`

In order to implement these, you will have to complete the `BPlusTreeIterator` inner class in `BPlusTree.java`.

After this, you should pass all the Project 2 tests we have provided to you \(and any you add yourselves\). These are all the provided tests in `database.index.*`.

