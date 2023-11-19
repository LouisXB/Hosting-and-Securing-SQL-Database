## Hosting-and-Securing-SQL-Database

### Description
In this project I hosted an Azure SQL Database on an Azure SQL server and secured the database using various techniques.

### Creating a resource group
To kick things off, I started by creating a resource group from within the Azure portal named "SQLproject01" that would house all my subsequent Azure resources created throughout this project.

### Creating a SQL Server
From the Azure portal, I first created a standard SQL server with SQL authentication.

### Creating a SQL Database hosted on the SQL server
Within the SQL server in the azure portal, I proceeded to create a cost optimized SQL database with the following:
- Serverless compute tier
- 1 vCore
- Data max size: 2GB
- Zone Reduntant: NO
![sqlprojectdashboard 01](https://github.com/LouisXB/Hosting-and-Securing-SQL-Database/assets/115196076/d79c30d9-fd23-416e-8666-19c23efc7f86)

### Configuring alerts and action group
Next I configured alerts and an action group to notify me via email, sms and discord webhook if my utilization exceeded my defined threshold.
</b>
<br />
<br />
![alertrule](https://github.com/LouisXB/Hosting-and-Securing-SQL-Database/assets/115196076/b697ff30-40ae-43f2-aa50-9936416c4fa1)

### Creating a virtual network
Establishing a virtual network allowed me to limit public network access to my Azure SQL database by using virtual network access. This made it so that my SQL database is only accessible from my virtual network.
![virtual network](https://github.com/LouisXB/Hosting-and-Securing-SQL-Database/assets/115196076/7db0641a-b903-4df7-952f-8594606aa9a8)

### Deploying a private endpoint
Creating a private endpoint adds an extra layer of security by making it so that we don't have to go outside of our virtual network for things like DNS request. This was accomplished by configuring Private DNS integration within our private endpoint.
![private endpoint](https://github.com/LouisXB/Hosting-and-Securing-SQL-Database/assets/115196076/f550a86d-98ee-42c0-a14e-9972d12fa859)

### Configuring auditing within SQL server
My next step was the enable auditing to monitor executed queries and changes to my data.

### Viewing and Querying Sample database withing SQL Server Managament Studio
Downloaded SQL Server Management Studio and connected my SQL server. I utilized server level firewall rules to enable access to my database from my client IP. After connecting my server to SSMS i was able to view and query the sample data within the database as shown below.
</b>
<br />
<br />
![sqlmanagementconsole](https://github.com/LouisXB/Hosting-and-Securing-SQL-Database/assets/115196076/c2660a3b-1a53-4c01-b408-8869e57c9436)

### Viewing activity from audit log query
After performing actions within the database, I was able to see activitiy through the audit logs set up earlier. From a security perspective, this is essential for monitoring and investigation and changes to data.
![auditlogquery](https://github.com/LouisXB/Hosting-and-Securing-SQL-Database/assets/115196076/c7f1fc61-341a-42c5-a7dc-11444353a93a)
![Sqllog](https://github.com/LouisXB/Hosting-and-Securing-SQL-Database/assets/115196076/f49ff0bc-eb06-4673-84d1-3e29eee619c2)



