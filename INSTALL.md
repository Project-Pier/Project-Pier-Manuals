Unless you have downloaded projectpier directly to your web server as described above, unzip the file **pp088wSP2_2014-08-14.zip** to a temporary location on the hard drive of your local computer.
Using an FTP client software application such as [FileZilla](http://filezilla-project.org/), transfer the files to your web hosting home directory.

  > If you prefer that ProjectPier be installed in a subdirectory (example: /projectpier or /projects), first create the subdirectory on your server, then upload the files there.

  > If you have downloaded the files directly to your server using wget (as described on the [download page](DOWNLOAD.md)) then this is not necessary.

Regardless of how you have accomplished the task of placing the files on your server, continue with the steps below.

ProjectPier will need to write to certain files on your file system as outlined in the two sub-items below.

- On Windows systems there is generally no special settings required.
- On *nix systems file permissions will need to be set accordingly. Taking these steps in advance is optional; the installer will let you know if it needs write access to a file or directory to which it does not have proper access at the time the installer is run.
  - Locate the following directories and change the permissions such that they are writable by the web server (755 will work on most *nix systems):
    - /public/files
    - /cache
    - /upload
    - /config
    - /tmp
  - Locate the following files and change the permissions such that they are writable by the web server (644 will work on most *nix systems):
    - /cache/autoloader.php
    - /cache/log.php
- Log into your MySQL database management tool through your preferred method (example: phpMyAdmin) and create a new database and a new username and password for that database.
  > Write these down, the ProjectPier installer will ask you to enter this information. Alternatively, the ProjectPier installer can create the database for you, but you will still need to know a MySQL username and password with appropriate permissions to create a new database.

- Run the ProjectPier installer. To do this, in your browser navigate to the ```/public/install``` URL.
  > For example, if you uploaded the ProjectPier installation files to a subdirectory named ```projectpier``` in your web hosting home directory, then navigate to ```http://www.example.com/projectpier/public/install```.

- Follow the installer's instructions.