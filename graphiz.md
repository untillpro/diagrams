# Graphviz Links

- http://www.graphviz.org/documentation/
  - https://graphviz.gitlab.io/_pages/doc/info/shapes.html
  - https://graphviz.gitlab.io/_pages/doc/info/arrows.html
- `Cluster`: https://graphviz.gitlab.io/_pages/Gallery/directed/cluster.html
- http://www.graphviz.org/doc/info/attrs.html
- http://www.graphviz.org/gallery/

# Problems

- Found problem https://gitlab.com/graphviz/graphviz/issues/1624
  - Removing node [ shape = "record"] fixes the problem
  - shape = "rect" fixes the problem

  
```dot
  digraph cluster {
    node [ shape = "rect"]

    subgraph cluster_dc1 {
        label = "dc1";
        cas1
        app1
    }
    subgraph cluster_dc2 {
        label = "dc2";
        cas2
        app2
    }
    app1 -> cas1
    app1 -> cas2
    app2 -> cas1
}
```
