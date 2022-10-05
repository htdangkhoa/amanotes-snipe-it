# Snipe-it Docker Compose Setup

```sh
docker-compose up
```

Cretae `.env` file

```
# Mysql Parameters
MYSQL_PORT_3306_TCP_ADDR=snipe-mysql
MYSQL_PORT_3306_TCP_PORT=3306
MYSQL_ROOT_PASSWORD=YOUR_ROOT_PW
MYSQL_DATABASE=snipeit
MYSQL_USER=snipeit
MYSQL_PASSWORD=snipeit

# Email Parameters
MAIL_PORT_587_TCP_ADDR=smtp.gmail.com
MAIL_ENV_ENCRYPTION=tls
MAIL_PORT_587_TCP_PORT=587
MAIL_ENV_FROM_ADDR=YOUR_EMAIL
MAIL_ENV_FROM_NAME=YOUR_NAME
MAIL_ENV_USERNAME=YOUR_EMAIL
MAIL_ENV_PASSWORD=YOUR_GOOGLE_APP_PW

# Snipe-IT Settings
APP_ENV=production
APP_DEBUG=false
APP_KEY={{INSERT_API_TOKEN}}
APP_URL=http://127.0.0.1:3051
APP_TIMEZONE=Asia/Ho_Chi_Minh # you should change this to your timezone
APP_LOCALE=en # you should change this for the desired language
```

# API Key

```sh
docker exec -it your-snipe-it-container-name sh
```

```sh
php artisan key:generate --show
```

Now go to your .env file and replace `{{INSERT_API_TOKEN}}` with your API key

And now if you restart your containers with for instance:

```sh
docker-compose down && docker-compose up -d --build
```

You should be good and have everything available at:

http://localhost:3051

Happy asset managing!!!
