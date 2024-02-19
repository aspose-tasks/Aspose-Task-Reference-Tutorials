---
title: Working with Report Types in Aspose.Tasks
linktitle: Working with Report Types in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: 
type: docs
weight: 16
url: /net/rate-recurring-tasks/report-types/
---

## Complete Source Code
```csharp
namespace Aspose.Tasks.Examples.CSharp
{
    using System.IO;
    using NUnit.Framework;
    using Visualization;

    [TestFixture]
    public class ExReportType : ApiExampleBase
    {
        [Test, Ignore("Should be run explicitly.")]
        public void SaveBurnDownReport()
        {
            // ExStart:SaveBurnDownReport
            // ExFor: ReportType
            // ExSummary: Shows how to save the project burndown report in PDF format to the specified stream.
            var project = new Project(DataDir + @"Homemoveplan.mpp");
            using (var stream = new FileStream(OutDir + "Burndown_out.pdf", FileMode.Create))
            {
                project.SaveReport(stream, ReportType.Burndown);
            }

            // ExEnd:SaveBurnDownReport
        }
    }
}
```
