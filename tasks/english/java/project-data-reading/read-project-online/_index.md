---
title: "aspose tasks java: Effortless MS Project Online Data Reading"
linktitle: Reading Project Online Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: "Learn how to read MS Project Online data using aspose tasks java. This guide shows how to retrieve project list, list sharepoint projects, and get resource count."
weight: 13
url: /java/project-data-reading/read-project-online/
date: 2025-12-15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java: Effortless MS Project Online Data Reading

## Introduction
In the realm of project management, handling Microsoft Project Online data efficiently is crucial for streamlined operations. **aspose tasks java** provides a robust, easy‑to‑use API that lets you read Project Online data without wrestling with low‑level HTTP calls. In this tutorial we’ll walk through how to retrieve a project list, list SharePoint projects, and get resource count from each project—all with just a few lines of Java code.

## Quick Answers
- **What does aspose tasks java do?** It reads and manipulates Microsoft Project files and Project Online data programmatically.  
- **Do I need a license to try it?** A free trial is available; a license is required for production use.  
- **Which credentials are required?** SharePoint domain, username, and password (or Azure AD token).  
- **Can I list SharePoint projects?** Yes – use `ProjectServerManager.getProjectList()` to retrieve them.  
- **How do I get the resource count?** Load each `Project` object and call `project.getResources().size()`.

## What is aspose tasks java?
**aspose tasks java** is a developer‑focused library that abstracts the complexities of Microsoft Project’s file formats and Project Server REST APIs. It enables you to read, create, and modify project data directly from Java applications, making integration with existing enterprise systems straightforward.

## Why use aspose tasks java for reading MS Project Online?
- **No manual HTTP handling** – the library takes care of authentication and REST calls.  
- **Strong type safety** – work with `Project`, `ProjectInfo`, and other POJOs instead of raw JSON.  
- **Cross‑platform** – runs on any JVM‑compatible environment.  
- **Rich feature set** – beyond reading, you can also update tasks, resources, and timelines.

## Prerequisites
Before diving in, make sure you have:

1. **Java Development Kit (JDK)** – JDK 8 or higher installed.  
2. **Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).  
3. **Microsoft Project Online account** – with permissions to read projects.  
4. **SharePoint domain address** – where your Project Online instance lives.  
5. **Username and password** – or appropriate Azure AD credentials for authentication.

## Import Packages
First, import the essential Aspose.Tasks classes that we’ll use throughout the tutorial:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Step 1: Set SharePoint Domain, Username, and Password
Define the connection details for your Project Online environment. Replace the placeholder values with your own credentials.

```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```

## Step 2: Authenticate with Project Server Credentials
Create a `ProjectServerCredentials` object and initialise a `ProjectServerManager`. This manager will handle all subsequent calls to Project Online.

```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## Step 3: Retrieve Project List and Display Information
Use the manager to **retrieve project list** (list SharePoint projects) and print basic details such as name, creation date, and last saved date.

```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## Step 4: Load Individual Projects and Output Resource Count
For each project returned in the previous step, load the full `Project` object and display the **resource count**.

```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **Authentication failed** | Incorrect domain, username, or password. | Verify credentials and ensure the account has Project Online read permissions. |
| **SSLHandshakeException** | Java runtime lacks the required TLS version. | Update JDK to the latest release or enable TLS 1.2+. |
| **`reader.getProjectList()` returns empty** | Account does not have access to any projects. | Check Project Online permissions or use an admin account. |
| **Large projects cause OutOfMemoryError** | Loading many projects at once consumes memory. | Load projects one at a time and release references after use. |

## Frequently Asked Questions
### Q: Can I use aspose tasks java to modify MS Project Online data?
A: Yes, Aspose.Tasks provides extensive capabilities for both reading **and** modifying Project Online data programmatically.

### Q: Does Aspose.Tasks support other project management file formats?
A: Absolutely. It supports MPP, XML, Primavera, and many more, ensuring compatibility across diverse project ecosystems.

### Q: Is there a free trial available for Aspose.Tasks for Java?
A: Yes, you can avail of a free trial from [here](https://releases.aspose.com/) to explore the features and functionalities of Aspose.Tasks.

### Q: Where can I find comprehensive documentation for Aspose.Tasks for Java?
A: You can refer to the detailed documentation [here](https://reference.aspose.com/tasks/java/) for comprehensive guidance on utilizing Aspose.Tasks in your Java projects.

### Q: What support options are available for Aspose.Tasks for Java?
A: If you encounter any issues or have queries, you can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).

---

**Last Updated:** 2025-12-15  
**Tested With:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}