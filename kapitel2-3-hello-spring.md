---
title: Spring Boot Hello World
description: Spring Boot Hello World
permalink: spring-boot-hello-world
vgwort: <img src="http://vg08.met.vgwort.de/na/4f06ad5ac496480e836f6aa4d2426618" width="1" height="1" alt=">
lang: de
---

# Spring Boot Hello World

Das Spring-Universum ist riesig und es gibt verschiedene Arten von Spring Boot-Anwendungen: Kommandozeilenanwendungen, Batch Programme, Web Flux-Anwendungen und MVC-Anwendungen um einige zu nennen. Durch das Hinzufügen der Starter-Abhängigkeit *spring-boot-starter-web* im letzten Kapitel haben wir uns für eine MVC-Anwendung basierend auf der Servlet-API entschieden. Das ist vermutlich die populärste Form der Spring-Anwendung, weshalb sie hier auch im Vordergrund steht.

## MVC

*MVC* steht für *Model-View-Controller* und ist ein bekanntes Muster zur Unterteilung der Software in die namensgebenden Komponenten, also Daten, Darstellung und Logik. Der Web Request wird dabei an einen Frontcontroller (in Spring das *Dispatcher Servlet*) geleitet und von dort mithilfe einer Mapping-Tabelle an spezialisierte Request Controller geroutet. Der Controller lädt oder erzeugt ein passendes Model (beispielsweise die anzuzeigenden Daten). Dieses Model reicht er entweder zur Darstellung eine HTML View weiter (das ist dann eine klassische Webanwendung) oder er schreibt die Daten - zum Beispiel in Form von JSON - direkt in die Response wo sie dann von Clientanwendungen wie zum Beispiel einer App ausgewertet werden. Wenn im letzteren Fall bestimmte Konventionen eingehalten werden, spricht man von einer REST-Anwendung.

Das Dispatcher Servlet ist bereits aktiv, sonst hätte man die Fehlermeldung im letzten Kapitel nicht gesehen. Was zur Anzeige einer Seite fehlt, ist zunächst ein spezialisierter Controller, der sich für eingehende Requests unter einer bestimmten URL zuständig fühlt. 

## Controller

Zu diesem Zweck wird eine neue Java-Klasse `CRMController` angelegt (`File > New > Class`). Die Klasse erhält die Annotation `@RestController`, was sie für Spring als Rest Controller, also einen Controller, der die Daten ohne View weitergibt, kennzeichnet. 

```java
import org.springframework.web.bind.annotation.RestController;

@RestController
public class CRMController {

}
```

Das alleine genügt noch nicht, es fehlt noch der Eintrag für die Routing-Tabelle. Dieser wird in Form der folgenden Methode zugefügt:

```java
@GetMapping("/")
public String home() throws IOException {
	return "Hello World";
}
```

Die Annotation `@GetMapping("/")`legt fest, dass GET-Requests auf Root von der darauf folgenden Methode (hier also home()) behandelt werden. Der Name der Methode darf frei vergeben werden. 

Ein Aufruf von http://localhost:8080 nach dem Restart der Anwendung führt nun zur Ausgabe des **Spring Boot Hello World**.
