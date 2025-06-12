---
title: "Aspose.Tasks .NET&#58; Managing Task Attributes with Lookup Values"
description: "Learn how to use Aspose.Tasks for .NET to create and manage task attributes, including text, cost, date, number, and duration, with lookup values. Enhance project management efficiency and decision-making."
date: "2025-06-10"
weight: 1
url: "/net/custom-fields-properties/mastering-aspose-tasks-dotnet-task-attributes/"
keywords:
- Aspose.Tasks .NET
- task attributes
- lookup values
- manage project tasks
- extended attributes

---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}
# Mastering Aspose.Tasks .NET: Creating and Managing Task Attributes with Lookup Values

## Introduction

Managing project tasks efficiently is a cornerstone of successful project management. With the right tools, you can enhance task tracking, reporting, and resource allocation. This tutorial focuses on using **Aspose.Tasks for .NET** to create and manage extended attributes with lookup values for tasks. By leveraging these features, you'll gain precise control over your projects' data, leading to more informed decision-making.

### What You’ll Learn

- How to create and add text, cost, date, number, and duration attributes using Aspose.Tasks .NET.
- Assigning lookup values to extended task attributes for better project management.
- Saving a project with updated extended attributes in MPP format.
- Practical applications of these features in real-world scenarios.

Let's delve into the prerequisites before diving into the implementation details.

## Prerequisites

Before you begin, ensure you have the following:

- **Aspose.Tasks for .NET** library: You need to install this package. It can be added via .NET CLI or NuGet Package Manager.
- A development environment: Visual Studio is recommended for C# projects.
- Basic knowledge of C# and project management principles.

## Setting Up Aspose.Tasks for .NET

### Installation

You can add the **Aspose.Tasks** library to your project using different methods:

#### .NET CLI
```bash
dotnet add package Aspose.Tasks
```

#### Package Manager
```powershell
Install-Package Aspose.Tasks
```

#### NuGet Package Manager UI
Search for "Aspose.Tasks" in the NuGet Package Manager and install the latest version.

### License Acquisition

To fully utilize Aspose.Tasks, you can acquire a temporary license or purchase one. Start with a free trial to explore its capabilities:

- **Free Trial**: Available at [Aspose Tasks Free Releases](https://releases.aspose.com/tasks/net/)
- **Temporary License**: Obtain through [Aspose Temporary License Page](https://purchase.aspose.com/temporary-license/)
- **Purchase**: Visit the [Aspose Purchase Page](https://purchase.aspose.com/buy) for detailed options.

### Basic Initialization

Once installed, include the necessary namespace in your C# files:

```csharp
using Aspose.Tasks;
```

Now you're ready to start implementing extended attributes using Aspose.Tasks .NET.

## Implementation Guide

We'll break down the implementation into specific features, each focusing on a particular type of attribute.

### Feature 1: Create and Add Text3 Extended Attribute with Lookup Values

This feature demonstrates how to define a text-based extended attribute for tasks with lookup values.

#### Overview

Creating text attributes allows you to categorize or tag tasks with predefined labels, enhancing searchability and organization within your project plan.

```csharp
using Aspose.Tasks;

// Create the Text3 attribute definition
ExtendedAttributeDefinition taskTextAttributeDefinition = ExtendedAttributeDefinition.CreateLookupTaskDefinition(ExtendedAttributeTask.Text3, "New text3 attribute");
taskTextAttributeDefinition.ElementType = ElementType.Task;

// Define a lookup value for the Text3 attribute
Value textVal = new Value();
textVal.Id = 1;
textVal.Description = "Text value descr";
textVal.Val = "Text value1";
taskTextAttributeDefinition.AddLookupValue(textVal);
```

#### Explanation

- `CreateLookupTaskDefinition`: Initializes a new lookup task definition.
- `ExtendedAttributeTask.Text3`: Specifies the type of text attribute.
- `AddLookupValue`: Adds predefined values to your attribute, facilitating easier categorization.

### Feature 2: Create and Add Cost1 Extended Attribute with Lookup Values

Here we'll add cost attributes that can help in budget tracking and financial planning within projects.

#### Overview

Assigning costs to tasks helps in maintaining a clear overview of project expenses, allowing for better financial management.

```csharp
using Aspose.Tasks;

// Define the Cost1 attribute
ExtendedAttributeDefinition taskCostAttributeDefinition = ExtendedAttributeDefinition.CreateLookupTaskDefinition(ExtendedAttributeTask.Cost1, "New cost1 attribute");

// Add multiple lookup values to represent different costs
Value costVal1 = new Value();
costVal1.Id = 2;
costVal1.Description = "Cost value 1 descr";
costVal1.Val = "99900";

Value costVal2 = new Value();
costVal2.Id = 3;
costVal2.Description = "Cost value 2 descr";
costVal2.Val = "11100";
taskCostAttributeDefinition.AddLookupValue(costVal1);
taskCostAttributeDefinition.AddLookupValue(costVal2);
```

#### Explanation

- `CreateLookupTaskDefinition`: Initializes a new cost attribute for task definition.
- `ExtendedAttributeTask.Cost1`: Indicates the use of a cost-related attribute.

### Feature 3: Add Task and Assign Attribute Lookup Value

Learn how to assign these newly created lookup values to specific tasks within your project.

#### Overview

Assigning attributes directly to tasks ensures that each task has all necessary metadata, improving clarity and communication across teams.

```csharp
using Aspose.Tasks;

// Create a new task in the project
Task task = project.RootTask.Children.Add("New task");

// Assign the cost attribute lookup value to the task
ExtendedAttribute taskAttr = taskCostAttributeDefinition.CreateExtendedAttribute(costVal1);
task.ExtendedAttributes.Add(taskAttr);
```

#### Explanation

- `RootTask.Children.Add`: Adds a new task under the root of your project.
- `CreateExtendedAttribute`: Generates an extended attribute instance for assignment.

### Feature 4: Create Start7 Attribute with Lookup Value

This feature focuses on date-based attributes, crucial for scheduling and tracking task timelines.

#### Overview

Using start date attributes allows teams to track when tasks are planned to begin, enhancing schedule management.

```csharp
using Aspose.Tasks;

// Define the Start7 attribute for task start dates
ExtendedAttributeDefinition taskStartAttributeDefinition = ExtendedAttributeDefinition.CreateLookupTaskDefinition(ExtendedAttributeTask.Start7, "New start 7 attribute");

// Add a lookup value representing today's date
Value startVal = new Value();
startVal.Id = 4;
startVal.DateTimeValue = DateTime.Now;
startVal.Description = "Start 7 value description";
taskStartAttributeDefinition.AddLookupValue(startVal);
```

#### Explanation

- `DateTimeValue`: Sets the specific date for a task attribute, useful for scheduling.

### Feature 5: Create Finish4 Attribute with Lookup Value

Similar to Start7, this feature demonstrates managing finish dates for tasks.

#### Overview

Tracking when tasks are expected to be completed helps in assessing project progress and identifying potential delays.

```csharp
using Aspose.Tasks;

// Define the Finish4 attribute for task end dates
ExtendedAttributeDefinition taskFinishAttributeDefinition = ExtendedAttributeDefinition.CreateLookupTaskDefinition(ExtendedAttributeTask.Finish4, "New finish 4 attribute");

// Assign a lookup value with today's date as an example
Value finishVal = new Value();
finishVal.Id = 5;
finishVal.DateTimeValue = DateTime.Now;
finishVal.Description = "Finish 4 value description";
taskFinishAttributeDefinition.ValueList.Add(finishVal);
```

#### Explanation

- `ValueList.Add`: Adds a specific date to the attribute's list of possible values.

### Feature 6: Create and Add Number Attribute with Lookup Values

Number attributes can be used for various categorizations, such as priority levels or resource allocation codes.

#### Overview

Using numerical attributes allows for easy sorting and filtering within project management software, enhancing data analysis capabilities.

```csharp
using Aspose.Tasks;

// Define a number attribute with multiple lookup values
ExtendedAttributeDefinition numberAttributeDefinition = ExtendedAttributeDefinition.CreateLookupTaskDefinition(ExtendedAttributeTask.Number20, "New number attribute");

// Add several numbers as lookup values
Value val1 = new Value();
val1.Id = 6;
val1.Val = "1";
val1.Description = "Number 1 value";

Value val2 = new Value();
val2.Id = 7;
val2.Val = "2";
val2.Description = "Number 2 value";

Value val3 = new Value();
val3.Id = 8;
val3.Val = "3";
val3.Description = "Number 3 value";
numberAttributeDefinition.AddLookupValue(val1);
numberAttributeDefinition.AddLookupValue(val2);
numberAttributeDefinition.AddLookupValue(val3);
```

#### Explanation

- `CreateLookupTaskDefinition`: Initializes a new number attribute.
- `Val`: Represents the numerical value of the lookup.

### Feature 7: Create and Add Resource Start5 Attribute with Lookup Value

Resource management is crucial in project planning, and this feature aids in tracking resource allocation dates.

#### Overview

Assigning start dates to resources ensures they are available when needed, preventing scheduling conflicts.

```csharp
using Aspose.Tasks;

// Define the Start5 attribute for resource start dates
ExtendedAttributeDefinition resourceStartAttributeDefinition = ExtendedAttributeDefinition.CreateLookupResourceDefinition(ExtendedAttributeResource.Start5, "New start5 attribute");

// Add a lookup value with today's date as an example
Value startVal2 = new Value();
startVal2.Id = 9;
startVal2.DateTimeValue = DateTime.Now;
startVal2.Description = "this is start5 value descr";
resourceStartAttributeDefinition.AddLookupValue(startVal2);
```

#### Explanation

- `CreateLookupResourceDefinition`: Sets up a resource-specific attribute.
- `ExtendedAttributeResource.Start5`: Specifies the use of a date-related attribute for resources.

### Feature 8: Define Duration Attribute without Lookup

Managing task durations is essential for timeline estimation and workload balancing.

#### Overview

Defining duration attributes helps in tracking how long tasks are expected to take, aiding in resource planning.

```csharp
using Aspose.Tasks;

// Create a duration attribute definition
ExtendedAttributeDefinition taskDurationAttributeDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Duration1, "New Duration");
```

#### Explanation

- `CreateTaskDefinition`: Initializes a new duration attribute for tasks without predefined values.

### Feature 9: Add Task and Assign Duration Value to the Defined Attribute

Assigning specific durations to tasks ensures that each task's time requirements are clearly defined.

```csharp
using Aspose.Tasks;

// Create a new task in the project
Task timeTask = project.RootTask.Children.Add("New task");

// Assign a duration value to the task's extended attribute
ExtendedAttribute durationExtendedAttribute = taskDurationAttributeDefinition.CreateExtendedAttribute();
durationExtendedAttribute.DurationValue = project.GetDuration(3.0, TimeUnitType.Hour);
timeTask.ExtendedAttributes.Add(durationExtendedAttribute);
```

#### Explanation

- `GetDuration`: Calculates the duration based on hours or other time units.

### Feature 10: Save Project with Updated Attributes

Finally, save your project to preserve all changes and attributes added.

```csharp
using Aspose.Tasks;

// Save the project with updated attributes in MPP format
project.Save("UpdatedProject.mpp", SaveFileFormat.MPP);
```

#### Explanation

- `Save`: Stores the current state of your project file, including all modifications made during the session.

## Practical Applications

These features can be applied in various scenarios:

- **Budget Tracking**: Use cost attributes to monitor expenses against the budget.
- **Scheduling**: Date and duration attributes help manage timelines effectively.
- **Resource Allocation**: Resource start dates prevent conflicts and ensure optimal utilization.
- **Task Prioritization**: Number attributes can represent priority levels for tasks.

## Conclusion

By implementing these features using Aspose.Tasks .NET, you enhance your project management capabilities. This guide provides a comprehensive approach to defining and assigning extended attributes within projects, ensuring better organization, tracking, and resource management. With practical applications in budgeting, scheduling, and more, these techniques are invaluable for efficient project execution.

For further details on Aspose.Tasks features, refer to the [official documentation](https://docs.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}