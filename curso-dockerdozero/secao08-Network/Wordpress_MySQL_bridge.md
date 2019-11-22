Webapp Wordpress com MySQL usando driver bridge network
============

* 01 - Crie uma user-defined bridge network chamada rede-wordpress:
$>  sudo docker network create -d bridge rede-wordpress

* 02 - Inspecione a nova rede
$>  sudo docker  network ls
$>  sudo docker network inspect rede-wordpress

* 03 - Inicie 2 containers para criar um CMS Wordpress
$>  sudo docker run --name db1 -e MYSQL_ROOT_PASSWORD=mysql -d --net rede-wordpress mysql:5.7 (ou versao menor que a 8 - erro em conexao)
$>  sudo docker run --name wp1 -e WORDPRESS_DB_HOST=db1 -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD=mysql -p 8080:80 -d --net rede-wordpress wordpress





