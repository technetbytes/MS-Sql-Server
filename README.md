### In Both Juypter Notebook we share code through which we establish connectivity to <br>MS SQL Server from Ubuntu.

### Using Libraries
      ODBC Driver :- { ODBC Driver 17 for SQL Server }
      pyodbc
      sqlalchemy
      Pandas DataFrame      

 ### Drive Installation (Driver 17)
      sudo su
      curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add -

      #Download appropriate package for the OS version
      #Choose only ONE of the following, corresponding to your OS version

      #Ubuntu 16.04
      curl https://packages.microsoft.com/config/ubuntu/16.04/prod.list > /etc/apt/sources.list.d/mssql-release.list

      #Ubuntu 18.04
      curl https://packages.microsoft.com/config/ubuntu/18.04/prod.list > /etc/apt/sources.list.d/mssql-release.list

      #Ubuntu 19.10
      curl https://packages.microsoft.com/config/ubuntu/19.10/prod.list > /etc/apt/sources.list.d/mssql-release.list

      exit
      sudo apt-get update
      sudo ACCEPT_EULA=Y apt-get install msodbcsql17
      # optional: for bcp and sqlcmd
      sudo ACCEPT_EULA=Y apt-get install mssql-tools
      echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bash_profile
      echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bashrc
      source ~/.bashrc
      # optional: for unixODBC development headers
      sudo apt-get install unixodbc-dev
      
###   /etc/odbcinst.ini like this
      [ODBC Driver 17 for SQL Server]
      Description=Microsoft ODBC Driver 17 for SQL Server
      Driver=/opt/microsoft/msodbcsql17/lib64/libmsodbcsql-17.5.so.2.1
      UsageCount=1
