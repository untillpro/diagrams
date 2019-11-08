```dot
digraph graphname {

    graph[rankdir=BT splines=ortho]
    node [ fontname = "Cambria" shape = "record" fontsize = 12]
    edge [dir=both arrowhead=none arrowtail=none]

    Mother -> Family
    Father -> Family
    Pet -> Family [arrowtail=odot]
    Child -> Family [arrowtail=crowodot]
    Hobby -> Father [arrowtail=crow]
}
```

- Family has exactly one Father and Mother
- Family has zero or one Pet
- Father has many hobbies
- Family has zero or few kids

# Links 

- http://blog.konca.com/2013/08/25/draws-uml-class-diagram-with-graphviz/