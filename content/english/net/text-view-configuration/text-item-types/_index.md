---
title: Handling Text Item Types in Aspose.Tasks
linktitle: Handling Text Item Types in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: 
type: docs
weight: 10
url: /net/text-view-configuration/text-item-types/
---

## Complete Source Code
```csharp
namespace Aspose.Tasks.Examples.CSharp
{
    using System.Collections.Generic;
    using System.Drawing;
    using NUnit.Framework;
    using Saving;
    using Visualization;

    [TestFixture]
    public class ExTextItemType : ApiExampleBase
    {
        [Test]
        public void CustomizeTextStyle()
        {
            // ExStart
            // ExFor: TextItemType
            // ExSummary: Shows how to work with text item types.
            var project = new Project(DataDir + "CreateProject2.mpp");
            SaveOptions options = new PdfSaveOptions
            {
                PresentationFormat = PresentationFormat.ResourceSheet
            };

            var style = new TextStyle(FontStyles.Italic | FontStyles.Bold)
            {
                Color = Color.OrangeRed
            };

            style.ItemType = TextItemType.OverallocatedResources;

            options.TextStyles = new List<TextStyle>
            {
                style
            };
            project.Save(OutDir + "CustomizeTextStyle_out.pdf", options);

            // ExEnd
        }
    }
}
```
