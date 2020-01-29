```dot
digraph graphname {
    node [ fontname = "Cambria" shape = "rect" fontsize = 12]
    compound=true

    subgraph cluster_router {
        label = "Router"
        Routing
    }
    subgraph cluster_app {
        label = "App";
        Validator
    }

    Cassandra[shape=cylinder]
    Writer[shape=parallelogram]
    End[style=rounded]

    Client -> Routing
    Routing -> Validator [label="Line between clusters" ltail=cluster_router lhead=cluster_app]
    Validator -> End

    Cassandra -> Writer [label="Dotted line" style=dotted dir=none]
    Cassandra -> Reader [label="Dashed line" style=dashed dir=none]    
}
```

# Links

- https://stackoverflow.com/questions/7115870/creating-straight-edges-in-graphviz