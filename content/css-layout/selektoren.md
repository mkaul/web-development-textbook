---
title: CSS Selektoren
order: 30
---
Das Document Object Model (DOM) ist ein allgemeines Modell wie ein Dokument (die Webseite oder auch ein XML- Dokument) als Baum (im mathematische Sinne) angesehen werden kann. Mit dieser Vorstellung ergeben sich neue Fachwörter:

Die Tags werden als Elemente bezeichnet. So ist in folgendem Beispiel das erste li-Element innerhalb des ol-Elements. Das li Element enthält wiederum ein a Element, und dieses einen Text „erster Link“. 

    <html>
    <body>
        <p>Navigation</p>
        <h1>Überschrift</h1>
        <div class="intro">
          <h2>Dies und Das</h2>
          <ol>
            <li><a href="#bla">erster Link</a></li>
            <li><a href="#bla">zweiter Link</a></li>
          </ol>
        </div> ...

Elemente und Tags undwerden als Nodes oder Knoten bezeichnet. Für die Beziehungen zwischen Nodes werden die Begriffe Eltern, Kind, Nachkommen, Vorfahren verwedent: h1 ist ein Kind von body, „Überschrift“ ist das erste Kind von h1. „Überschrift“ ist damit ein Nachkomme von body.

Damit haben wir das Vokabular um auch kompliziertere CSS-Selektoren zu verstehen.

In Kapitel 2.2.2 haben Sie CSS Selektoren für Klassen und IDs kennen gelernt. In der CSS 2.1 Spezifikation werden u.a. folgende Schreibweisen für Selektoren beschrieben8:

<table border="1">
<tr><td>Name
<tr><td>Universal selector
<tr><td>Type selectors
<tr><td>Grouping
<tr><td>Descendant selectors
<tr><td>Child selectors
<tr><td>The link pseudo-classes
:focus
<tr><td>Adjacent selectors
<tr><td>Class selectors
<tr><td>ID selectors
</table>


Mit CSS3 kommen u.a. folgende Selektoren dazu:

<table border="1">
<tr><td>
Name

a[href^="mailto:"]

pseudo-class


:disabled
:checked

:nth-child(13)
:nth-child(odd)
:nth-child(even)
:nth-child(3n+1)
:last-child

    { float: right; }
img:nth-of-type(even) 

    { float: left; }

 
E::first-line


p::first-letter


</td></tr>
</table>

