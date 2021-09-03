---
title: Asynchrone Daten in Komponenten?
description: Asynchrone Daten in NuxtJS-Komponenten?
---

Da Komponenten keine `asyncData` Methode haben, können Sie die asynchrone Datenserverseite nicht direkt innerhalb einer Komponente abrufen. Um diese Einschränkung zu umgehen, haben Sie zwei grundlegende Möglichkeiten:

1. Führen Sie den API-Aufruf im `mounted` Hook aus und legen Sie die Dateneigenschaften beim Laden fest. *Nachteil: Funktioniert nicht für serverseitiges Rendering.*
2. `asyncData` Sie den API-Aufruf in den asyncData- oder `fetch` Methoden der Seitenkomponente durch und übergeben Sie die Daten als Requisiten an die Unterkomponenten. Das Server-Rendering funktioniert einwandfrei. *Nachteil: Die `asyncData` oder der `fetch` der Seite sind möglicherweise weniger lesbar, da die Daten für andere Komponenten* geladen werden.
