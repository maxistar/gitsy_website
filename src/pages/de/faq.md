---
layout: ../../layouts/MarkdownLayout.astro
title: Häufig gestellte Fragen
---

## Erste Schritte

> Was ist GitSy?

GitSy ist eine Android-App, die einen auf dem Gerät ausgewählten Ordner mit einem Git-Repository über HTTPS synchronisiert. Die App dient als Synchronisationsschicht zwischen diesem Ordner und einem Repository unter deiner Kontrolle.

> Ist GitSy ein Notiz-Editor?

Nein. GitSy synchronisiert Dateien, erstellt oder bearbeitet aber keine Notizen. Verwende eine andere Android-App, die Dateien im selben ausgewählten Ordner öffnen und bearbeiten kann.

> Welche Plattformen werden unterstützt?

Die GitSy-App ist für Android 7.0 und neuer verfügbar. Es gibt keine GitSy-App für iPhone, Windows, macOS oder Linux. Auf einem Desktop-System kannst du mit normalen Git-Werkzeugen auf dasselbe Repository zugreifen und die Dateien mit deiner bevorzugten Anwendung bearbeiten.

> Kann ich Dateien zwischen Android und einem Desktop-Computer synchronisieren?

Ja. GitSy kann den Android-Ordner mit einem Git-Repository synchronisieren. Ein Desktop-Computer kann dieses Repository mit normalen Git-Werkzeugen klonen und synchronisieren. GitSy selbst läuft nur auf Android.

> Warum muss der ausgewählte Ordner leer sein?

Beim Hinzufügen eines Projekts klont GitSy das Repository und kopiert dessen Inhalt in den ausgewählten Ordner. Ein leerer Ordner verhindert, dass nicht zugehörige lokale Dateien mit dem ersten Klon vermischt werden.

## Repositories und Authentifizierung

> Welche Git-Dienste werden unterstützt?

GitSy unterstützt Repositories, die über HTTPS erreichbar sind. GitHub, GitLab und kompatible selbst gehostete Git-Server sind die dokumentierten Optionen. URL-Beispiele findest du in der [Dokumentation zur Repository-Einrichtung](/de/documentation/#repositories).

> Kann ich ein bestehendes Repository verwenden?

Ja. Gib seine HTTPS-Klon-URL ein und wähle einen leeren Android-Ordner. GitSy klont das Repository in eine interne Arbeitskopie und kopiert anschließend die Dateien in den ausgewählten Ordner.

> Unterstützt GitSy SSH-Repository-URLs?

Nein. Die aktuelle Version unterstützt Repository-Zugriff über HTTPS. SSH- und OAuth-Authentifizierung sind geplant.

> Warum kann ich mein GitHub- oder GitLab-Kontopasswort nicht verwenden?

GitHub und GitLab verlangen für Git-Operationen über HTTPS ein persönliches Zugriffstoken. Gib deinen Kontonamen als Benutzernamen und das Token als Passwort ein. Weitere Hinweise findest du in der [Dokumentation zur Authentifizierung](/de/documentation/#authentication).

> Welche Berechtigungen benötigt mein Zugriffstoken?

Das Token benötigt Lese- und Schreibzugriff auf das Repository. Verwende den engsten Repository-Berechtigungsumfang, den dein Anbieter ermöglicht, und widerrufe oder ersetze ein offengelegtes Token.

> Sollte ich ein privates Repository verwenden?

Ja, wenn das Repository persönliche Notizen oder andere private Dateien enthält. GitSy funktioniert mit öffentlichen und privaten Repositories, aber der Repository-Anbieter steuert, wer darauf zugreifen kann.

## Synchronisation

> Was passiert beim Synchronisieren eines Projekts?

GitSy kopiert Änderungen aus dem ausgewählten Android-Ordner in seine interne Git-Arbeitskopie, erstellt einen Commit mit lokalen Änderungen, holt entfernte Änderungen, überträgt den synchronisierten Stand und kopiert das Ergebnis zurück in den ausgewählten Ordner.

> Erfolgt die Synchronisation automatisch?

Du kannst ein einzelnes Projekt oder alle Projekte manuell synchronisieren. Beim Öffnen von GitSy kann die App außerdem bereite Projekte einreihen, die seit mehr als einer Stunde nicht synchronisiert wurden. Konfigurierbare Hintergrundzeitpläne sind derzeit nicht verfügbar.

> Kann ich Dateien offline bearbeiten?

Ja. Du kannst Dateien im ausgewählten Ordner offline bearbeiten. GitSy benötigt eine Netzwerkverbindung, wenn du mit dem entfernten Repository synchronisierst.

> Kann ich mehrere Ordner oder Repositories konfigurieren?

Ja. Jedes GitSy-Projekt verbindet einen ausgewählten Android-Ordner mit einem Git-Repository. Du kannst mehrere Projekte erstellen und einzeln oder gemeinsam synchronisieren.

> Können mehrere Geräte dasselbe Repository verwenden?

Ja. Synchronisiere jedoch vor und nach der Bearbeitung derselben Dateien auf einem anderen Gerät. Gleichzeitige Änderungen an derselben Datei können Git-Konflikte verursachen.

> Wie behandelt GitSy Konflikte?

Die Konfliktbehandlung hängt derzeit vom Verhalten von Git/JGit während der Synchronisation ab. GitSy bietet noch keine interaktive Oberfläche zur Konfliktlösung. Halte eine weitere Kopie des Repositorys bereit, falls eine manuelle Git-Konfliktlösung erforderlich ist.

> Was soll ich tun, wenn die Synchronisation unterbrochen wird?

Lasse GitSy während der Synchronisation geöffnet. Wenn Android die App beendet, kann GitSy darauf hinweisen, dass der vorherige Vorgang nicht abgeschlossen wurde. Prüfe den ausgewählten Ordner und das entfernte Repository vor einer erneuten Synchronisation, besonders wenn dieselben Dateien an anderer Stelle geändert wurden.

## Dateien, Speicherung und Datenschutz

> Welche Dateitypen kann GitSy synchronisieren?

GitSy synchronisiert Dateien und Ordner statt eines bestimmten Notizformats. Reiner Text und Markdown sind typische Optionen. Für große Binärdateien gelten die normalen Grenzen und Leistungseigenschaften von Git und deinem Repository-Anbieter.

> Wo werden meine Dateien gespeichert?

Die Dateien werden im ausgewählten Android-Ordner, in einer von der App verwalteten Git-Arbeitskopie auf dem Gerät und nach erfolgreichem Push im entfernten Git-Repository gespeichert.

> Lädt GitSy meine Dateien auf eigene Server hoch?

Nein. GitSy betreibt kein eigenes gehostetes Notiz-Backend. Netzwerkübertragungen gehen an das von dir konfigurierte Git-Repository. Weitere Informationen findest du in der [Datenschutzerklärung](/de/privacy/).

> Kann GitSy auf Dateien anderer Apps zugreifen?

GitSy kann auf den Ordner zugreifen, den du ausdrücklich über die Android-Systemauswahl auswählst. Die App fordert keinen Zugriff auf alle Dateien des Geräts an. Eine andere App muss ebenfalls mit diesem Ordner arbeiten können, wenn du die Dateien dort bearbeiten möchtest.

> Was passiert, wenn ich ein Projekt aus GitSy lösche?

Das Löschen eines Projekts entfernt es aus der Liste der konfigurierten GitSy-Projekte. Der ausgewählte Ordner und das entfernte Git-Repository werden nicht gelöscht.

> Wie kann ich eine ältere Version einer Datei wiederherstellen?

GitSy bietet derzeit keine Oberfläche für den Versionsverlauf. Verwende deinen Git-Anbieter oder normale Git-Werkzeuge, um Commits zu prüfen und eine frühere Version wiederherzustellen.

## Fehlerbehebung

> Warum schlägt die Authentifizierung fehl?

Prüfe die HTTPS-Repository-URL, den Benutzernamen, den Token-Wert, den Ablauf des Tokens und die Lese- und Schreibberechtigungen für das Repository. Kontopasswörter funktionieren normalerweise nicht mit GitHub oder GitLab.

> Warum wird ein Klon- oder Synchronisationsfehler angezeigt?

Prüfe die Netzwerkverbindung, Repository-URL, Zugangsdaten, den freien Gerätespeicher und den Zugriff auf den ausgewählten Ordner. Stelle bei einem neuen Projekt außerdem sicher, dass der ausgewählte Ordner leer ist.

> Warum fehlen Änderungen auf einem anderen Gerät?

Prüfe, ob das erste Gerät die Synchronisation abgeschlossen und seinen Commit übertragen hat. Synchronisiere oder hole das Repository anschließend auf dem anderen Gerät. Wenn beide Geräte dieselbe Datei geändert haben, prüfe das Repository auf einen Konflikt.

> Welche Angaben sollte ein Fehlerbericht enthalten?

Nenne die GitSy-Version, Android-Version, den Git-Anbieter, den fehlgeschlagenen Vorgang, die angezeigte Fehlermeldung und ob das Problem reproduzierbar ist. Füge keine Zugriffstoken oder privaten Dateiinhalte hinzu. Support-Optionen findest du auf der [Kontaktseite](/de/contact/).
