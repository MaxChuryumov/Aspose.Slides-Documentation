---
title: Vertically align the text in table cell in Ruby
type: docs
weight: 50
url: /java/vertically-align-the-text-in-table-cell-in-ruby/
---

## **Aspose.Slides - Vertically align the text in table cell**
To Vertically align the text in table cell using **Aspose.Slides Java for Ruby**, simply invoke **AlignText** module. Here you can see example code.

**Ruby Code**

```

 data_dir = File.dirname(File.dirname(File.dirname(File.dirname(__FILE__)))) + '/data/Tables/'



\# Create an instance of Presentation class

pres = Rjb::import('com.aspose.slides.Presentation').new

\# Get the first slide

slide = pres.getSlides().get_Item(0)

\# Define columns with widths and rows with heights

dbl_cols = [120, 120, 120, 120]

dbl_rows = [100, 100, 100, 100]

\# Add table shape to slide

tbl = slide.getShapes().addTable(100, 50, dbl_cols, dbl_rows)

\# Add text to the merged cell

tbl.getRows().get_Item(0).get_Item(1).getTextFrame().setText("10")

tbl.getRows().get_Item(0).get_Item(2).getTextFrame().setText("20")

tbl.getRows().get_Item(0).get_Item(3).getTextFrame().setText("30")

\# Accessing the text frame

txt_frame = tbl.getRows().get_Item(0).get_Item(0).getTextFrame()

\# Create the Paragraph object for text frame

para = txt_frame.getParagraphs().get_Item(0)

\# Create Portion object for paragraph

portion = para.getPortions().get_Item(0)

portion.setText("Text here")

portion.getPortionFormat().getFillFormat().setFillType(Rjb::import('com.aspose.slides.FillType').Solid)

portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Rjb::import('java.awt.Color').BLACK)

\# Aligning the text vertically

cell = tbl.getRows().get_Item(0).get_Item(0)

cell.setTextAnchorType(Rjb::import('com.aspose.slides.TextAnchorType').Center)

cell.setTextVerticalType(Rjb::import('com.aspose.slides.TextVerticalType').Vertical270)

\# Write the presentation as a PPTX file

save_format = Rjb::import('com.aspose.slides.SaveFormat')

pres.save(data_dir + "AlignText.pptx", save_format.Pptx)

puts "Aligned Text, please check the output file."

```
## **Download Running Code**
Download **Vertically align the text in table cell (Aspose.Slides)** from any of the below mentioned social coding sites:

- [GitHub](https://github.com/aspose-slides/Aspose.Slides-for-Java/blob/master/Plugins/Aspose_Slides_Java_for_Ruby/lib/asposeslidesjava/Tables/aligntext.rb)
