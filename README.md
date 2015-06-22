# laravel-vendor-softlink

## Objective
Create soft link against laravel vendor directory to reduce creation of
multiple vendor directories when creating multiple laravel project


Draft version, have not investigate any potential error in executing these action

## Execution Command
`./pycreatesoftlink.py -e "composer" laravel_directory/vendor`

Currently "-e" only accept one argument, i.e. if parameter given is "composer,
exception_folder_2", exception_folder_2 will not be copied to destination
vendor folder, although it will escaped from created as a soft link in
destination.

Commands excecuted by this script internally: 

    create softlink for common folder
    `ln -s laravel_directory/vendor target`

    copy the composer folder, which will have different content for each project
    `cp -rf laravel_directory/vendor/exceptions_folders target`

## Update Autoload
if necessary, please run `composer dump-autoload` after the running this
script to generate the correct autoload_classmap.php

This script aims to save your internet bandwidth and reduce unnecessary files
on your computer. You can skip the `composer install` command after running
this script.
