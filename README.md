# Razer Product API

Die Razer Produkt API bietet einen Mechanismus, um Informationen über Razer-Produkte, insbesondere ihre Produkt-IDs, zu verwalten und abzurufen.

## Inhaltsverzeichnis

- [**Einführung**](#einführung)
- [**Basis-URL**](#basis-url)
- [**Endpunkte**](#endpunkte)
  - [Produktliste abrufen](#produktliste-abrufen)
  - [Neues Produkt hinzufügen](#neues-produkt-hinzufügen)
- [**Häufig gestellte Fragen (FAQ)**](#häufig-gestellte-fragen-faq)
- [**Fehlerbehandlung**](#fehlerbehandlung)
- [**Abschluss**](#abschluss)

## Einführung

Die Razer Produkt API ermöglicht es Benutzern, eine Liste der verfügbaren Produkte zu erhalten oder neue Produkte zur Datenbank hinzuzufügen.

## Basis-URL

```
https://www.sys-worx.net/api/
```

## Endpunkte

### **Produktliste abrufen**

- **URL:** `/getProducts`
- **Methode:** `GET`
- **Beschreibung:** Ruft die vollständige Liste der Razer-Produkte und ihrer zugehörigen Produkt-IDs ab.

**Antwort:**

- **200 OK:** Bei Erfolg wird eine Liste von Produkten im JSON-Format zurückgegeben.
- **404 Not Found:** Die Datei mit den Produkt-IDs wurde nicht gefunden.

```json
[
    {
        "name": "Razer Basilisk V3 Pro",
        "transaction_id": "0x1f"
    },
    ...
]
```

### **Neues Produkt hinzufügen**

- **URL:** `/addProduct`
- **Methode:** `POST`
- **Beschreibung:** Fügt ein neues Razer-Produkt zur Datenbank hinzu.
- **Eingabe:** Ein JSON-Objekt, das den Produktnamen und die Produkt-ID enthält.

**Antwort:**

- **200 OK:** Bei Erfolg wird eine Bestätigungsnachricht zurückgegeben.
- **400 Bad Request:** Wenn das Produkt bereits existiert oder wenn die Datenstruktur nicht korrekt ist.
- **404 Not Found:** Die Datei mit den Produkt-IDs wurde nicht gefunden.

**Beispieleingabe:**
```json
{
    "name": "Razer Neues Produkt",
    "transaction_id": "0x2f"
}
```

**Beispielantwort:**
```json
{
    "message": "Product added successfully"
}
```

## Häufig gestellte Fragen (FAQ)

- **Kann ich mehrere Produkte gleichzeitig hinzufügen?**  
  Derzeit unterstützt die API das Hinzufügen eines einzelnen Produkts pro Anfrage.

- **Was passiert, wenn ich versuche, ein bereits vorhandenes Produkt hinzuzufügen?**  
  Die API gibt eine Fehlermeldung zurück und das Produkt wird nicht erneut hinzugefügt.

- **Wie kann ich sicherstellen, dass meine Daten korrekt sind?**  
  Stellen Sie sicher, dass die gesendeten Daten dem im Beispiel gezeigten JSON-Format entsprechen.

## Fehlerbehandlung

Es ist wichtig, auf die HTTP-Antwortcodes und die in der Antwort enthaltenen Nachrichten zu achten, um zu verstehen, was die API tut oder wenn etwas schief geht.

## Abschluss

Die Razer Produkt API ist ein einfaches, aber effektives Tool zur Verwaltung und Abfrage von Razer-Produkten und deren IDs. Bei weiteren Fragen oder Bedenken wenden Sie sich bitte an den API-Administrator.

---
