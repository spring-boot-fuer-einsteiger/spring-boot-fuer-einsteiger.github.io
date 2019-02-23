## Controller

Zu diesem Zweck wird eine neue Java-Klasse `CRMController` im Paket `de.dirkkoller`angelegt. Die Klasse erhält die Annotation `@Controller`, was sie für Spring als Controller kennzeichnet. 

```java
package de.dirkkoller.crm;

import org.springframework.stereotype.Controller;

@Controller
public class CRMController {
	
}
```

Das alleine genügt noch nicht, es fehlt noch der Eintrag für die Routing-Tabelle. Dieser wird in Form der folgenden Methode zugefügt:

```java
@GetMapping("/")
public void ping(HttpServletResponse response) throws IOException {
	response.getWriter().write("<html><body><h1>Hello World</h1></body></html>");
}
```

Die Annotation `@GetMapping("/")`legt fest, dass GET-Requests auf Root von der darauf folgenden Methode behandelt werden. Der Name der Methode darf frei vergeben werden. Bei dem Parameter *response* vom Typ *HttpServletResponse* handelt es sich um einen impliziten Parameter, der von Spring gepflegt wird. Es gibt eine ganze Menge dieser Parameter, im Folgenden tauchen weitere auf. Die repsonse gestattet Zugriff auf einen Writer in den hier der anzuzeigende html-Code geschrieben wird.

Ein Aufruf von http://localhost:8080 führt nun zur Ausgabe von Hello World.
