---
title: Set Resource Properties in Aspose.Tasks
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 20
url: /java/resource-management/set-resource-properties/
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



import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;


import java.math.BigDecimal;

public class SetResourceProperties {
    public static void main(String[] args) {
        Project project = new Project();
        Resource rsc = project.getResources().add("Rsc");
        // Resource properties are represented by static class Rsc

        // set resource properties
        rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
        rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
    }
}





```
