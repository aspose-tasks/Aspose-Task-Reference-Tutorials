---
title: Handling Workgroup Types in Aspose.Tasks
linktitle: Handling Workgroup Types in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: 
type: docs
weight: 12
url: /net/time-recurrence-configuration/workgroup-types/
---

## Complete Source Code
```csharp
namespace Aspose.Tasks.Examples.CSharp
{
    using NUnit.Framework;

    [TestFixture]
    public class ExWorkGroupType : ApiExampleBase
    {
        [Test]
        public void WorkWithWorkGroupType()
        {
            // ExStart
            // ExFor: WorkGroupType
            // ExSummary: Shows how to set work group of a resource.
            var project = new Project();

            // ...
            var resource = project.Resources.Add("Resource");
            resource.Set(Rsc.Workgroup, WorkGroupType.Web);

            // ...
            // ExEnd
        }
    }
}
```
