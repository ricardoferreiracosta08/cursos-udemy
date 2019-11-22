Webapp Wordpress com MySQL usando containers links
============

# MySQL
$>  sudo docker run --name db1 -e MYSQL_ROOT_PASSWORD=mysql -d mysql:5.7 (ou versao menor que a 8 - erro em conexao)

# Wordpress
$>  sudo docker run --name wp1 --link db1:mysql -p 8081:80 -d wordpress






