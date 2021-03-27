## Short urls without '/public'

For short urls without '/public' add .htaccess to main folder with this code:

	<IfModule mod_rewrite.c>
		RewriteEngine On
		RewriteRule ^(.*)$ laravel/public/$1 [L]
	</IfModule>
	
and asset_url to .env file 

    ASSET_URL=laravel/public

## Pusher

This project use https://pusher.com

Create account and set your settings in .env

    PUSHER_APP_ID=your_app_id
    PUSHER_APP_KEY=your_app_key
    PUSHER_APP_SECRET=your_app_secret
    PUSHER_APP_CLUSTER=your_region_cluster
