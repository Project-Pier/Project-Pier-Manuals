# Project-Pier-Manuals

*ProjectPier* is a Free & Open-Source, PHP application for managing tasks, projects, and teams through an intuitive web interface.
ProjectPier will help your organization communicate, collaborate and get things done.

Its function is similar to commercial groupware/project management products, but allows the freedom and scalability of self-hosting.

This manual will explain how to [download](DOWNLOAD.md), [install](INSTALL.md), and [configure](CONFIGURE.md) ProjectPier.

## Who should perform the installation?
Installing ProjectPier requires an understanding of how to install PHP/MySQL based software applications.

  - If you have installed other PHP/MySQL software applications (example: Wordpress or Joomla) you will find the instructions below easy to follow.
  - If you have never installed a PHP/MySQL application but are familiar with how basic linux web hosting accounts work (for example you have used C-Panel based web hosting) then you should be able to understand the instruction and successfully install ProjectPier on your server.
  - If most of this paragraph has not been understandable, then you should probably not attempt to perform the installation yourself.
    > In this case you may want to consider contacting your Information Technology department for help, or purchasing a web hosting package with and automated ProjectPier installer.

## Requirements
To install ProjectPier you need a web server that meets the following requirements

- Apache HTTP web server 2.0 or greater
- PHP 5.2 or 5.3 (plus required extensions)
  - MySQL
  - GD
  - SimpleXML
- MySQL 4.1 or greater *with InnoDB support*

  > Please note that you cannot use ProjectPier with PHP 4. Please contact your provider if and how you have to configure your settings to use PHP 5.
- enabling innodb support
  > Some installations of MySQL don't support InnoDB by default.
  > The ProjectPier installer will tell you if your server is not configured to support InnoDB. This is [easy to fix](#innodb-support) on a dedicated server or virtual server if you have root access.
  > If you are attempting to use a shared web hosting account you probably don’t have access to the files required. *In that case contact your hosting provider.*

### InnoDB Support
Open your MySQL options file:
- the file name is:
  - ```my.cnf``` (Linux) - usually at ```/etc/my.cnf```
  - or ```my.ini``` (Windows) - usually at ```c:/windows/my.ini```. 
  > If you are using the Uniform Server on Windows, the file will be named ```my-small``` and will need to be edited with a unix compatible editor such as Notepad++, PSPad, Atom or Sublime-Text.

- Comment the skip-innodb line by adding ```#``` in front of it (like ```#skip-innodb```).
  > It would also be good to increase ```max_allowed_packet``` to ensure that you will be able to upload files larger than 1MB. Just add this line below the ```#skip-innodb``` line:

  ```
  set-variable = max_allowed_packet=64M
  ```

Alternatively, just install without InnoDB support. The installer will allow you.