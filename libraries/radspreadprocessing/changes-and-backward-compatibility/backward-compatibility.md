---
title: Backwards Compatibility
page_title: Backwards Compatibility
slug: radspreadprocessing-backwards-compatibility
tags: backward,compatibility
published: True
position: 1
---

# Backward Compatibility



This article will list the breaking changes and how they can be fixed when upgrading from a specific version of the controls to the next one.
## What's Different in 2023 R1

### Changed

 Removed obsolete method void Add(SeriesBase series) of SeriesCollection&lt;T&gt;.

 ### What to do now
 
 Use the other overrides instead.

## What's Different in 2022 R3

### Changed
 
The parameterless constructors of the following classes are obsoleted:
* TwoColorScaleValueContext 
* ThreeColorScaleValueContext 
* FiveIconSetValueContext 
* FourIconSetValueContext 
* ThreeIconSetValueContext 

### What to do now
 
 Use the constructor with parameters instead.

### Changed

The __UpdateConditionalFormattingCellRanges__ method is marked obsolete.

### What to do now

Use use the combination of __RemoveConditionalFormatting__ and __AddConditionalFormatting__ instead.
## What's Different in 2022 R2

### Changed

The following types are now moved to the namespace *Telerik.Windows.Documents.Spreadsheet.Model.ConditionalFormattings*:

- Telerik.Windows.Documents.Spreadsheet.Model.ConditionalFormatting
- Telerik.Windows.Documents.Spreadsheet.Model.DataBarAxisPosition
- Telerik.Windows.Documents.Spreadsheet.Model.PresetIconSet
- Telerik.Windows.Documents.Spreadsheet.Model.IconDefinition

### What to do now

Change the full name of the types:

- Telerik.Windows.Documents.Spreadsheet.Model.ConditionalFormattings.ConditionalFormatting
- Telerik.Windows.Documents.Spreadsheet.Model.ConditionalFormattings.DataBarAxisPosition
- Telerik.Windows.Documents.Spreadsheet.Model.ConditionalFormattings.PresetIconSet
- Telerik.Windows.Documents.Spreadsheet.Model.ConditionalFormattings.IconDefinition

### Changed

IconSetRule.IsReversed is now read-only.

### What to do now

You can set the IsReversed property through the constructor of IconSetRule.

### Changed

Telerik.Windows.Documents.Spreadsheet.Model.FilteredShapeCollection.Changing event's arguments type changed from ___ShapeCollectionChangedEventArgs___ to ___ShapeCollectionChangingEventArgs___.


### What to do now

You can replace the old event arguments type with the new one.


## What's Different in 2019 R2

### Changed

**Values** and **Categories** properties are moved from **SeriesBase** to **CategorySeriesBase** class.

### What to do now

Use the properties exposed in **CategorySeriesBase**.

## What's Different in 2019 R1 SP1

### Changed

**IPdfChartRenderer** now uses **FloatingChartShape** instead of **DocumentChart**. FloatingChartShape contains UI information for chart like Width/Height/Outline/Fill.

### Changed

The method **GetBitmapSourceFromChartModel()** in **ChartModelToImageConverter** is **deleted**. 

### What to do now

You can now use **GetBitmapSourceFromFloatingChartShape** methods which accepts **FloatingChartShape** instead of **DocumentChart**. There is an example in our SDK repository showing a possible approach: [Export Chart](https://github.com/telerik/document-processing-sdk/tree/master/SpreadProcessing/ExportChart).

## What's Different in 2018 R2

### Changed

The default value of Telerik.Windows.Documents.Spreadsheet.Model.Printing.SheetPageSetupBase::**PaperType** has been changed from `A4` to `Letter`.

### What to do now

If you need to keep the document with A4 PaperType, you can apply this setting before exporting it:

#### [C#] Set PaperType
{{region radspreadprocessing-backward-compatibility_0}}

	foreach (Worksheet worksheet in workbook.Worksheets)
	{
		worksheet.WorksheetPageSetup.PaperType = PaperTypes.A4;
	}

{{endregion}}


## What's Different in 2016 R3  


### Changed

Assemblies with a version number ending with .45 suffix are **not** distributed.

### What to do now

Use the assemblies with a version number ending with .40 suffix. The library doesn't contain code specific for .NET Framework 4.5, thus an additional version is not needed.


## What's Different in 2016 Q1

### Changed

**Telerik.Windows.Maths.dll** is removed and integrated in Telerik.Windows.Documents.Spreadsheet.

### Changed

Telerik.Windows.Maths::**InterpolationExtensions** is now internal.

### Changed

Telerik.Windows.Maths::**RVector** is now internal.

### Changed

Telerik.Windows.Documents.Spreadsheet.Expressions.Functions::**FunctionBase.Evaluate(RadExpression[] arguments)** method is obsolete.

### What to do now

Use Telerik.Windows.Documents.Spreadsheet.Expressions.Functions::**FunctionBase.Evaluate(FunctionEvaluationContext context)** instead.

### Changed

Telerik.Windows.Documents.Spreadsheet.Expressions.Functions::**FunctionBase.EvaluateOverride(RadExpression[] arguments)** is obsolete.

### What to do now

Use Telerik.Windows.Documents.Spreadsheet.Expressions.Functions::**FunctionBase.EvaluateOverride(FunctionEvaluationContext context)** instead.


### Changed

Telerik.Windows.Documents.Spreadsheet.Expressions.Functions::**FunctionWithArguments.EvaluateOverride(object[] arguments)** is obsolete.

### What to do now

Use Telerik.Windows.Documents.Spreadsheet.Expressions.Functions::**FunctionWithArguments.EvaluateOverride(FunctionEvaluationContext&lt;object&gt; context)** instead.

### Changed

Telerik.Windows.Documents.Spreadsheet.Expressions.Functions::**FunctionWithSameTypeArguments&lt;T&gt;.EvaluateOverride(T[] arguments)** instead.

### What to do now

Use Telerik.Windows.Documents.Spreadsheet.Expressions.Functions::**FunctionWithSameTypeArguments&lt;T&gt;.EvaluateOverride(FunctionEvaluationContext&lt;T&gt; context)** instead.



## What's Different in 2015 Q2

### Changed

Telerik.Windows.Documents.Spreadsheet.Layout.Layers.WorksheetRenderUpdateContext::__ViewportPaneTypeToVisibleCellBoxes__ property is removed.

### What to do now

Use Telerik.Windows.Documents.Spreadsheet.Layout.Layers.WorksheetRenderUpdateContext::__VisibleCellLayoutBoxes__ property instead.


### Changed

Telerik.Windows.Documents.Spreadsheet.Measurement.__FontManager__ is removed.

### What to do now

Use Telerik.Windows.Documents.Core.Fonts.__SystemFontsManager__ class instead.


### Changed

Telerik.Windows.Documents.Spreadsheet.Model.SpreadsheetNameCollectionScope::__Name__ property is removed.


### Changed

Telerik.Windows.Documents.Spreadsheet.Model.SelectionState::__SelectionState(IEnumerable selectedRanges, CellIndex activeCellIndex)__ constructor is removed.


### Changed 

Use Telerik.Windows.Documents.Spreadsheet.Model.SelectionState::__SelectionState(IEnumerable selectedRanges, CellIndex activeCellIndex, ViewportPaneType pane)__ constructor instead.


### Changed

Telerik.Windows.Documents.Spreadsheet.Utilities.UnitHelper::__EMUsToDIP(int value)__ is removed.

### What to do now

Use __EmuToDip(double value)__ method instead.



## What's Different in 2014 Q3

### Changed

The default value of the IsEnabled property of the WorkbookHistory class is changed to false.
        

### What to do now

You can enable the history of a Workbook by setting the property to true.
        

### Changed

The Width, Height and RotationAngle properties of the FloatingShapeBase class no longer update the CellIndex, OffsetX and OffsetY properties.
        

### What to do now

If it is necessary for them to be updated automatically, the SetWidth, SetHeight and SetRotationAngle methods can be used instead with the bool adjustCellIndex parameter set to true.
        

### Changed

String Name property of SpreadsheetNameCollectionScope is marked obsolete.
        

### What to do now

The property is related to the RadSpreadsheet UI control and is not used in the processing library.
        
