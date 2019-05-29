---
title: Práctica 6 - News Stream
layout: practice
permalink: /practice/news
---

# Práctica 6: NewsStream

Implementar diferentes ResourceProviders. 
Como implementación requerida habrá que implementar un `ResourceProvider` para La Nación y otro para Clarín, obteniendo los artículos del home como `Resources`.

```
interface Resource {
	defaul String id() { return this.link(); }
	String link();
	String label();
}
```

```
interface ResourceProvider {
	Iterable<Resource> resources();
	Duration interval();
}
```

Implementar un ResourceStream que reciba un ResourceProvider vía constructor y se configure con un tick de intervalo específico.

```
class ResourceStream extends Observable<ResourceChange> {
	ResourceStream(ResourceProvider provider) {
		// ...
	}
	// ...
}
```

Este stream deberá manejar internamente el estado de los recursos del provider y emitir ResourceChanges por cada resource que se agregue, se modifique o se borre.

```
interface ResourceChange {
	Resource resource();
	ChangeType type();
}
```

```
enum ChangeType {
	ADD, REMOVE, MODIFY
}
```

Implementar un NewsStream que extienda de Observable<ResourceChange> y combine todas las instancias de ResourceStream que se creen por cada provider configurado en un Multibinder<ResourceProvider>.
	
```
public class NewsStream extends Observable<ResourceChange> {
    @Inject public NewsStream(@NotNull Set<NewsPaperProvider> providers) {
        // ...
    }
    // ...    
}
```    

![Merge Streams](../4-behaviour/merge.png)
