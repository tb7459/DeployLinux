# DeployLinux
FSND Final project

----LOGIN TO SERVER----
1) store provided key in a location you can find
2) use the following command to login as grader(be sure to replace <path to key> with the full path,
    and <key name> with the name of the file):
  
    ssh grader@54.89.65.110 -p 2200 -i (path to key)/(key name)
    (ip address: 54.89.65.11 port: 2200)
  
----URL for webpage ----
http://ec2-54-89-65-110.compute-1.amazonaws.com/

---- SUMMARY OF SOFTWARE INSTALLED AND CONFIGURATION CHANGES ----
software installed:
  1) Python 2.7
  2) Flask
  3) SqlAlchemy
  4) PostGreSql
  5) Apache2
  6) mod-wsgi
  7) oauth2 client
  
configuration changes:
  1) Apache2: 
      updated to give path to the WSGI application, 
      added WSGIScriptAlias,
      and added <DIRECTORY />
      
   2) PostGreSql:
       updated postgresql.conf to listen on all,
       updated pg_hba.conf to allow only catalog 
         to login to libbooks database on 35.171.4.160
        
    3) my files:
       updated all files to use postgresql database instead of sqllite,
       updated application.py(wsgi file being called by apache2) to use facebook login 
       as google plus wouldn't allow the connection, also updated templates/login.html 
       to point to facebook login. updated database_setup.py, had to change table name 'user' 
       to 'libraryuser' as user is already a table in postgresql.
       
