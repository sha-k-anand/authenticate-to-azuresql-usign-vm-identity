# Connect to Azure SQL using Azure VMs identity

Many organizations do not approve the use of SQL logins to Database due to various security concerns.


If your application that connects to Azure SQL DB or SQL MI is running on an Azure VM. You can avoid  SQL Logins and use the VMs identity to connect to Azure SQL DB/SQL MI.

Here are the steps (refer to screenshots below for more info)
1. Activate Managed Identity on Azure VM
2. Download ODBC Driver 17 on the VM
3. Grant VM identity access to Azure SQL DB or SQL MI (using external provider)
4. Setup a ODBC Datasource using ODBC 17
5. Update application connection string 


Applciation Connection string 
    "DSN=odbc17azuresqldb;Authentication=ActiveDirectoryMsi"

If application connection string change is not possible, update the windows registry to set the Authentication=ActiveDirectoryMsi parameter on the ODBC DSN

ODBC Driver 17 - https://www.microsoft.com/en-us/download/details.aspx?id=56567

MSI Auth - https://docs.microsoft.com/en-us/sql/connect/jdbc/connecting-using-azure-active-directory-authentication?view=sql-server-ver15



# Screenshots

![Activate VM Identity](/screenshots/Screenshot133951.jpeg)

![Grant VM Identity access to Azure SQL](/screenshots/Screenshot134049.jpg)

![ODBC Setup 1](/screenshots/Screenshot134049.jpg)

![ODBC Setup 2](/screenshots/Screenshot135701.jpg)

![Registry Setup](/screenshots/Screenshot135809.jpg)

