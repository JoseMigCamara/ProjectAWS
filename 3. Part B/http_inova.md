```
apt install ngnix
```

```
apt install ssl-cert
```

```
cd /etc/nginx/snippets/
```

```
cp snakeoil.conf inova.conf
```

```
nano inova.conf
```
* Change the names and path of the certificates

```
cd ../sites-available/
```

```
cp default secure
```

```
nano secure
```
* Comment line X (80) 
* Uncomment line X (443)
* Uncomment line X (snippets/snakeoil.conf)
* Change in line X, snakeoil.conf to inova.conf
* Change in line x, the root to /var/www/htmls
```
cd /etc/nginx/sites-available/
```

```
ln -s /etc/ngnix/sites-available/secure secure
```

```
cd /var/www/
```

```
mv html/index.nginx-debian.html html/index.html
```

```
cp -t html/ htmls
```

```
nano html/index.html
```

```
nano htmls/index.html
```

```
systemctl restart nginx
```

```
systemctl status nginx
```
