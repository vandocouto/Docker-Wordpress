### Docker Container WordPress + Nginx + PHP7


Step 1 - Project clone 
<pre>
git clone https://github.com/vandocouto/Docker-Wordpress.git
</pre>

Step 2 - Create volume 
<pre>
$ docker volume create wordpress
wordpress
</pre>

Step 3 - Build image 
<pre>
$ cd Docker-Wordpress
$ docker build -f build/Dockerfile -t wp:1.0.0-TGL .
</pre>

Step 4 - Container up
<pre>
$ docker-compose up -d 
</pre>

Step 5 - CMS
<pre>
http://127.0.0.1
</pre>

Step 6 - Configure /var/www/html/wordpress/wp-config.php
