---
title: Práctica 4 - REPL
layout: practice
permalink: /practice/repl-1
---

# Práctica 4: REPL Console (I)

1- Implementar las interfaces declaradas en el paquete ‘daoo.repl’.

2- Implementar el loop de REPL. Lograr un comportamiento similar a:

```java
public static void main(String[] args) {
        final Environment e = new EnvironmentImpl();
        e.addOperandFactory(new DoubleOperandFactory());
        e.addOperandFactory(new LiteralOperandFactory());
        e.addCommandFactory(new BinaryArithmeticCommandFactory());
        e.addCommandFactory(new LengthCommandFactory());
        
        final Repl repl = new ReplImpl(e);
        repl.loop(System.in, System.out);
}
```

Console:

```
10
> 10.0
20
> 20.0
+
> 30.0
"daoo"
> "daoo"
length
> 4.0
*
> 120.0
```

3- Implementar directivas de consola para soportar undo y redo. Lograr un comportamiento similar a:

```
10
> 10.0
2
> 2.0
*
> 20.0
:undo
> 2.0
:redo
> 20.0
```

- [DAOO Repl](../3-structural/daoo-repl.jar)
- [DAOO Repl Sources](../3-structural/daoo-repl-src.jar)
