# magento-2-bulk-export-and-import-product-extension
magento 2 bulk export and import product extension

Extension Overview
The extension can Import and Export ALL Product related data. It will also export all existing product data and will export all product types / tier pricing / custom options etc and you can then use that same file and re-import. This extension can also be used to updated existing price data and qty data or any other data that may need to be updated. This extension includes a how to PDF with screenshots on how to setup your Magento as well as an example csv's and all needed code / files etc to make this import process work. This extension will also now allow you to export all product data from a magento 1.x install and import / transfer them to another magento 2.x install.


Extension Installation
1. Log out from Magento Admin panel if you are logged in
2. Unpack the contents of the zip file purchased and VIA ftp and upload the app folder to your magento install root.
3. Log into Magento Admin Panel
4. Clear cache using command php -f bin/magento cache:flush
5. After uncompressing the product attributes import/export package, you should have one folder: app
Upload everything in the app/* folder to your app/* folder. Then go to app/etc/modules
6. SSH into your magento 2 server and run command via ssh in root of magento 2 install to install module
php -f bin/magento setup:upgrade
and
php -d memory_limit=1024M -f bin/magento setup:di:compile

Extension Usage
1. DO NOT - Edit the CSV in excel it strips format and breaks import. I recommend using openoffice.org calc and saving in utf-8 format.
2. Overall the extension is very straight forward. You can find in magento admin under
system -> import/export products
and you can run the export to get a sample csv of products already in your site and then you just upload it for import and it will import it back into the site.
3. You can also control the ability to export grouped product positions on export / for reimport later by setting this value in dropdown of the export profile to "Yes".
4. You can also control the ability to ONLY update product data on import by setting this value in dropdown of the export profile to "Yes".
5. On import you can control the ability to import images either by setting “import_images_by_url” to "Yes".and you supply HTTP://www.site.com/image.jpg in the “image”,”small_image”,”thumbnail”,”gallery” columns or set to false and supply “/image.jpg” in same columns
6. On import you can control the ability to reimport images or skip/leave images as-is by setting this value in dropdown of the export profile to "Yes".
7. On import assuming reimport_images is already "Yes". This setting if set to "Yes" will delete ALL existing images for the product and re-import ONLY the images you set in the csv. If this is set to "No" it will keep any existing images and append/add to the product the images in the csv even if they are a duplicate.
8. On import you can control the ability to append / add tier pricing to existing products with tier pricing already existing or if you set to "No" it will delete all existing tier pricing and import just what is in your csv.
9. On import you can control the ability to append / add categories for products with existing categories or if you set to "No" then it will delete all existing categories and import just what is in your csv "categories" column. NOTE "category_ids" column cannot exist.
10. On Export with setting " Export Category Paths" you can control the ability to export with category paths e.g. “Maincategory/Subcategory” vs Category Ids “23,24”.. by setting this value in dropdown of the export profile to "Yes" if it is set to "No" then It just exports category_ids.
11. If you are importing category paths via the “categories” column make sure you have deleted the “category_ids” column as you can’t use both at the same time and you’ve set the correct root catalog ID





