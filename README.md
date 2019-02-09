##Simple Docker for Magento2 (PHP 7.1 + nginx 1.13.11 + MySQL 8)

####How to use it?

Simply create directory in Magento2 location and pull this repository there. Then `docker-compose up -d` and you're good to go!

There is example `.env` file in case of installing Magento. Put there desired config and then run command: `/var/www/magento2/bin/magento setup:install --base-url=$MAGENTO_URL --backend-frontname=$MAGENTO_BACKEND_FRONTNAME --language=$MAGENTO_LANGUAGE --timezone=$MAGENTO_TIMEZONE --currency=$MAGENTO_DEFAULT_CURRENCY --db-host=$MYSQL_HOST --db-name=$MYSQL_DATABASE --db-user=$MYSQL_USER --db-password=$MYSQL_PASSWORD --use-secure=$MAGENTO_USE_SECURE --base-url-secure=$MAGENTO_BASE_URL_SECURE --use-secure-admin=$MAGENTO_USE_SECURE_ADMIN --admin-firstname=$MAGENTO_ADMIN_FIRSTNAME --admin-lastname=$MAGENTO_ADMIN_LASTNAME --admin-email=$MAGENTO_ADMIN_EMAIL --admin-user=$MAGENTO_ADMIN_USERNAME --admin-password=$MAGENTO_ADMIN_PASSWORD`.
Magento will configure itself based on passed configuration.

####Known issues
If you are using Windows make sure your filesystem will work well with virtual machine. Using Docker Toolbox will require running Docker Quickstart Terminal as Administrator (right click -> Run as Administrator), otherwise there will be problem with symlinks.