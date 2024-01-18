Certainly! Here is a template for the README section of your project:

---

# Invoice Processing Workflow

## Use-case/Problem Statement

You often receive invoices in the form of scanned PDF files through email. Your task is to automate the extraction of the Date and Total from these invoices and save them into an Excel file.

## Project Dependencies

Ensure the following dependencies are installed:

- UiPath.PDF.Activities
- UiPath.Excel.Activities
- UiPath.System.Activities
- UiPath.UiAutomation.Activities


## Approach

To accomplish this task, we can follow these steps:

1. **Install Dependencies**
   - Install the UiPath.PDF.Activities package.
   
2. **Extract Data from PDFs**
   - Use the Read PDF With OCR activity to retrieve the Date and Total values from the scanned PDF files.
   
3. **Save Extracted Data to Excel**
   - Utilize the Write Range Workbook activity to store the extracted data from all PDF invoices into an Excel file.

## Solution Steps

1. **Copy Invoice Files**
   - Copy the invoice files to the `Data` folder in the Project folder.

2. **Rename Sequence**
   - Rename the Sequence in the designer panel to provide an appropriate name and description.

3. **Assign Folder Path**
   - Add an Assign activity to create a string variable called `FolderPath` containing the folder path to the PDF files.

4. **Build Data Table**
   - Add a Build Data Table activity to create a new Data Table with the Invoice Date and Invoice Total columns. Save the output as `dt_DataTable`.

5. **Process PDF Files**
   - Add a For Each File in Folder activity to iterate through all the PDF files.
   - Use the Read PDF With OCR activity to extract text from the PDF.
   - Extract the Date and Total values using Text to Left/Right and Modify Text activities.
   - Use the Add Data Row activity to store the extracted data in the `dt_DataTable`.

6. **Write to Excel**
   - Use the Write Range Workbook activity to write the data into an Excel file.
   - Provide the workbook path as "Report.xlsx" and specify the sheet name as "Sheet1" with the starting cell "A1".
   - Check the "Add Headers" option under Properties Panel to include headers in the Excel file.


## Notes

Make sure to adjust file paths, separators, and other parameters as needed for your specific use case.

---

Feel free to customize the template based on additional details or specific requirements for your project.
