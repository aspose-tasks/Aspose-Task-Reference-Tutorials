---
title: Field Helper in Aspose.Tasks
linktitle: Field Helper in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: 
type: docs
weight: 15
url: /net/tasks-project-management/field-helper/
---

## Complete Source Code
```csharp
using Aspose.Tasks.Util;

namespace Aspose.Tasks.Examples.CSharp
{
    using System;
    using NUnit.Framework;

    [TestFixture]
    public class ExFieldHelper : ApiExampleBase
    {
        [Test] 
        public void WorkWithGetDefaultTaskFieldTitle()
        {
            // ExStart:WorkWithGetDefaultTaskFieldTitle
            // ExFor: FieldHelper.GetDefaultTaskFieldTitle
            // ExSummary: Shows how to get default field title for the specific task's field.

            Console.WriteLine("Title for Tsk.ActualCost: " + FieldHelper.GetDefaultTaskFieldTitle(Tsk.ActualCost.KeyType));
            Console.WriteLine("Title for Tsk.PercentWorkComplete: " + FieldHelper.GetDefaultTaskFieldTitle(Tsk.PercentWorkComplete.KeyType));
            // ExEnd:WorkWithGetDefaultTaskFieldTitle
        }
    }
}
```
