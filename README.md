# laravel-vendor-softlink

## Objective
Create softlink against laravel vendor directory to reduce creation of
multiple vendor directories when creating multiple laravel project


Draft version, have not investigate any potential error in executing these action

## Execution Command
`./pycreatesoftlink.py -e "composer, expcetion_folder" source_vendor_directory/target`


Commands excecuted by this script internally: 

    create softlink for common folder
    `ln -s source_vendor_directory/target target`

    copy the composer folder, which will have different content for each project
    `cp -rf source_vendor_directory/target target`

## Update Autoload
if necessary, please run `composer dump-autoload` after the running this
script to generate the correct autoload_classmap.php

This script aims to save your internet bandwidth and reduce unnecessary files
on your computer. You can skip the `composer install` command after running
this script.
