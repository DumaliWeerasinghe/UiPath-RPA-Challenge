# UiPath-RPA-Challenge
This automation navigates to the UiPath RPA Challenge page, downloads the Excel file, and fills out the form on the page using the data from the file. It submits the form for each row of data in the Excel file until all entries are completed.

Process Description:
This automation is developed using the UiPath REFramework.

Initialization State:
The process starts by reading the Config file, which is located in the default path: \Data\Config.xlsx inside the project folder.
It then kills any unwanted processes (e.g., chrome, excel) before starting the automation.
The names of the processes to be terminated are specified in the Config file, making it easy to update without modifying the code.
After cleanup, the bot navigates to the RPA Challenge website.
The URL is also provided in the Config file.
The browser to be used (e.g., chrome or msedge) is configurable — simply update the Browser value in the Config file to switch.

Get Transaction Data State:
The bot downloads the Excel file from the RPA Challenge page.
It then reads the downloaded Excel file and stores the data in a DataTable, which is used as the source for Transaction Items.

Process Transaction State:
For each transaction (i.e., each row of data), the bot fills in the form on the RPA Challenge page using the corresponding data from the Excel file.
The form is submitted after each entry.

End Process State:
The bot closes the browser that was opened during the process.
Finally, an auto-close message box appears to notify the user that the automation has successfully completed.
