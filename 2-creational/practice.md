---
title: Práctica 1 - Factories, Builders & Fluent Interfaces
layout: practice
permalink: /practice/creational
---

# Práctica 1: Factories, Builders & Fluent Interfaces

1. Utilizando una combinación de estos, el trabajo práctico consiste en programar un builder para queries sql.

**Ejemplo para la composición de un equipo de fútbol**

Teniendo Team, TeamBuilder, Player, PlayerBuilder y un BuilderFactory (con sus members importados estáticamente), el objetivo sería lograr algo similar a:

```
public class Main {
    public static void main(String[] args) {
        final Team team = team("Boca Juniors")
                            .add(player("Agustín Orión").shirt(1))
                            .add(player("Juan R. Riquelme").shirt(10).captain())
                            .add(player("Nicolás Blandi").shirt(25))
                            .add(coach("Carlos Bianchi"))
                            .stadium("Alberto J. Armando", "Bombonera")
                          .build();

        System.out.println("Main.main team = " + team);
    }
}
```
