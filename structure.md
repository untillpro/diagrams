```dot
digraph graphname {

    graph[rankdir=TB splines=ortho]
    node [ fontname = "Cambria" shape = "record" fontsize = 12]
    edge [dir=both arrowhead=none arrowtail=none]
    Family -> Mother
    Family -> Father
    Family -> Pet [arrowhead=odot]
    Family -> Child [arrowhead=crowodot]
    Father -> Hobby [arrowhead=crow]
}
```

- Family has exactly one Father and Mother
- Family has zero or one Pet
- Father has many hobbies
- Family has zero or few kids

# Links 

- http://blog.konca.com/2013/08/25/draws-uml-class-diagram-with-graphviz/