---
title: Creating a Table from Scratch in Slide in Python
type: docs
weight: 30
url: /java/creating-a-table-from-scratch-in-slide-in-python/
---

## **Aspose.Slides - Creating a Table from Scratch in Slide**
To Create a Table from Scratch in Slide using **Aspose.Slides Java for Python**. Here you can see example code.

**Python Code**

```

 pres =  self.Presentation()

\# Get the first slide

sld = pres.getSlides().get_Item(0)

\# Define columns with widths and rows with heights

dblCols = [50, 50, 50]

dblRows = [50, 30, 30, 30, 30]

\# Add table shape to slide

tbl = sld.getShapes().addTable(100, 50, dblCols, dblRows)

fill_type =  self.FillType

color =  self.Color

\# Set border format for each cell

row = 0

while (row < tbl.getRows().size()): 

    cell = 0

    while (cell < tbl.getRows().get_Item(row).size()):

        tbl.getRows().get_Item(row).get_Item(cell).getBorderTop().getFillFormat().setFillType(fill_type.Solid)

        tbl.getRows().get_Item(row).get_Item(cell).getBorderTop().getFillFormat().getSolidFillColor().setColor(color.RED)

        tbl.getRows().get_Item(row).get_Item(cell).getBorderTop().setWidth(5)

        tbl.getRows().get_Item(row).get_Item(cell).getBorderBottom().getFillFormat().setFillType(fill_type.Solid)

        tbl.getRows().get_Item(row).get_Item(cell).getBorderBottom().getFillFormat().getSolidFillColor().setColor(color.RED)

        tbl.getRows().get_Item(row).get_Item(cell).getBorderBottom().setWidth(5)

        tbl.getRows().get_Item(row).get_Item(cell).getBorderLeft().getFillFormat().setFillType(fill_type.Solid)

        tbl.getRows().get_Item(row).get_Item(cell).getBorderLeft().getFillFormat().getSolidFillColor().setColor(color.RED)

        tbl.getRows().get_Item(row).get_Item(cell).getBorderLeft().setWidth(5)

        tbl.getRows().get_Item(row).get_Item(cell).getBorderRight().getFillFormat().setFillType(fill_type.Solid)

        tbl.getRows().get_Item(row).get_Item(cell).getBorderRight().getFillFormat().getSolidFillColor().setColor(color.RED)

        tbl.getRows().get_Item(row).get_Item(cell).getBorderRight().setWidth(5)

        cell+=1

    row+=1


\# Merge cells 1 & 2 of row 1

tbl.mergeCells(tbl.getRows().get_Item(0).get_Item(0), tbl.getRows().get_Item(1).get_Item(0), False)

\# Add text to the merged cell

tbl.getRows().get_Item(0).get_Item(0).getTextFrame().setText("Merged Cells")

\# Write the presentation as a PPTX file

save_format =  SaveFormat

pres.save(self.dataDir + "CreateTable.pptx", save_format.Pptx)

print "Created table, please check the output file."

```
## **Download Running Code**
Download running code from any of the below mentioned social coding sites:

- [CodePlex](https://asposeslidesjavapython.codeplex.com/releases/view/620922)
- [GitHub](https://github.com/aspose-slides/Aspose.Slides-for-Java/releases/tag/Aspose.Slides_Java_for_Python-v1.0)
