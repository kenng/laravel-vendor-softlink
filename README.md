# laravel-vendor-softlink
create softlink against laravel vendor to reduce creation of multiple vendor directories


Draft version, have not investigate any potential error in executing these action

`./pycreatesoftlink.py -e "composer, expcetion_folder" source_vendor_directory/target`

command excecuted by this script internally: 

    ## create softlink for common folder
    `ln -s source_vendor_directory/target target`

    ## copy the composer folder, which will have different content for each project
    `cp -rf source_vendor_directory/target target`

if necessary, please run `composer dump-autoload` after the running this
script to generate the correct autoload_classmap.php
