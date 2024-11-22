# file-manager-for-TinyMCE-substitution-for-responsivefilemanager
Optional settings for [primakurzy.cz](https://www.primakurzyonline.cz/): training with project PrimaKavarna.

## 1. PURPOSE
Library Is For Educational Purposes Only Directly Connected With Project PrimaKavarna.

## 2. INFO
Unfortunatelly [responsivefilemanager](https://www.responsivefilemanager.com/) official development ended in 2019, even it some updated are foundable on GIT (TinyMCE supported version is 5!!!).
FLMNGR-SERVER-PHP tested with TinyMCE v7.5 and till now seems promissable (with rest of settings from training also OK!), however is only online solution!

## 3. Installation
The easiest way to install the library is using [Composer](https://getcomposer.org/):

```sh

composer require tinymce/tinymce
composer update edsdk/flmngr-server-php

```
 My installed version:
 ![image](https://github.com/user-attachments/assets/e9d9ab65-6973-4020-815a-1f685b7e71ba)

## 4. Create flmngr.php in root of your project

```php

<?php
    \EdSDK\FlmngrServer\FlmngrServer::flmngrRequest(
        array(
            'dirFiles' => '/var/www/files',
        )
    );

```

## 5. Donwload file-manager folder (only for offline presentation)
As with Composer was downladed pure online solution, so from [flmngr-tinymce](https://github.com/edsdk/flmngr-tinymce) download
and add "file-manager" folder to your-path\xampp\htdocs\primakavarna\vendor\tinymce\tinymce\plugins

## 6. Register API and gain API key
Offline presentation: open for example [primakavarna/stranka-uvod](http://localhost/primakavarna/admin.php?stranka=uvod) and hit "upload":
![image](https://github.com/user-attachments/assets/c139f6ae-e261-4b5d-85f1-3c2462001c3e) => register your API.

If you skipped step 5, you can [register](https://flmngr.com/dashboard) your API directly.

Finish all settings:
![image](https://github.com/user-attachments/assets/69b35cf1-51f2-415c-90cb-5072f7c9c41e)

## 7. Update tinymce.init
Edit acordingly to your online project

```php

plugins: "file-manager",
                 Flmngr: {
                    urlFileManager: " http://your-website.com/flmngr/flmngr.php",
                    urlFiles: " http://your-website.com/files/"  
                    },
                 toolbar: "Flmngr,Upload,ImgPen", // add your buttons here too
                 apiKey: "YOUR_API_KEY",

```

## 8. Waiting for final test
In current state of security of my project, it would be really silly upload it to firebase and finish tests with download / upload files.
will be done later.
But seems as really good substitution for responsivefilemanager!

