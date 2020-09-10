# AIC2020-Unzip-By-Coding-Warriors
This repository contains code that are used for demonstration of the key functions in our proposed solution - UNZIP - for AIC Challenge.

# QR Code Generator
It is an html file which contains a simplified version of invoice.

After downloading the file, one can open it and key in the information in the fields. Then click on the "Generate QR Code button" to generate a QR code for the invoice information that is just filled.

The new QR code will contain all the information and using a QR code decoder and Iphone camera, the information coded in the QR code can be seen.

# Invoice Vouching Demo
It is a file that demonstrates how information can be extracted from invoice and how the information can be subsequently used in audit procedures to verify the transactions.

**Code chunk 1 (Function to extract information)**

The extract_info function is created to extract relevant information from the invoices. The search area is predefined and its dimensions are extracted using tabulizer::locate_areas() and stored in the variable "area". After which the tabulizer::extract_tables() is used to extract information within the search area into a dataframe (raw_df). The "Total.Due" column contains the total amount listed in the invoice, which is further cleaned by removing '$' and ',' characters such that it can be converted into a numeric value.

**Code chunk 2 (Extracting information from all Invoices)**

Here, we will initialise a variable (Invoices) to contain all of the file names with the ".pdf" suffix. We then run a for loop through all of the invoices and applying extract_info() function to all of the invoices, while consolidating the data into a single dataframe (invoices_df).

**Code chunk 3 (Analyzing Client's financial data)**

Here, we stipulate how a company will store its financial data into a table format within excel. We purposely included some common errors that might adversely affect audit quality if left unnoticed (incorrect data entry, messy data formatting, missing records etc.).

**Code chunk 4 (Output an excel file which contains errors in Client's financial data)**

We will clean the Total.Due column from the client's financial data to account for  the messy data formatting. After which, we will leverage on 2 anti-joins to capture all entries which contain errors and also missing entries - these are then combined using a full join (combined_df) .

Lastly, we filtered out duplicated errors highlighted in combined_df and output the results in a new excel file ("Error_Summary.xlsx").

**Thank you!**


