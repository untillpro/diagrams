```dot
graph graphname {

    graph[rankdir=TB splines=ortho]
    node [ fontname = "Cambria" shape = "record" fontsize = 12]
    edge [dir=both arrowhead=none arrowtail=none]
    Networks[label="Social Networks" style=dashed]

    Family -- Mother
    Family -- Father
    Family -- Pet [arrowhead=odot]
    Family -- Child [arrowhead=crowodot]
    Father -- Hobby [arrowhead=crow]
    Hobby -- Foto[arrowtail=empty]
    Hobby -- Fishing[arrowtail=empty]
    Mother -- Networks
    Networks -- vk
    vk -- ok

}
```

- Family has exactly one Father and Mother
- Family has zero or one Pet
- Father has one or few hobbies
- Hobby can be `Foto` or `Fishing` 
  - `Foto` and `Fishing` are subclasses of `Hobby` class
- Family has zero or few kids
- Mother is a member of `vk` and `ok` social networks
- `vk`, `ok` - ordered items of `Social Networks` list

# Links 

- http://blog.konca.com/2013/08/25/draws-uml-class-diagram-with-graphviz/