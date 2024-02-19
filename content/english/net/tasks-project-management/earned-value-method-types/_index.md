---
title: Earned Value Method Types in Aspose.Tasks
linktitle: Earned Value Method Types in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: 
type: docs
weight: 10
url: /net/tasks-project-management/earned-value-method-types/
---

## Complete Source Code
```csharp
namespace Aspose.Tasks.Examples.CSharp
{
    using NUnit.Framework;

    [TestFixture]
    public class ExEarnedValueMethodType : ApiExampleBase
    {
        [Test]
        public void WorkWithEarnedValueMethodType()
        {
            {
                // ExStart
                // ExFor: EarnedValueMethodType
                // ExSummary: Shows how to specify the method used for calculating earned value (EarnedValueMethodType.PercentComplete).
                var project = new Project(DataDir + "Project2.mpp");
                // set earned value method type to 'PercentComplete'
                project.Set(Prj.DefaultTaskEVMethod, EarnedValueMethodType.PercentComplete);
                // work with the project...
                // ExEnd
            }
        }
    }
}
```
