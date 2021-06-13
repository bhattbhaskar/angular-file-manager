# Angular Gulp Responsive File Manager

This is file explorer helps to explore files and directories for hosting panel that does not have file explorer. 
File exploeres front end is built on angular, gulp, and backend is developed on PHP.

- [Introduction](#introduction)
- [What’s Included?](#whats-included)
- [Installation](#Installation)

## Introduction
File explorer UI should be simple and easy to understand. It is helping to explore with simple UI, its good hierarchy tab, and current direct content.

It supports both responsive modes for desktop and mobile. It is the first to launch of the product so we are going to improve more features. The existing features are listed below.

## What’s Included?
Your environment will have everything you need to build a modern angular file manager:
  - Folders and files list differently on alpha betically order
  - Providing a list of folders even though it has space
  - Multiple File Uploads
  - File Download
  - Move file or folder from one directory to another
  - Navigation bar 
  - Tree navigation system
  - Image file Preview
  - UTF-8 support for file name and directory
 
---------


## Installation
Here is the step-by-step tutorial to install of angular gulp file manager with your system.

Requriments
- [PHP](http://php.net/)
- Browser enabled JavaScript

### Steps to set-up
- save assets folder at your preferred location on your server
- save bridge folder at your preferred location on your server

Now, need to set up API for the server with **FTP username and password**. Please create an FTP account of hosting if not exist.

Now, store FTP account details in the PHP bridges directory 
Go to
bridges/php/handler.php
```sh
// Set ftp details
$oFtp = new FileManager(array(
    'hostname' => 'FTP_HOSTNAME',
    'username' => 'FTP_USERNAME',
    'password' => 'FTP_PASSWORD'
));
```
Now, We will move forward for front end.
```sh
<!-- support -->
<script src="assets/modules/angular/angular.min.js"> </script>
<script src="assets/modules/angular-translate/angular-translate.min.js"> </script>
<script src="assets/modules/ng-file-upload/ng-file-upload.min.js"> </script>
<script src="assets/modules/jquery/dist/jquery.min.js"> </script>
<script src="assets/modules/bootstrap/dist/js/bootstrap.min.js"> </script>
<link rel="stylesheet" href="assets/modules/bootswatch/paper/bootstrap.min.css" />
<!-- /support -->

<!-- angular file manager css and js -->
<link href="assets/file-manager/angular-filemanager.min.css" rel="stylesheet" />
<script src="assets/file-manager/angular-filemanager.min.js"></script>
<!-- /angular file manager css and js -->
  
<link href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css" rel="stylesheet" />
<link href="assets/custom/custom.css" rel="stylesheet">
  <script type="text/javascript">
    //example to override angular-filemanager default config
    angular.module('FileManagerApp').config(['fileManagerConfigProvider', function (config) {
      var defaults = config.$get();
      config.set({
        appName: 'angular-filemanager',
        pickCallback: function(item) {
          var msg = 'Picked %s "%s" for external use'
            .replace('%s', item.type)
            .replace('%s', item.fullPath());
          window.alert(msg);
        },

        allowedActions: angular.extend(defaults.allowedActions, {
          pickFiles: false,
          pickFolders: false,
        }),
      });
    }]);
  </script>
```
Now add this tag where you want to place in section
```sh
 <angular-filemanager> </angular-filemanager>
```

## Contributing
We'd love to have your helping hand on Angular File Manager!

We hope that you have sucessfully installed.
👍
