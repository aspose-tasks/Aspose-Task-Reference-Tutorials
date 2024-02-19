---
title: Saving Files in Various Formats in Aspose.Tasks
linktitle: Saving Files in Various Formats in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: 
type: docs
weight: 17
url: /net/rate-recurring-tasks/save-file-formats/
---

## Complete Source Code
```csharp
namespace Aspose.Tasks.Examples.CSharp
{
    using NUnit.Framework;
    using Saving;

    [TestFixture]
    public class ExSaveFileFormat : ApiExampleBase
    {
        [Test]
        public void SaveProjectAsCsv()
        {
            // ExStart:SaveProjectAsCSV
            // ExFor: SaveFileFormat
            // ExSummary: Shows how to save a project in CSV format.
            var project = new Project(DataDir + "CreateProject1.mpp");
            project.Save(OutDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);

            // ExEnd:SaveProjectAsCSV
        }
    }
}
```
