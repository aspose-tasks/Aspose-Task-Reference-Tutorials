---
title: Different Types of Baselines in Aspose.Tasks
linktitle: Different Types of Baselines in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: 
type: docs
weight: 21
url: /net/advanced-features/baseline-types/
---

## Complete Source Code
```csharp
namespace Aspose.Tasks.Examples.CSharp
{
    using NUnit.Framework;

    [TestFixture]
    public class ExBaselineType : ApiExampleBase
    {
        [Test]
        public void WorkWithBaselineType()
        {
            // ExStart
            // ExFor: BaselineType
            // ExSummary: Shows how to set baseline for the project (BaselineType.Baseline).
            var project = new Project(DataDir + "Project2.mpp");
            // save baseline fields to the specified baseline for the entire project.
            project.SetBaseline(BaselineType.Baseline);
            // work with project's baselines...
            // ExEnd
        }
    }
}
```
