# php/apache/mysql/setup
 
Steps:

--- Apache ---
- Download Apache Win64: https://www.apachelounge.com/download/

- Open the downloaded Zip File
- Drag-Drop Apache24 Folder into the C:/ Drive
- Open a CMD Window in Administrator Mode
- Command: cd /
- Command: cd Apache24
- Command: cd bin
- Command: httpd -k install
If vcruntime140.dll missing error occurs, here is the fix: https://youtu.be/ubFhPDTymRc
- Open Apache configuration file in C:/Apache24/conf/httpd.conf
- Change "ServerName www.example..." to "ServerName localhost"
- Save & Close the Configuration file
- Restart Apache in your CMD window
- Command: httpd -k stop
- Command: httpd -k start

--- PHP ---
- Download PHP VS16 x64 Thread Safe: https://windows.php.net/download#php-8.0
- Create a Folder called "php" in C:/
- Copy-Paste everything from the Zip-File into the "php" folder
- Open Apache configuration file in C:/Apache24/conf/httpd.conf
- Add the following lines underneath the last "#LoadModule" lines:

LoadModule php_module "c:/php/php8apache2_4.dll"
AddType Application/x-httpd-php .php
PHPIniDir "c:/php"

- Add "index.php" after "DirectoryIndex"
- Save & Close the Configuration file
- Create a "index.php" file in c:/Apache24/htdocs
- Add the following lines: " ?php phpinfo() ?" 
// Sorry i cannot add the SmallerThan/biggerThan signes... YouTube won't allow it...
- Restart Apache in your CMD window
- Command: httpd -k restart

--- MySQL ---
- Download the MySQL Database Server: https://dev.mysql.com/downloads/insta...
- Click on "No Thanks"
- Install MySQL using the Installer
- Set Root Password

-- End Steps ---