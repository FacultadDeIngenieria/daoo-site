---
title: Práctica 5 - REPL II
layout: practice
permalink: /practice/repl-2
---

# Práctica 4: Repl Console (II)

1- Agregar soporte para declaración de variables (soportar undo).

Console:

```
a = 5
>
a
> 5.0
a
> 5.0
*
> 25.0
```

2- Agregar soporte para declaración de funciones (undo optional).

Console:

```
f(x) = x x +
>
5
> 5.0
f
> 10.0
f
> 20.0
```

```
f(x) = x
>
5
> 5.0
f
> 5.0
f
> 5.0
```

```
f(x,y) = x x y +
>
5
> 5.0
4
> 4.0
f
> 9.0
f
[oops...]
```

NOTA: usar immutable stack
