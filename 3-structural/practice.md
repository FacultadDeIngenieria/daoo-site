---
title: Práctica 2 - Factories, Builders & Fluent Interfaces
layout: practice
permalink: /practice/normalization
---

# Práctica 2: Factories, Builders & Fluent Interfaces (Normalization)

1. Rediseñar el trabajo anterior acorde a las nuevas interfaces provistas.

- [DAOO Sql](../3-structural/daoo-sql.jar)
- [DAOO Sql Sources](../3-structural/daoo-sql-src.jar)

**Ejemplo de uso**
```
...
import static daoo.query.impl.QueryBuilder.query;
import static daoo.query.impl.TableFactory.*;

public class Main {
    public static void main(String[] args) {
        final Table t = table("student");
        final StrColumn lastName = t.col(string("lastName"));
        final StrColumn fistName = t.col(string("firstName"));
        final IntColumn age = t.col(integer("age"));

        final Query q = query()
                .select(age, fistName)
                .from(t)
                .where(lastName.startsWith("Lopez")
                        .and(age.between(18, 21))
                        .and(age.lt(fistName.length())))
                .orderBy(age)
                .groupBy(lastName)
                .build();
    }
}                
```                
