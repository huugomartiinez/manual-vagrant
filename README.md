# manual-vagrant
## pasos:

1. Crear un directorio (mkdir *directorio*) y entrar en él (cd *directorio*)
2. Ponemos este comando para crear un VagrantFile (vagrant init ubuntu/jammy64)
3. Y este otro para la infraestructura (vagrant up --provider=virtualbox)
4. Hacemos ssh (vagrant ssh)
5. Y miramos los archivos con (ll /vagrant)

6. Hacemos un apt update para actualizar paquetes (sudo apt update)
7. Y un upgrade (sudo apt upgrade)
8. Instalamos apache (sudo apt install -y apache2)
9. Instalamos el mysql (sudo apt install -y mysql-server)
10. Instalamos alugans de las librerias de php (sudo apt install -y php libapache2-mod-php)
11. Y mas (sudo apt install -y php-fpm php-common php-mbstring php-xmlrpc php-soap php-gd php-xml php-intl php-mysql php-cli php-ldap php-zip php-curl)
12. Reiniciamos el servidor (sudo systemctl restart apache2)

13. Nos convertimos en root (sudo -s)
14. Entramos en mysql (mysql)
15. Creamos la base de datos (CREATE DATABASE bbdd;)
16. Creamos un usuario (CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';)
17. Damos privilegios al usuario (GRANT ALL ON bbdd.(asterisco) to 'usuario'@'localhost';)
18. Salimos (exit)

19. Vamos a nextcloud y en "Communic projects" le damos a "Get ZIP file" para descargarnos el archivo comprimido
20. Lo copiamos a la carpeta que hemos creado al principio
21. Movemos el archivo a /var/www/html (sudo mv /vagrant/latest.zip /var/www/html/)
22. Entramos a /var/www/html/ (cd /var/www/html/)
23. Unzipeamos el archivo (sudo unzip *archivo*)
24. Copiamos el contenido de nextcloud al repositorio actual (sudo cp -R nextcloud/. .)
25. Ponemos permisos (chmod -R 775 .) 
26. Y mas permisos (chown -R root:www-data .)

27. Editamos el fichero VargantFile (vi VagrantFile)
28. Desmarcamos las siguientes lineas
```# Create a forwarded port mapping which allows access to a specific port
# within the machine from a port on the host machine. In the example below,
# accessing "localhost:8080" will access port 80 on the guest machine.
# NOTE: This will enable public access to the opened port
config.vm.network "forwarded_port", guest: 80, host: 8080


# Create a public network, which generally matched to bridged network.
# Bridged networks make the machine appear as another physical device on
# your network.
config.vm.network "public_network"

