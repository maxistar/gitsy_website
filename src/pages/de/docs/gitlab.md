---
layout: ../../../layouts/MarkdownLayout.astro
title: Privates GitLab-Repository erstellen und HTTPS-Zugang einrichten
---

## Privates Repository erstellen

1. Öffne [GitLab](https://gitlab.com) und melde dich an.
2. Klicke in der oberen Navigation auf „+“ und wähle „New project“.
3. Gib Projektname und Beschreibung ein.
4. Wähle bei der Sichtbarkeit „Private“.
5. Klicke auf „Create project“.

![](/images/gitlab_create_repository.png)

## HTTPS-Zugang einrichten

1. Erstelle einen Personal Access Token:
   - Klicke oben rechts auf dein Profilbild.
   - Öffne „Preferences“.
   - Wähle in der Seitenleiste „Access Tokens“.
   - Gib dem Token einen Namen, zum Beispiel „HTTPS Access“.
   - Wähle die Berechtigungen `read_repository` und `write_repository`.
   - Klicke auf „Create personal access token“.
   - Kopiere den erzeugten Token sofort; er wird später nicht erneut angezeigt.

![](/images/gitlab_create_token_properties.png)

2. Verwende den Token für HTTPS-Zugang:
   - Nutze zum Klonen oder Pushen diese Repository-URL:

   `https://gitlab.com/DEIN_BENUTZERNAME/DEIN_PROJEKT.git`

![](/images/gitlab_test_notes.png)

   - Ersetze:
     - `DEIN_BENUTZERNAME` durch deinen GitLab-Benutzernamen
     - `DEIN_PROJEKT` durch den Projektnamen

![](/images/gitlab_use_credentials.png)

## Wichtige Hinweise

- Bewahre deinen Personal Access Token sicher auf und teile ihn nicht.
- Der Token erhält nur Zugriff entsprechend den gewählten Berechtigungen.
- Du kannst Tokens jederzeit in den GitLab-Einstellungen widerrufen.
- Ein Passwortmanager hilft bei der sicheren Aufbewahrung.
- GitLab-Tokens laufen standardmäßig nach einem Jahr ab.

## Beispielbefehle

Repository klonen:

```bash
git clone https://DEIN_BENUTZERNAME:DEIN_TOKEN@gitlab.com/DEIN_BENUTZERNAME/DEIN_PROJEKT.git
```

Repository pushen:

```bash
git push https://DEIN_BENUTZERNAME:DEIN_TOKEN@gitlab.com/DEIN_BENUTZERNAME/DEIN_PROJEKT.git
```
