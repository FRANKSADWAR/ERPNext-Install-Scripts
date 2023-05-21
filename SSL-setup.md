# SSL Setup in ERPNext / Frappe sites

```
sudo apt-get update
```

```
sudo apt-get install gunicorn
```

```
sudo apt-get install supervisor
```

```
sudo service nginx stop
```

## SETUP SSL

```
sudo apt-get install certbot -y
```

```
sudo apt install certbot python3-certbot-nginx
```

```
sudo certbot certonly -a nginx -d yoursite.example.com 
```


> Now you have certificate here in this folder /etc/letsencrypt/live/

Edit nginx configuration file. In our case /etc/nginx/conf.d/frappe-bench.conf

Goto the server section, change port 80 to 443 ( or whatever port you want )


Check for ports usage and kill the processes using these ports: 
```
sudo apt-get install net-tools
```

```
sudo nestat -lnp
```

```
sudo kill -9 $(sudo lsof -t -i:80)
```

> Simulate renewal for the SSL certificate; 

```
sudo certbot -a nginx renew --dry-run 
```