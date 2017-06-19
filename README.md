### Docker Container WordPress + Nginx + PHP7

Step 1 - Create volume 
<pre>
$ docker volume create wordpress
wordpress
</pre>

Step 2 - Build image 
<pre>
$ docker build -f build/Dockerfile -t wp-fornecedores:1.0.0-TGL .
</pre>

Step 3 - Container up
<pre>
$ docker-compose up -d 
</pre>

Step 4 - CMS
<pre>
http://127.0.0.1
</pre>

Step 5 - Configure /var/www/html/wordpress/wp-config.php
