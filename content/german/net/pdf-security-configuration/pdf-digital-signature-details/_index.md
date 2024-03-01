---
title: Konfigurieren Sie die digitale PDF-Signatur von MS Project mit Aspose.Tasks
linktitle: Konfigurieren der Details der digitalen PDF-Signatur in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie die digitalen Signaturdetails von Microsoft Project PDF mit Aspose.Tasks für .NET konfigurieren. Sorgen Sie für Sicherheit und Authentizität Ihrer Projektdateien.
type: docs
weight: 10
url: /de/net/pdf-security-configuration/pdf-digital-signature-details/
---
## Einführung
In diesem Tutorial führen wir Sie durch den Prozess der Konfiguration der digitalen Signaturdetails von Microsoft Project PDF mit Aspose.Tasks für .NET. Wenn Sie diese Schritte befolgen, können Sie digitale Signaturen nahtlos in Ihre MS Project-Dateien integrieren und so Sicherheit und Authentizität gewährleisten.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1.  Aspose.Tasks für .NET: Stellen Sie sicher, dass Aspose.Tasks für .NET in Ihrer Entwicklungsumgebung installiert ist. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).
2. Microsoft Project-Datei: Bereiten Sie die Microsoft Project-Datei vor, mit der Sie arbeiten möchten, und stellen Sie sicher, dass sie in Ihrem Projektverzeichnis zugänglich ist.
3. X.509-Zertifikat: Besorgen Sie sich ein X.509-Zertifikat, das für die digitale Signatur verwendet wird. Wenn Sie noch kein Zertifikat haben, können Sie zu Testzwecken ein selbstsigniertes Zertifikat erstellen.
## Namensräume importieren
Zunächst müssen Sie die erforderlichen Namespaces in Ihr .NET-Projekt importieren, um auf die erforderlichen Klassen und Methoden von Aspose.Tasks zuzugreifen.
```csharp
using Aspose.Tasks;
using System;
using System.Security.Cryptography;
using System.Security.Cryptography.X509Certificates;

using Aspose.Tasks.Saving;
```
Lassen Sie uns das Beispiel nun in mehrere Schritte unterteilen:
## Schritt 1: Laden Sie die Microsoft Project-Datei
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```
## Schritt 2: Konfigurieren Sie die PDF-Speicheroptionen
```csharp
var options = new PdfSaveOptions();
```
## Schritt 3: Geben Sie das X.509-Zertifikat an
```csharp
var certificate = new X509Certificate2();
```
## Schritt 4: PDF-Signaturdetails erstellen
```csharp
var signatureDetails = new PdfDigitalSignatureDetails(
    // Zertifikat angeben
    certificate,
    // Geben Sie einen Grund für die Unterzeichnung an
    "reason",
    // Geben Sie einen Ort für die Unterzeichnung an
    "location",
    // Geben Sie ein Datum für die Unterzeichnung an
    new DateTime(2019, 1, 1),
    // Geben Sie einen Hash-Algorithmus zum Signieren an
    PdfDigitalSignatureHashAlgorithm.Sha1);
```
## Schritt 5: Signaturdetails anzeigen
```csharp
Console.WriteLine("Certificate: " + signatureDetails.Certificate);
Console.WriteLine("Reason: " + signatureDetails.Reason);
Console.WriteLine("Location: " + signatureDetails.Location);
Console.WriteLine("Signature Date: " + signatureDetails.SignatureDate);
Console.WriteLine("Hash Algorithm: " + signatureDetails.HashAlgorithm);
```
## Schritt 6: Legen Sie die Details der digitalen Signatur fest
```csharp
// Legen Sie die Details der digitalen Signatur fest
options.DigitalSignatureDetails = signatureDetails;
```
## Schritt 7: Speichern Sie das Projekt mit Verschlüsselungsdetails
```csharp
// Speichern Sie das Projekt mit den angegebenen Verschlüsselungsdetails
project.Save(DataDir + "WorkWithPdfEncryptionDetails_out.pdf", options);
```
## Abschluss
Glückwunsch! Sie haben die digitalen Signaturdetails von Microsoft Project PDF mit Aspose.Tasks für .NET erfolgreich konfiguriert. Indem Sie diese Schritte befolgen, können Sie die Sicherheit und Authentizität Ihrer MS Project-Dateien gewährleisten.
## FAQs
### F: Kann ich ein selbstsigniertes Zertifikat zum digitalen Signieren verwenden?
A: Ja, Sie können zu Testzwecken ein selbstsigniertes Zertifikat verwenden. Für Produktionsumgebungen wird jedoch empfohlen, ein vertrauenswürdiges Zertifikat zu verwenden, das von einer Zertifizierungsstelle ausgestellt wurde.
### F: Unterstützt Aspose.Tasks andere Hash-Algorithmen für die digitale Signatur?
A: Ja, Aspose.Tasks unterstützt verschiedene Hash-Algorithmen für die digitale Signatur, darunter SHA-1, SHA-256 und SHA-512.
### F: Kann ich das Erscheinungsbild der digitalen Signatur im PDF anpassen?
A: Ja, Sie können das Erscheinungsbild der digitalen Signatur, einschließlich Text, Schriftart, Farbe und Position, entsprechend Ihren Anforderungen anpassen.
### F: Ist es möglich, eine digitale Signatur zu entfernen oder zu aktualisieren, nachdem sie angewendet wurde?
A: Nein, sobald eine digitale Signatur auf ein PDF angewendet wurde, kann diese nicht entfernt oder aktualisiert werden. Bei Bedarf können Sie jedoch weitere Signaturen hinzufügen.
### F: Gibt es Einschränkungen hinsichtlich der Größe oder Komplexität der Microsoft Project-Datei?
A: Aspose.Tasks kann ohne Einschränkungen Microsoft Project-Dateien unterschiedlicher Größe und Komplexität verarbeiten. Die Leistung kann jedoch je nach Hardware und verfügbaren Ressourcen variieren.