# Phylogenetic Tree Comparing Metrics

## RF Distance

The **Robinson-Foulds (RF) distance** is a widely used metric for quantifying the dissimilarity between two phylogenetic trees. Here's a structured breakdown:

**Related Concepts**

1. **Splits (Unrooted Trees)**:
   - An unrooted tree's edges define **splits** (bipartitions) of the leaf set. For example, an edge splits the leaves into two disjoint subsets.
   - The RF distance compares the splits of two unrooted trees.

2. **Clusters (Rooted Trees)**:
   - In rooted trees, internal nodes define **clusters**, which are subsets of leaves descended from that node.
   - The RF distance compares the clusters of two rooted trees.

**Calculation**

- For two trees $T_1$ and $T_2$, compute the sets of splits/clusters $S_1$ (for $T_1$) and $S_2$ (for $T_2$).
- The RF distance is the number of elements in the symmetric difference:  
    $$
    \text{RF}(T_1, T_2) = |S_1 \setminus S_2| + |S_2 \setminus S_1|
    $$


Our package `astraea` support calculating Robinson-Foulds distance (RF distance) to compare the similarity of two trees (only for unrooted way, but also work for rooted tree):

```python
import astraea.phylo
import astraea.phylo.metric

tree1 = astraea.phylo.RootedTree()
tree1.load_newick("data/PF00042_NJ.nwk")

tree2 = astraea.phylo.RootedTree()
tree2.load_newick("data/PF00042.nwk")

rf_distance = astraea.phylo.metric.robinson_foulds_distance(tree1, tree2)
print("Robinson-Foulds distance: %d" % rf_distance)
```


