---
title: Configure MS Project PDF Encryption Details in Aspose.Tasks
linktitle: Configuring PDF Encryption Details in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to configure MS Project PDF encryption details in Aspose.Tasks for .NET. Secure your project files with user and owner passwords.
type: docs
weight: 11
url: /net/pdf-security-configuration/pdf-encryption-details/
---
## Introduction
In the world of .NET development, managing tasks efficiently is crucial. Aspose.Tasks for .NET simplifies this process by providing a comprehensive set of tools to work with Microsoft Project files. One essential aspect of task management is ensuring the security of sensitive project information. In this tutorial, we will delve into configuring MS Project PDF encryption details using Aspose.Tasks for .NET.
## Prerequisites
Before we begin, ensure you have the following prerequisites:
1. Basic Understanding of .NET: Familiarity with C# and .NET development environment.
2. Installation of Aspose.Tasks for .NET: Download and install the Aspose.Tasks for .NET library from [here](https://releases.aspose.com/tasks/net/).
3. Microsoft Project Files: Have access to Microsoft Project files for encryption.
4. Development Environment: Set up a development environment such as Visual Studio.

## Import Namespaces
In your C# code, include the necessary namespaces for working with Aspose.Tasks and PDF functionalities:
```csharp
    using System;
    using NUnit.Framework;
    using Saving;
```
## Step 1: Load the Microsoft Project File
The first step is to load the Microsoft Project file you want to encrypt:
```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Step 2: Specify Encryption Details
Define the encryption details including user password, owner password, encryption algorithm, and permissions:
```csharp
var encryptionDetails = new PdfEncryptionDetails(
    "userPassword",        // User Password
    "ownerPassword",       // Owner Password
    PdfEncryptionAlgorithm.RC4_128);  // Encryption Algorithm
// Specify permissions
encryptionDetails.Permissions = PdfPermissions.ModifyContents | PdfPermissions.ModifyAnnotations;
```
## Step 3: Set Encryption Options
Configure encryption options for saving the PDF:
```csharp
var options = new PdfSaveOptions
{
    EncryptionDetails = encryptionDetails
};
```
## Step 4: Save the Project with Encryption
Save the project with the specified encryption details:
```csharp
project.Save(DataDir + "EncryptedProject.pdf", options);
```

## Conclusion
In this tutorial, we've explored how to configure MS Project PDF encryption details using Aspose.Tasks for .NET. By following these steps, you can ensure the security of your project files by encrypting them with user and owner passwords, specifying encryption algorithms, and setting permissions as needed.
## FAQ's
### Q: Can I encrypt multiple MS Project files simultaneously?
A: Yes, you can loop through multiple project files and apply encryption details to each one individually.
### Q: What encryption algorithms are supported?
A: Aspose.Tasks for .NET supports RC4_40 and RC4_128 encryption algorithms for PDF encryption.
### Q: Can I change encryption details after saving the PDF?
A: No, once the PDF is encrypted and saved, the encryption details cannot be altered.
### Q: Are there any limitations on password length?
A: While there are no specific limitations imposed by Aspose.Tasks, it's recommended to use strong passwords for enhanced security.
### Q: Can encrypted PDFs be decrypted programmatically?
A: Aspose.Tasks provides APIs to work with encrypted PDFs, allowing decryption using appropriate credentials.
