```dot
digraph graphname {
    node [ fontname = "Cambria" shape = "rect" fontsize = 12]
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

