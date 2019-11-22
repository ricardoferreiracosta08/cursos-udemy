Docker Volume - persistindo dados em Volume
============

* 01 - Criar docker volume chamado vol-web:

$>  sudo docker volume create vol-web

$>  sudo docker volume ls 

$>  sudo docker volume inspect vol-web

* 02 - Criar container web com esse volume:

$>  sudo docker run -itd --name apache -p 8080:80 -v /etc/localtime:/etc/localtime:ro -v vol-web:/usr/local/apache2/htdocs/ httpd:2.4

* 03 - Acessar web:

http://localhost

* 04 - Criar arquivo e conteúdo para index.html

* 05 - Copiar arquivo index.html para dentro do volume:

$>  sudo docker cp index.html apache:/usr/local/apache2/htdocs/

* 06 - Acessar web: http://localhost
