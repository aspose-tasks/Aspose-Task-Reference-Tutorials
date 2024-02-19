---
title: Handling Compound Document Header Exception in Aspose.Tasks
linktitle: Handling Compound Document Header Exception in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: 
type: docs
weight: 16
url: /net/calendar-scheduling/compound-document-header-exception/
---

## Complete Source Code
```csharp
namespace Aspose.Tasks.Examples.CSharp
{
    using System;
    using NUnit.Framework;

    [TestFixture]
    public class ExCompoundDocumentHeaderException : ApiExampleBase
    {
        [Test]
        public void WorkWithCompoundDocumentHeaderException()
        {
            // ExStart
            // ExFor: CompoundDocumentHeaderException
            // ExFor: CompoundDocumentHeaderException.#ctor(SerializationInfo,StreamingContext)
            // ExSummary: Shows how to catch <see cref=\"CompoundDocumentHeaderException\" /> exception.
            try
            {
                var project = new Project(DataDir + "Project1.mpp");

                Console.WriteLine("Project Name: " + project.Get(Prj.Name));
            }
            catch (CompoundDocumentHeaderException e)
            {
                Console.WriteLine(e.Message);
            }

            // ExEnd
        }
    }
}
```
