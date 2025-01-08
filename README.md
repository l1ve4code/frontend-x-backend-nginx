<h1 align="center"><img src="resources/nginx.svg" width="32"> SSL NGINX TEMPLATE</h1>

## About

This is a template for creating a web application with an **SSL certificate**

### Technologies

- Technologies: **Nginx, Certbot, Docker**

### Resources

- [https-using-nginx-certbot-docker](https://mindsers.blog/en/post/https-using-nginx-certbot-docker/)
- [react-js-application-showing-404-not-found-in-nginx-server](https://stackoverflow.com/questions/43555282/react-js-application-showing-404-not-found-in-nginx-server)

## Installing

- **[1]** Run the following command in the terminal `mkdir frontend && mkdir certbot`
- **[2]** Move your **frontend project** to the **frontend folder**
- **[3]** In the **nginx/nginx.conf** file, replace **your-url.net** to **your domain**
- **[4]** In the **nginx/nginx.conf** file, add: **ssl_certificate, ssl_certificate_key**; to the **comment**
- **[5]** Run the following command in the terminal `docker compose -f nginx.yml up -d`
- **[6]** Run the following command in the terminal `docker compose -f certbot.yml run --rm  certbot certonly --webroot --webroot-path /var/www/certbot/ --dry-run -d your-url.net`
- **[7]** Run the following command in the terminal `docker compose -f certbot.yml run --rm  certbot certonly --webroot --webroot-path /var/www/certbot/ -d your-url.net`
- **[8]** In the **nginx/nginx.conf** file, remove: **ssl_certificate, ssl_certificate_key**; from the **comment**
- **[9]** Run the following command in the terminal `docker compose -f nginx.yml restart`

## Author

* Telegram: **[@live4code](https://t.me/live4code)**
* Email: **steven.marelly@gmail.com**