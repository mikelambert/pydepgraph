pydepgraph - A dependencies analyzer for Python
===============================================


Introduction
------------

pydepgraph is a stand-alone program that analyzes one or more tree of
Python sources to find dependencies amongst the files, and output a
DOT file, suitable to be displayed or converted to an image.


Usage
-----

From the command line help.

```
usage: pydepgraph [-h] [-p PATH] [-e EXCLUDE] [-c CLUSTERS] [-r] [-g GRAPH]

Draw the dependency graph of a Python project.

optional arguments:
  -h, --help            show this help message and exit
  -p PATH, --path PATH  comma separated list of paths to include
  -e EXCLUDE, --exclude EXCLUDE
                        comma separated list of paths to exclude
  -c CLUSTERS, --clusters CLUSTERS
                        comma separated list of clusters
  -r, --no-recursive    do not descend into subdirectories
  -g GRAPH, --graph GRAPH
                        type of graph: 0 (without clusters), 1 (with
                        clusters), 2 (only clusters), 3 (only clusters,
                        drawing also self edges
```

It is important to notice that the paths specified with the -p switch
must be the root of the source tree, in order to let pydepgraph
recognize correctly the dependencies. For example, if you want that
the instruction

```python
import tornado.ioloop
```

is correctly assessed as an edge to tornado/ioloop.py, you need to
specify the parent directory of tornado (i.e., the grandparent of
ioloop.py) in the path list. In future versions this limitation could
be removed to allow sub-project inspections.


References
----------

A small tutorial can be found at [1].

[1] http://poisson.phc.unipi.it/~maggiolo/index.php/2012/02/pydepgraph-a-dependencies-analyzer-for-python/
