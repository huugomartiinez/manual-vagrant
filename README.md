# NextCloud
## pasos:

1. Crear un directorio (mkdir *directorio*) y entrar en él (cd *directorio*)
2. Ponemos este comando para crear un VagrantFile (vagrant init ubuntu/jammy64)
3. Y este otro para la infraestructura (vagrant up --provider=virtualbox)
4. Hacemos ssh (vagrant ssh)
5. Y miramos los archivos con (ll /vagrant)

6. Hacemos un apt update para actualizar paquetes (sudo apt update)
7. Y un upgrade (sudo apt upgrade)
8. Hacemos estos comando (apt-get install software-properties-common gnupg2 -y 
add-apt-repository ppa:ondrej/php 
apt-get update -y 
apt-get install php7.4 php7.4-fpm php7.4-cli -y
apt install zip
sudo apt install smbclient redis-server unzip openssl rsync imagemagick
sudo apt install php7.4 php7.4-intl php7.4-mysql php7.4-mbstring \
    php7.4-imagick php7.4-igbinary php7.4-gmp php7.4-bcmath \
    php7.4-curl php7.4-gd php7.4-zip php7.4-imap php7.4-ldap \
    php7.4-bz2 php7.4-ssh2 php7.4-common php7.4-json \
    php7.4-xml php7.4-dev php7.4-apcu php7.4-redis \
    libsmbclient-dev php-pear php-phpseclib)
8. Instalamos apache (sudo apt install -y apache2)
9. Instalamos el mysql (sudo apt install -y mysql-server)
10. Reiniciamos el servidor (sudo systemctl restart apache2)

11. Nos convertimos en root (sudo -s)
12. Entramos en mysql (mysql)
13. Creamos la base de datos (CREATE DATABASE bbdd;)
14. Creamos un usuario (CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';)
15. Damos privilegios al usuario (GRANT ALL ON bbdd.(asterisco) to 'usuario'@'localhost';)
16. Salimos (exit)

17. Vamos a nextcloud y en "Communic projects" le damos a "Get ZIP file" para descargarnos el archivo comprimido
18. Lo copiamos a la carpeta que hemos creado al principio
19. Movemos el archivo a /var/www/html (sudo mv /vagrant/latest.zip /var/www/html/)
20. Entramos a /var/www/html/ (cd /var/www/html/)
21. Unzipeamos el archivo (sudo unzip *archivo*)
22. Copiamos el contenido de nextcloud al repositorio actual (sudo cp -R nextcloud/. .)
23. Ponemos permisos (chmod -R 775 .) 
24. Y mas permisos (chown -R root:www-data .)

25. Editamos el fichero VargantFile (vi VagrantFile)
26. Desmarcamos las siguientes lineas
```# Create a forwarded port mapping which allows access to a specific port
# within the machine from a port on the host machine. In the example below,
# accessing "localhost:8080" will access port 80 on the guest machine.
# NOTE: This will enable public access to the opened port
config.vm.network "forwarded_port", guest: 80, host: 8080


# Create a public network, which generally matched to bridged network.
# Bridged networks make the machine appear as another physical device on
# your network.
config.vm.network "public_network"
```
27. Hacemos este comando (sudo apt install libapache2-mod-php7.4 php7.4-mysql)
28. Salimos y hacemos vagrant reload (exit) (vagrant reload)
29. Hacemos ssh (vagrant ssh)
30. Copiamos y pegamos la ip que nos sale en el navegador.

