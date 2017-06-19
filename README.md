### Docker Container WordPress + Nginx + PHP7
<pre>
$ docker volume create wordpress
wordpress
</pre>

<pre>
$ docker build -f build/Dockerfile -t wp-fornecedores:1.0.0-TGL .
</pre>

<pre>
$ docker-compose up -d 
</pre>

<pre>
http://127.0.0.1
</pre>
