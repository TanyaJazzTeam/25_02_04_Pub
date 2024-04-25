Erster Header | Zweite Überschrift
--- | ---
Inhaltszelle | Inhaltszelle
Inhaltszelle | Inhaltszelle

Erster Header | Zweite Überschrift
--- | ---
Inhaltszelle | Inhaltszelle
Inhaltszelle | Inhaltszelle

![Zitadelle](https://vignette.wikia.nocookie.net/masseffect/images/d/d7/MassEffect2Citadel.jpg/revision/latest?cb=20100721191415)

Linksbündig | Zentriert | Rechtsbündig
:-- | :-: | --:
Spalte 3 ist | ein wortreicher Text | **1600 $**
Spalte 2 ist | zentriert | $12
Zebrastreifen | sind ordentlich | ~~$1~~

Dillinger ist ein Cloud-fähiger, für mobile Endgeräte geeigneter, Offline-Speicher- und AngularJS-basierter HTML5-Markdown-Editor.

- Geben Sie links etwas Markdown ein
- Siehe HTML rechts
- Magie

# trueE_E

- Importieren Sie eine HTML-Datei und sehen Sie zu, wie sie wie von Zauberhand in Markdown konvertiert wird
- Bilder per Drag &amp; Drop verschieben (erfordert eine Verknüpfung mit Ihrem Dropbox-Konto)

Du kannst auch:

- Importieren und speichern Sie Dateien von GitHub, Dropbox, Google Drive und One Drive
- Ziehen Sie Markdown- und HTML-Dateien per Drag &amp; Drop in Dillinger
- Exportieren Sie Dokumente als Markdown, HTML und PDF

Markdown ist eine leichtgewichtige Auszeichnungssprache, die auf den Formatierungskonventionen basiert, die Menschen normalerweise in E-Mails verwenden. Wie [John Gruber] auf der [Markdown-Site][df1] schreibt:

> Das wichtigste Designziel für die Formatierungssyntax von Markdown ist, sie so lesbar wie möglich zu machen. Die Idee ist, dass ein mit Markdown formatiertes Dokument so wie es ist, als einfacher Text veröffentlicht werden kann, ohne dass es aussieht, als wäre es mit Tags oder Formatierungsanweisungen markiert.

Der Text, den Sie hier sehen, ist *tatsächlich* in Markdown geschrieben! Um ein Gefühl für die Syntax von Markdown zu bekommen, geben Sie etwas Text in das linke Fenster ein und sehen Sie sich die Ergebnisse im rechten an.

### FALSCH

Um ordnungsgemäß zu funktionieren, verwendet Dillinger eine Reihe von Open-Source-Projekten:

- [AngularJS] – HTML für Web-Apps verbessert!
- [Ace Editor] - toller webbasierter Texteditor
- [markdown-it] - Markdown-Parser richtig gemacht. Schnell und einfach zu erweitern.
- [Twitter Bootstrap] - großartiges UI-Boilerplate für moderne Web-Apps
- [node.js] - ereignisgesteuerte E/A für das Backend
- [Express] - schnelles node.js Netzwerk-App-Framework [@tjholowaychuk]
- [Gulp] - das Streaming-Build-System
- [Breakdance](https://breakdance.github.io/breakdance/) - HTML-zu-Markdown-Konverter
- [jQuery] – na klar

Und natürlich ist Dillinger selbst Open Source mit einem [öffentlichen Repository][dill] auf GitHub.

### Installation

![Ilos](https://lh3.googleusercontent.com/proxy/DDV8a7sLIWurhJtW8Ego9bq-JlwpfFFoR0tkLJQKKYXEXoWHB6ZUP5jGKD2VcYt3z1QVsgcn6L3GoU1ns8m9fvi3U51GzddA70ZUMHgzHvjl4-i7YOJY9cShBPrfjUhMQhxaJ97WFBp612XmjMXVGypfGkiBarN4PWxhiHkiYYNW7HGbtTpOcyt9GQ4Q23C2noxLTWFXZMcQZhRpQA_qzu2n6_H6CPViBnhSHpEl4JZAPaGCSJqgZg)

Zum Ausführen von Dillinger ist [Node.js](https://nodejs.org/) v4+ erforderlich.

Installieren Sie die Abhängigkeiten und Entwicklungsabhängigkeiten und starten Sie den Server.

```sh
$ cd dillinger
$ npm install -d
$ node app
```

Für Produktionsumgebungen ...

```sh
$ npm install --production
$ NODE_ENV=production node app
```

### Plugins

Dillinger wird derzeit um die folgenden Plugins erweitert. Anweisungen zur Verwendung in Ihrer eigenen Anwendung finden Sie unten.

Plugin | Liesmich
--- | ---
Dropbox | [plugins/dropbox/README.md][PlDb]
GitHub | [plugins/github/README.md][PlGh]
Google Drive | [plugins/googledrive/README.md][PlGd]
Eine Fahrt | [plugins/onedrive/README.md][PlOd]
Mittel | [plugins/medium/README.md][PlMe]
Google Analytics | [plugins/googleanalytics/README.md][PlGa]

### Entwicklung

## alt

Die Kennzahlen, aus denen sich die Core Web Vitals zusammensetzen, werden sich im Laufe der Zeit [weiterentwickeln](#evolving-web-vitals) . Der aktuelle Satz für 2020 konzentriert sich auf drei Aspekte der Benutzererfahrung – *Laden* , *Interaktivität* und *visuelle Stabilität* – und umfasst die folgenden Kennzahlen

Möchten Sie einen Beitrag leisten? Großartig!

Dillinger verwendet Gulp + Webpack für eine schnelle Entwicklung. Nehmen Sie eine Änderung in Ihrer Datei vor und sehen Sie sofort Ihre Aktualisierungen!

Öffnen Sie Ihr bevorzugtes Terminal und führen Sie diese Befehle aus.

Erste Registerkarte:

```sh
$ node app
```

Zweite Registerkarte:

```sh
$ gulp watch
```

(optional) Drittens:

```sh
$ karma test
```

#### Gebäude für Quelle

Für die Produktionsfreigabe:

```sh
$ gulp build --prod
```

Erstellen vorgefertigter ZIP-Archive zur Verteilung:

```sh
$ gulp build dist --prod
```

### Docker

Dillinger lässt sich sehr einfach in einem Docker-Container installieren und bereitstellen.

Standardmäßig stellt der Docker Port 8080 bereit. Ändern Sie dies also bei Bedarf im Dockerfile. Wenn Sie bereit sind, verwenden Sie einfach das Dockerfile, um das Image zu erstellen.

```sh
cd dillinger
docker build -t joemccann/dillinger:${package.json.version} .
```

Dadurch wird das Dillinger-Image erstellt und die erforderlichen Abhängigkeiten werden eingefügt. Achten Sie darauf, `${package.json.version}` durch die aktuelle Version von Dillinger zu ersetzen.

Sobald dies erledigt ist, führen Sie das Docker-Image aus und ordnen den Port dem gewünschten Port auf Ihrem Host zu. In diesem Beispiel ordnen wir einfach Port 8000 des Hosts Port 8080 des Dockers zu (oder dem Port, der in der Docker-Datei verfügbar gemacht wurde):

```sh
docker run -d -p 8000:8080 --restart="always" <youruser>/dillinger:${package.json.version}
```

Überprüfen Sie die Bereitstellung, indem Sie in Ihrem bevorzugten Browser zu Ihrer Serveradresse navigieren.

```sh
127.0.0.1:8000
```

#### Kubernetes + Google Cloud

Siehe [KUBERNETES.md](https://github.com/joemccann/dillinger/blob/master/KUBERNETES.md)

### Alle
