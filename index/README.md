---
description: 'Due: Friday, 2/21/2020, 11:59 PM'
---

# Project 2: B+ Trees

## Prerequisites

In this project you will be implementing B+ tree indices. You should watch the B+ Trees lectures before working on this project. We also recommend reviewing the B+ Trees note here.

## Getting Started

**It is essential that you run `git pull` in the `/cs186/sp20-moocbase` directory before starting work on this project to get the most recent updates.**

The project files you'll be making changes to are all located in `src/main/java/edu/berkeley/cs186/database/index`. See the section "Submitting the Assignment" for a full list of the files we'll be grading you on. The test cases for this project are all located in`src/test/java/edu/berkeley/cs186/database/index`. To build and test your code in the container, run the following inside `/cs186/sp20-moocbase`:

```bash
git pull origin master
mvn clean test -D proj=2
```

There should be 16 failures, 4 errors, and 20 tests run.

### Modifying the Skeleton Code

For testing purposes you may **not** modify the signature of any methods or classes that we provide to you, but you're free to add helper methods.

You should make sure that all code you modify belongs to files with `TODO(proj2)` comments in them \(e.g. don't add helper methods to `DataBox`\). A full list of files that you may modify follows:

* `index/BPlusTree.java`
* `index/InnerNode.java`
* `index/LeafNode.java`

Make sure that your code does _not_ use any static \(non-final\) variables - this may cause odd behavior when running with maven vs. in your IDE \(tests run through the IDE often run with a new instance of Java for each test, so the static variables get reset, but multiple tests per Java instance may be run when using maven, where static variables _do not_ get reset\).

