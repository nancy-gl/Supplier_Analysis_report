# Supplier_Analysis_report

## Details of the Report
### Data Setup:
  *	After importing the Excel file into Power BI, performed the cleansing of data in Power Query Editor and created data model as follows
  *	Used Power BI tips Theme Generator to copy-paste the HEX codes to generate and download a theme JSON file. But changed it again to custom theme. I was not happy with the color choice in this report but did not change with the amount of time I allocated to practice for this report. 
  *	The snapshot of the report pages looks like below:
  
  ![](https://github.com/nancy-gl/Supplier_Analysis_report/blob/main/images/Combined.png)

### Data Model:
  *	Imported [SupplierData.xlsx] as a staging query and created references in new [Data Model] group.
  *	Separated fact table [SupplierQuality] and dimension tables [Category], [MaterialType], [DefectType], [Defect], [Plant], [Vendors] and [Date]
  *	Applied ETL to merge queries, remove duplicates, custom columns, round for necessary transformations
  *	Hid all the Primary, Foreign Keys from the model
  *	Added blank tables for [Key Measures], [Narrative Measures], [Ranking Measures]
  *	Created Last refresh table to store the latest refresh date for the report for administration
  *	Created “Top N” What-if parameter to make analysis of top N (N Being dynamic in the range of 1 to 30) worst [Category], [Plant], [Material] with respect to Defect Quantity and Downtime minutes.
  *	The raw data in Excel is as follows:
  
  ![](https://github.com/nancy-gl/Supplier_Analysis_report/blob/main/images/Excel%20Raw.png)
  
  * Separating the fact table and dimension tables, the Power BI model is as shown
  
  ![](https://github.com/nancy-gl/Supplier_Analysis_report/blob/main/images/Data%20Model.png)
  
### Visuals:
  *	added three report pages for [Overview], [Plant/Vendor], [Details]
  *	[Overview] page
      *	added report pages for [Overview], [Plant/Vendor], [Details]
      *	hid all pages except for [Overview] page 
      *	added buttons for page navigation to [Plant/Vendor], [Details], [Overview]
      *	added multi-card visual to show some important numbers
      *	used smart narrative text box to show static notes and dynamic measures, for best and worst performing Plants, Vendors, Category and Materials.
      *	used standard scatter chart to show defect quantity and downtime minutes by Plant (linear x-axis and y-axis) and implemented clustering to group the plants for better visualization of good and bad performers
      *	used standard scatter chart to show defect quantity and downtime minutes by Vendor (changed axes to log x-axis and y-axis for better visualization) and implemented clustering to group the vendors for better visualization of good and bad performers
      *	used standard scatter chart to show defect quantity and downtime minutes by Category (linear x-axis and y-axis)
      *	used standard scatter chart to show defect quantity and downtime minutes by Material Type (log x-axis and y-axis)
      *	added Last Refresh Date to make a note of data refresh administration
      *	added report tooltip on scatter chart of Plant and Vendor for more information on plant and vendor
      *	added slicer to filter data by year, quarter and month
      *	The overview page is shown below
      
      ![](https://github.com/nancy-gl/Supplier_Analysis_report/blob/main/images/Overview.png)
      
      * The tooltip for vendor shows the rank of the vendor among all in terms of defect quantity and downtime measures as shown below

      ![](https://github.com/nancy-gl/Supplier_Analysis_report/blob/main/images/Overview-tooltip.png)
  
  * [Plant/Vendor] page:
      * Used muti-card visual to highlight the worst 3 plant based on defect quantity
      *	Used bar charts to view the top N worst performing category, material and plant
      *	Used Top N what if parameter slicer to make dynamic selection 
      *	Added two buttons for Defect Qty and Downtime Mins to control the bar chart measure selection
      *	Used bookmark to layer bar chart visuals on top, based on the selection
      *	Added Vendor slicer for this page to analyze vendor behavior on category, material and plant
      
      ![](https://github.com/nancy-gl/Supplier_Analysis_report/blob/main/images/Plants.png)

  *	[Details] page:
      *	used line chart to show the relationship between defect quantity and downtime minutes for the date periods as selected by slicer to see the trends
      *	added average line to analyze the deflection from it at different periods
      *	used slicer for year, defect type, material, plant and vendor dimension to slice the data
      *	used table visual to show the detail for the slicer selections, calculated days of downtime from downtime minutes to include in the table visual 
      *	used “reset” button to easily clear all slicer selections

      ![](https://github.com/nancy-gl/Supplier_Analysis_report/blob/main/images/Detail.png)
      
## [Click here to view the report on the web.](https://app.powerbi.com/reportEmbed?reportId=e11c141f-efa1-4626-b3cd-f27bbc7ae9c6&autoAuth=true&ctid=3fb43f9e-f396-473f-bdb4-7b116a3228ce&config=eyJjbHVzdGVyVXJsIjoiaHR0cHM6Ly93YWJpLXdlc3QtdXMtYi1wcmltYXJ5LXJlZGlyZWN0LmFuYWx5c2lzLndpbmRvd3MubmV0LyJ9) 

