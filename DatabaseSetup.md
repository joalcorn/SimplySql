# Database Setup for Testing

## MSSQL

1. Download [Sql Server 2017 Express](https://www.microsoft.com/en-us/sql-server/sql-server-editions-express)
1. Make sure to install in "Mixed Mode"
1. Set password for SA account (default it to 'password1', if isolated)
1. Create user with dbcreator rights
    ```sql
    CREATE LOGIN test WITH PASSWORD = 'test'
    ALTER SERVER ROLE dbcreator ADD MEMBER test
    ```
1. Make sure that the `SQL Server Browser` service is running
1. Make sure that the `TCP/IP` protocol is enabled (Sql Server Configuration Manager > Sql Server Network Configuration > Protocols for SQLEXPRESS)

## Oracle

1. Download [Oracle 11g XE](https://www.oracle.com/database/technologies/xe-prior-releases.html)
1. Install, use `password` as the password for sysadmin, etc.
1. run SQLPLUS, login as `system`, run following sql
    ```sql
    ALTER USER hr IDENTIFIED BY hr ACCOUNT UNLOCK;
    ```