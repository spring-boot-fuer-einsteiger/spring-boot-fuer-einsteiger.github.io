# Container, Dependency Injection und IOC

Java-Anwendungen bestehen aus Objekten (Instanzen von Klassen), die untereinander Methoden aufrufen. Damit ein Objekt die Methode eines anderen Objekts aufrufen kann muss es eine Referenz auf dieses besitzen. Im einfachsten Fall wird das Objekt mit dem new-Operator erzeugt und einer Variablen zugewiesen:

	
	Person person = new Person();

Diese Standard-Instanziierung, die man so in jedem Lehrbuch findet, bringt ein kleines und anfangs meist unscheinbares Problem mit sich: Nan handelt sich eine Abhängigkeit ein: Klasse A verweist in ihrem Quellcode auf Klasse B, sie ist eng-gekoppelt. B kann nicht ohne weiteres (ohne Ändern des Quellcodes) gegen etwas anderes ausgetauscht werden. Aber warum sollte man das überhaupt tun? Weil sich die Welt weiter dreht und die Anforderungen ändern. Irgendwann soll B gegen ein viel besseres B' ausgetauscht werden. Vielleicht soll sogar der Benutzer entscheiden ob B oder B' (oder B'' mit Perleffekt) zum Einsatz kommen soll. Oder A soll getestet werden und B deshalb gegen eine Mock-Implementierung ersetzt werden. Es gibt viele gute Gründe A nicht anfassen zu müssen wenn sich bei B was ändert, also eine enge Kopplung zu vermeiden.

Eine Möglichkeit das Dilemma zu vermeiden ist in der Klasse A nicht mit einer konkreten Instanz von B zu arbeiten, sondern lediglich mit einem Typ der durch ein Interface definiert wird.





