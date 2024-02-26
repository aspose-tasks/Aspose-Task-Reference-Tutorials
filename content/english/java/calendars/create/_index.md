---
title: Create Calendar using Aspose.Tasks
linktitle: Create Calendar using Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 11
url: /java/calendars/create/
---

## Complete Source Code
```java
/*
 * Copyright 2001-2022 Aspose Pty Ltd. All Rights Reserved.
 *
 * This file is part of Aspose.Tasks. The source code in this file
 * is only intended as a supplement to the documentation, and is provided
 * "as is", without warranty of any kind, either expressed or implied.
 */



import com.aspose.tasks.*;


public class CreateCalendar {
	public static void main(String[] args) {
		// ExStart: CreateCalendar
		// The path to the documents directory.
		String dataDir = "Your Data Directory";

		// Create a project instance
		Project prj = new Project();

		// Define Calendar
		Calendar cal1 = prj.getCalendars().add("no info");
		Calendar cal2 = prj.getCalendars().add("no name");
		Calendar cal3 = prj.getCalendars().add("cal3");

		// Save the Project
		prj.save(dataDir + "project.xml", SaveFileFormat.Xml);

		// Display result of conversion.
		System.out.println("Process completed Successfully");
		// ExEnd: CreateCalendar
	}
}

```
