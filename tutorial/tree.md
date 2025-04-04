# Phylogenetic Tree

## Overview

We are using `astraea.phylo` to plot phylogenetic tree. 

This function is similar to commonly used tree visualizing tools including [iTOL](https://itol.embl.de/), [FigTree](http://tree.bio.ed.ac.uk/software/figtree/) and [ggtree](https://bioconductor.org/packages/release/bioc/html/ggtree.html). But there is no comprehensive tool for tree and annotation visualization using Python and `matplotlib`.

## Plot a circular tree

Example of a circular tree:

![fig_circular_tree](https://www.researchgate.net/profile/Daniel-Janies/publication/51099854/figure/fig1/AS:305755552010240@1449909212118/Circular-phylogenetic-tree-at-level-of-genus-The-tree-was-generated-with-RAxML-and.png)


First, you need to have a precomputed tree as newick format `.nwk`

- What is newick file? [link](https://en.wikipedia.org/wiki/Newick_format)

Tools which can produce newick tree from multiple sequence alignment (MSA):

- FastTree
- IQTree

Then, you need to load the tree with following code:

```python
# import astraea phylo
import astraea.phylo
import astraea.phylo.figure

# LOAD TREE
tree = astraea.phylo.RootedTree()
tree.load_newick("data/[YOUR_TREE].nwk")
print("Number of nodes: %d" % len(tree.node_list))
```

Finally, plot the tree using [`plot_circular_tree`](../phylo/plot_circular_tree.md) function:

```python
# PLOT TREE
astraea.phylo.figure.plot_circular_tree(tree)
```

PS. currently, add annotation is not supported using `plot_circular_tree`.


