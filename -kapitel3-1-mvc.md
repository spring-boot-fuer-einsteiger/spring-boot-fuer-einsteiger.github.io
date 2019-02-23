---
title: Mvc
---

## MVC

Das Spring-Universum ist riesig, deshalb gibt es verschiedene Arten von Spring Boot-Anwendungen: Kommandozeilenanwendungen, Batch Programme, Web Flux-Anwendungen und MVC-Anwendungen um einige zu nennen. Durch das Hinzufügen von *spring-boot-starter-web* im letzten Kapitel haben wir uns für eine MVC-Anwendung basierend auf der Servlet-API entschieden. Das ist vermutlich die populärste Form der Spring-Anwendung, weshalb sie hier auch im Vordergrund steht.

MVC steht für Model-View-Controller und ist ein bekanntes Muster zur Unterteilung der Software in die namensgebenden Komponenten. Der Web Request wird dabei an einen Frontcontroller (in Spring das Dispatcher Servlet) geleitet und von dort mithilfe einer Mapping-Tabelle an andere Request Controller geroutet. Der Controller lädt oder erzeugt ein passendes Model (beispielsweise die anzuzeigenden Daten) und reicht diese an eine View weiter. Die View zeigt das Model dann an. 

Abbildung dazu!!!!!!!!
siehe baeldung.com/spring-controllers

Das Dispatcher Servlet ist bereits aktiv, sonst hätte man die Fehlermeldung im letzten Kapitel nicht gesehen. Was fehlt, ist zunächst ein spezialisierter Controller, der sich für eingehende Requests unter einer bestimmten URL zuständig fühlt. 



