# Phylogenetic Tree

## Plot a phylogenetic tree

We are using `astraea.phylo` to plot phylogenetic tree

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

Finally, plot the tree using [`plot_circular_tree`](../phylo/plot_circular_tree.md) function

```python
astraea.phylo.figure.plot_circular_tree(tree)
```

