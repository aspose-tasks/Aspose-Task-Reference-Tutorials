---
title: Read Project from Primavera XML in Aspose.Tasks
linktitle: Read Project from Primavera XML in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 21
url: /java/project-management/read-primavera-xml/
---

## Complete Source Code
```java


import com.aspose.tasks.PrimaveraXmlReader;
import com.aspose.tasks.Project;


import java.io.FileInputStream;
import java.io.IOException;
import java.io.InputStream;
import java.nio.file.Files;
import java.nio.file.OpenOption;
import java.nio.file.Paths;
import java.nio.file.StandardCopyOption;
import java.nio.file.StandardOpenOption;
import java.util.List;

public class PrimaveraXmlRead {
    public static void main(String[] args) throws IOException {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        readProjectUidsFromXmlFile(dataDir);

        readLoadPrimaveraXmlProject(dataDir);

        readProjectUidsFromStream(dataDir);

        // Display result of conversion.
        System.out.println("Process completed Successfully");
    }

    public static void readProjectUidsFromXmlFile(String dataDir)
    {
        // Shows how to import a project from a Primavera XML file.
        PrimaveraXmlReader reader = new PrimaveraXmlReader(dataDir + "Primavera.xml");
        List<Integer> projectUids = reader.getProjectUids();
        for (Integer projectUid : projectUids)
        {
            System.out.println("Project UID: " + projectUid);
        }
    }

    public static void readLoadPrimaveraXmlProject(String dataDir)
    {
        // Shows how to load a project from a Primavera XML file when project uid is known.
        PrimaveraXmlReader reader = new PrimaveraXmlReader(dataDir + "PrimaveraProject.xml");
        Project project = reader.loadProject(3882);
        System.out.println(project.getName());
    }

    public static void readProjectUidsFromStream(String dataDir) throws IOException
    {
        // Shows how to import a project from a Primavera XML stream.
        try (InputStream stream = Files.newInputStream(Paths.get(dataDir + "Primavera.xml"), StandardOpenOption.READ)){
            PrimaveraXmlReader reader = new PrimaveraXmlReader(stream);
            List<Integer> projectUids = reader.getProjectUids();
            for (Integer projectUid : projectUids)
            {
                System.out.println("Project UID: " + projectUid);
            }
        }
    }
}

```
