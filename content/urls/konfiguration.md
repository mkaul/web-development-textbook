---
title: Konfiguration
order: 20
---

Die Konfiguration des Webservers wird hier am Beispiel von Apache gezeigt. Andere Webserver (z.B: Internet Information Server von Microsoft) verfügen auch über diese Fähigkeiten, werden aber anders konfiguriert.

Die Apache-Konfiguration müssen Sie noch nicht anwenden können, sie ist hier nur zur Information angeführt. Eventuell können Sie im Fach „Operations &amp; IT“ diese Information in diesem Semester anwenden, auf jeden Fall im nächsten Semester in „Webprogrammierung 2“.

 Betriebssystem des Webservers
Die Webserver der FH sind ausnahmslos UNIX-Server. Die UNIX-Dateisysteme unterscheiden bei Datei- und Ordnernamen zwischen Groß- und Kleinschreibung, sind also „case-sensitive“. Der Rechner auf dem Sie die Webseiten erstellen läuft wahrscheinlich unter Windows oder MacOS; dort sind die Dateisysteme „case-insensitive“.

Ein Link auf die Datei bild.JPG funktioniert unter Windows oder MacOS auch, wenn er bild.jpg geschreiben wird.

Liegt die Datei aber dann am (UNIX-)Webserver, so funktioniert der Link nicht mehr! bild.jpg und bild.JPG sind zwei unterschiedliche Dateien!

 Webspace und Ordner
Im einfachsten Fall wird im Webserver ein Ordner spezifiziert, der als Ausgangspunkt für den Webspace dient. Für den Webserver mediacube.at ist dies der Ordner /var/www/virthosts/mediacube.at/

URL

    <VirtualHost mediacube.at>
    DocumentRoot /var/www/virthosts/mediacube.at/
    </VirtualHost>

 Standard-Dokument

Endet eine URL auf einen Schrägstrich, dann verweist sie eigentlich auf einen ganzen Ordner, nicht auf eine spezielle Datei. Für diesen Fall kann im Webserver ein Standard-Dokument definiert werden. Auf allen Webservern der FH ist dies die Datei index.html.  d.h. wenn eine URL auf einen Ordner verweist, und in diesem Ordner eine Datei mit Namen index.html  existiert, dann wird diese Datei geliefert.

URL

DirectoryIndex index.html

Achtung: die Konfiguration ist am Internet Information Server normalerweise anders, dort wir die Datei default.htm verwendet!

Was passiert wenn keine Datei mit dem richtigen Namen vorhanden ist? Die zwei Möglichkeiten sehen Sie in Abbildung 43: entweder eine Auflistung der Dateien im Ordner oder eine Fehlermeldung.

 
![Abbildung 43: Zugriff auf einen Ordner ohne Standard-Dokument (index.html): Auflistung oder Fehlermeldung](/images/apache-directory-index.png)

Die entsprechenden Apache-Konfigurationsanweisung dazu sind:

Options +Indexes

Am Webserver www.users existiert für jeden Account automatisch ein Webspace. Dieser Webspace befindet sich innerhalb des Home-Verzeichnisses des jeweiligen Accounts. Z.B. könnte eine Studentin den Username fhs303030 habe und das Home-Verzeichnis /home/store/fhs303030/. Ihr Webspace ist im Unter-Ordner htdocs: 

URL

Der Link von einem User-Webspace zum nächsten funktioniert also so:

http://www.users.fh-salzburg.ac.at/~fhs303030/test.html   +    ../~fhs111111/test   =

http://www.users.fh-salzburg.ac.at/~fhs111111/test

Oder relative zum Webserver:

http://www.users.fh-salzburg.ac.at/~fhs303030/test.html   +    /~fhs111111/test   =

http://www.users.fh-salzburg.ac.at/~fhs111111/test

Die Apache Konfigurationsanweisung lautet:

UserDir htdocs
