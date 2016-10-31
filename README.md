# magento-2-bulk-export-and-import-product-extension
magento 2 bulk export and import product extension

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
