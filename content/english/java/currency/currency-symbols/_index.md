---
title: Currency Symbols Manipulation in Aspose.Tasks
linktitle: Currency Symbols Manipulation in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 12
url: /java/currency/currency-symbols/
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



import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;


public class CurrencySymbols {
    public static void main(String[] args) {
        settingCurrencySymbol();

        gettingCurrencySymbol();

        //Display result of conversion.
        System.out.println("Process completed Successfully");
    }

    public static void settingCurrencySymbol() {
        Project project = new Project();
        project.set(Prj.CURRENCY_SYMBOL, "$$");
    }

    public static void gettingCurrencySymbol() {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project project = new Project(dataDir + "project.mpp");
        System.out.println(project.get(Prj.CURRENCY_SYMBOL));
    }
}





```
