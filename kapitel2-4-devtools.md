---
title: Spring Developer Tools
description: Praktische Werkzeuge für den Entwickler
permalink: spring-developer-tools
vgwort:
lang: de
---

# Spring Developer Tools

Bisher war für jede Codeänderung ein Neustart der Anwendung erforderlich. Spring Boot bzw. der Embedded Tomcat startet zwar glücklicherweise sehr flott, dennoch geht es noch schneller. Pivotal bietet einen Satz von Hilfswerkzeugen an, mit denen sich die Spring Boot-Entwicklung noch weiter tunen lässt, die **Spring Developer Tools**. Sie werden dem aktuellen Projekt als Dependency *devtools* zugefügt, entweder über das Kontextmenü vom pom.xml (Spring > Edit Starters) oder direkt durch das Zufügen von folgender Dependency im pom:

```java
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-devtools</artifactId>
	<optional>true</optional>
</dependency>
```

## Automatic Restart
Die DevTools enthalten mehrere Werkzeuge. Das wohl hilfreichste ist ein Feature namens *Automatic Restart*, das dazu führt, dass bei bestimmten Triggern (bei Eclipse bzw. STS das Speichern des Codes) die Anwendung automatisch neu gestartet wird. Allerdings gilt das nur für "echten Code" des aktuellen Projekts und nicht die zugefügten Dependencies. Spring arbeitet hier mit zwei separaten Class Loadern und aus Performancegründen wird nur der Loader für den aktuellen Projektcode neu gestartet. Deshalb muss die Anwendung nach dem Zufügen der DevTools noch mal von Hand neu gestartet werden. Danach restartet Tomcat bei Codeänderungen dann automatisch. Man kann das ausprobieren, indem man beispielsweise ein Leerzeichen irgendwo in den Code einfügt, speichert und dabei die Ausgaben in der Konsole im Auge behält. 

## LiveReload
Ein weiteres interessantes Werkzeug der Developer Tools ist *LiveReload*. Nach dem Einbinden einer Browser-Eerweiterung die man unter [^1] erhält, werden geänderte Webseiten automatisch aktualisiert. Das ständige Klicken auf Reload entfällt also.

## Deaktivieren von Templates
Im weiteren Verlauf des Buchs wird viel mit Thymeleaf-Templates gearbeitet. Templates zur Darstellung von Webseiten werden normalerweise gecacht, damit sie für den Besucher schnell verfügbar sind. Das Cachen stört allerdings bei der Entwicklung, weil Änderungen nicht sofort sichtbar sind. Auch hier helfen die DevTools, sie deaktivieren den Cache während der Entwicklung.

Die Developer Tools bieten weitere kleine Helfer, die hier nicht alle aufgezählt werden sollen. Wer sich dafür interessiert findet eine Auflistung unter [^2].

Da die Tools in produktiver Umgebung automatisch deaktiviert werden ist es eigentlich immer sinnvoll, sie einzubinden.

[^1]: http://livereload.com
[^2]: https://docs.spring.io/spring-boot/docs/current/reference/html/using-boot-devtools.html
