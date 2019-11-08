```dot
digraph graphname {
    node [ fontname = "Cambria" shape = "record" fontsize = 12]
    compound=true

    subgraph cluster_router_out {
        label = "Router"
        Routing
        RouterOutput
	}    
    subgraph cluster_app {
        label = "App";
        subgraph cluster_ph{
            label = "PartitionHandler"
            Cache
            Validator
            Blogger
            Writer
        }
    }
    subgraph cluster_router_in {
        label = "Router"
        RouterInput
    }

    Cassandra

    Client -> Traefik
    Traefik -> Routing
    Routing -> RouterOutput

    RouterOutput-> Cache
    Cache -> Validator
    Validator -> Blogger
    Blogger -> Writer
    Writer -> RouterInput
    Cassandra -> Writer  [style=dotted dir=none lhead=cluster_ph]
}
```

# Graphviz Links

- http://www.graphviz.org/documentation/
  - https://graphviz.gitlab.io/_pages/doc/info/shapes.html
  - https://graphviz.gitlab.io/_pages/doc/info/arrows.html
- `Cluster`: https://graphviz.gitlab.io/_pages/Gallery/directed/cluster.html
- http://www.graphviz.org/doc/info/attrs.html
- http://www.graphviz.org/gallery/