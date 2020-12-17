# Instalación Ubuntu 20.04 en AWS

EC2 sirve para lanzar servidores virtuales configurar la seguridad y las redes y administrar el almacenamiento.

Para empezar la instalación, vamos a iniciar sesión en nuestra cuenta de AWS Educate. Una vez accedemos a través de My Classrooms a nuestra clase, vamos a ver el siguiente menú. Para instalar la máquina virtual, vamos a hacer click en **Ejecute una máquina virtual**.

![imagen 1.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/1.PNG?raw=true)


En el siguiente paso vamos a seleccionar el tipo de máquina virtual que queramos instalar. Primero, vamos a seleccionar el checkbox **free tier only** y seleccionaremos Ubuntu Server 20.04 LTS. 

![imagen 2.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/2.PNG?raw=true)

En el segudo paso, vamos a seleccionar el tipo de instancia. En nuestra caso, al ser una cuenta "gratuita" solo podemos elegir la que viene por defecto. Para continuar haremos click en **Next: Configure Instance Details**.

![imagen 3.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/3.PNG?raw=true)

En el tercer paso, no vamos a cambiar ninguna configuración, por lo que haremos click en **Next: Add Storage**.

![imagen 4.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/4.PNG?raw=true)

En el cuarto paso, cambiaremos el almacenamiento de nuestra máquina virtual. Por defecto, viene con 8GB de capacidad pero lo máximo que nos permite con nuestra cuenta "gratuita" es de 30GB, cambiaremos el tamaño a 30GB. Para continuar, vamos a hacer click en **Next: Add Tags**.

![imagen 5.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/5.PNG?raw=true)
![imagen 6.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/6.PNG?raw=true)

En el quinto paso, no vamos a añadir ninguna etiqueta, por lo que haremos click en **Next: Configure Security Group**.

![imagen 7.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/7.PNG?raw=true)

En el sexto paso, vamos a añadir una descripción. Este paso es opcional.
Para terminar la instalación, vamos a hacer click en **Review and Launch**.

![imagen 8.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/8.PNG?raw=true)

El séptimo paso será para revisar la configuración de la máquina virtual. Una vez revisada, haremos click en **Launch**.

![imagen 9.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/9.PNG?raw=true)

El último paso de la intalación será para generar la clave privada para que cada vez que nos conectemos mediante SHH a nuestra máquina virtual no nos pida una contraseña. Para crearla, vamos a seleccionar **Create a new key pair** y le asignaremos un nombre. Haremos click en **Download Key Pair** y guardaremos bien el archivo porque no lo podemos generar en caso de perderelo. Una vez descargado, vamos a hacer click en **Launch Instances**.

![imagen 10.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/10.PNG?raw=true)

Para ver si se ha instalado corretamente, en el menú de instancias podemos ver las instancias que tenemos creadas. Una vez que se ponga el estado en verde, estará funcionando.

![imagen 11.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/11.PNG?raw=true)

Ahora, vamos a conectarnos mediate SSH a nuestra máquina virtual. Primero, vamos a seleccionar la instancia que está ejecutándose.

![imagen 13.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/13.PNG?raw=true)

Una vez seleccionada la instancia, vamos a seleccionar la opción **Conectar** y luego **SSH**. 

![imagen 14.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/14.PNG?raw=true)

Ahora, vamos a la carpeta donde hemos guardado la clave y vamos a abrir Git Bash:

![imagen 16.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/16.PNG?raw=true)

Vamos a cambiar los permisos de la carpeta para que nosotros podamos verla:

![imagen 17.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/17.PNG?raw=true)

Una vez cambiados los permisos, vamos a conectarnos con el comando SSH:

![imagen 18.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/18.PNG?raw=true)

En el mensaje que nos sale, escribiremos **yes** y pulsaremos **Enter**:

![imagen 19.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/19.PNG?raw=true)

Como podemos observar, ya estamos conectados mediante SSH a nuestro servidor de AWS:

![imagen 20.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/20.PNG?raw=true)

![imagen 21.1](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio1/21.PNG?raw=true)

# Instalar Apache

Vamos a instalar Apache en nuestro servidor y comprobar que está activo. Para ello, vamos a utilizar los siguientes comandos:

![imagen 4.2](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio2/4.PNG?raw=true)
![imagen 24.2](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio2/24.PNG?raw=true)

Si escribimos nuestra dirección IP en un navegador, debería de funcionar el servidor Apache, pero no es el caso. Para configurar este paso, vamos a seleccionar la instancia y nos situaremos en el apartado **Seguridad**. Para continuar, vamos a hacer click en el enlace azul: 

![imagen 25.2](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio2/25.PNG?raw=true)

Para añadir una nueva regla de entrada, hacemos click en el botón **Editar reglas de Entrada**. 

![imagen 26.2](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio2/26.PNG?raw=true)

En el tipo, seleccionaremos **HTTP**, en Origen seleccionaremos **0.0.0.0** y añadiremos una desprición:

![imagen 27.2](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio2/27.PNG?raw=true)

Para comprobar que funciona correctamente, vamos a escribir el nombre de nuestro servidor en el navegador y comprobar que funciona correctamente:

![imagen 28.2](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio2/28.PNG?raw=true)
![imagen 29.2](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio2/29.PNG?raw=true)

# Instalar MYSQL
Para instalar MYSQL, vamos a utilizar el siguiente comando:

![imagen 5.2](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio2/5.PNG?raw=true)

Para comprobar que está activo, vamos a utilizar el comando status:

![imagen 6.2](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio2/6.PNG?raw=true)

# Instalar PHP
Para instalar PHP, vamos a utilizar el siguiente comando:

![imagen 7.2](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio2/7.PNG?raw=true)

Después de realizar la configuración que está explicada en la documentación anterior, vamos a reiniciar el servicio PHP y comprobar que está activo con el comando comando status:

![imagen 10.2](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio2/10.PNG?raw=true)
![imagen 11.2](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio2/11.PNG?raw=true)

# Instalar FTP
Para instalar FTP, vamos a utilizar el siguiente comando:

![imagen 30.2](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio2/30.PNG?raw=true)

Para comprobar que está activo, vamos a utilizar el comando status:

![imagen 31.2](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio2/31.PNG?raw=true)

# IP Elásticas
Una dirección IP elástica es una dirección IPv4 pública, a la que se puede tener acceso desde Internet. Si la instancia no tiene una dirección IPv4 pública, puede asociar una dirección IP elástica a la instancia para habilitar la comunicación con Internet. Por ejemplo, esto le permite conectarse a la instancia desde el equipo local.

Vamos a asignar una dirección IP elástica a nuestra instancia. Como primer paso, vamos al menu principal EC2 y seleccionamos **Direcciones IP elásticas**.

![imagen 1.3](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio3/1.PNG?raw=true)

Una vez abierto el menú de las dirreciones IP, pulsamos el botón naranja **Asignar la dirección IP elástica**:

![imagen 2.3](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio3/2.PNG?raw=true)

Dejamos la configuración por defecto y volvemos a pulsar el botón naranja **asignar**:

![imagen 3.3](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio3/3.PNG?raw=true)

Con este paso, la dirección IP elástica ya estaría creada. Ahora, falta asociarla a nuestra instancia. Para ello, vamos a pulsar el botón **acciones** y **Asociar la dirección IP elástica**:

![imagen 4.3](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio3/4.PNG?raw=true)
![imagen 5.3](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio3/5.PNG?raw=true)

En el siguiente menú, vamos a elegir la instancia a la que queremos asociar la dirección IP y pulsamos en botón naranja **Asociar**:

![imagen 6.3](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio3/6.PNG?raw=true)

Con esto, ya tendriamos la dirección IP elástica asociada a nuestra instancia. Para finalizar, vamos a comprobar que funciona correctamente:

![imagen 7.3](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio3/7.PNG?raw=true)
![imagen 8.3](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio3/8.PNG?raw=true)
![imagen 9.3](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio3/9.PNG?raw=true)

# DNS
DNS (Domain Name System) es un sistema de nomenclatura jerárquico descentralizado para dispositivos conectados a redes IP como Internet o una red privada. Su función es traducir una dirección IP para devolvernos el nombre de un dominio  o a la inversa.

Hay 9 registros diferentes:

### A
Los usuarios de Internet pueden introducir un nombre de dominio en el navegador y hacer que el cliente envíe automáticamente una solicitud HTTP a la dirección IP correspondiente. Se utiliza una dirección IPv4.

### AAAA
También llamados quad-A, funcionan igual que los registros A salvo que, en lugar de usar una dirección IPv4, usan una dirección Ipv6. Su nombre surge de la longitud del campo de datos, que es cuatro veces más larga que la de un registro A.

### SOA
Son las iniciales de **Start of Authority**. Los registros de este tipo contienen información sobre la zona que se organiza a través del archivo de zona (del servidor DNS) y, por ello, son especialmente importantes para la transferencia de zonas. En estos registros DNS se encuentra, junto a la dirección de correo electrónico del administrador correspondiente, un número de serie que aumenta cada vez que se actualiza el archivo.

### CNAME
Un registro **CNAME** (canonical name record) contiene un alias, es decir, un nombre alternativo para un dominio, y remite a otro registro A o AAAA ya existente.

### MX 
El nombre del registro **MX** es una abreviación de **mail exchange**, intercambio que se produce mediante un servidor SMTP de correo electrónico. Aquí se definen uno o varios servidores de correo electrónico que pertenezcan al dominio en cuestión.

### PTR
El registro **PTR (pointer)** es un registro DNS que permite una búsqueda inversa o reverse lookup. Con ella, el servidor DNS puede indicar qué nombres de host pertenecen a una dirección IP concreta.

### NS
Un registro **NS** hace referencia al servidor de nombres de un archivo de zona y determina dónde recae la responsabilidad de una zona concreta. Es, por ello, un registro obligatorio en todo archivo de zona.

### SRV
Mediante un registro **SRV**, un servidor puede informar acerca de los servicios disponibles del dominio. Para ello, se indica el servicio, incluyendo el puerto en el que se puede encontrar.

### TXT
Los registros **TXT** contienen texto, ya sea como fuente de información para usuarios humanos o para ser leído maquinalmente.

## Registros DNS

Estos son los dominios que tenemos que en CPanel:

![imagen 1.4](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio4/1.PNG?raw=true)

## Registros DNS

### A
![imagen 2.4](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio4/2.PNG?raw=true)
Si nosotros escribimos **grupo4.zerbitzaria.net**  nos va a redirigir a la la dirección IP 54.76.1.76

### AAAA
![imagen 3.4](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio4/3.PNG?raw=true)
Nuestro dominio no tiene registros AAAA

### CNAME
![imagen 4.4](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio4/4.PNG?raw=true)
Si escribimos **www.grupo4.zerbitzaria.net** nos va a redirigir al alias **grupo4.zerbitzaria.net**

### MX
![imagen 5.4](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio4/5.PNG?raw=true)
El servidor de correo de nuestro dominio es mail.grupo4.zerbitzaria.net

### SRV
![imagen 6.4](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio4/6.PNG?raw=true)
Nos informa que el servicio **cpanelmaildiscovery.cpanel.net** está disponible a través del puerto 443

### TXT
![imagen 7.4](https://github.com/markelcenda/ImagenesAWS/blob/main/ejercicio4/7.PNG?raw=true)
Contiene texto.

# Ejercicio 5

**¿Cuántos servidores DNS existen?**
Hay 3 tipos de servidores DNS:
* Servidor de resolución de código auxiliar DNS
* Servidor de resolución recursiva DNS
* Servidor autoritario de DNS

Hay 13 tipos de servidores Raíz. Cada uno tiene una letra correspondiente a su número de la A hasta la M.
Por ejemplo: a.root-servers.net, b.root-servers.net, c.root-servers.net, d.root-servers.net, e.root-servers.net, f.root-servers.net, g.root-servers.net, h.root-servers.net, i.root-servers.net, j.root-servers.net, k.root-servers.net, l.root-servers.net, m.root-servers.net

**¿Cuántas redirecciones DNS son posibles?**
No hay límite de redirecciones, pero si los servidores no están disponibles (proveedores deconectados) no recibiremos ninguna dirección IP de vuelta.

**¿Qué son los servidores DNS Raíz?**
**Servidores DNS Raíz** son servidores de nombres para la zona raíz del DNS. Son el primer paso en la traducción de los nombres de host legibles en direcciones IP.

**¿Para qué montar un servidor si simplemente escribiendo en un fichero la relación IP/Nombre el sistema ya funcionaría?**
Porque en el fichero etc/hosts asignamos las direcciones IP, pero solo funcionaría en nuestro equipo.


**Según lo expuesto, y si en tu configuración de red del sistema operativo solamente posees un servidor DNS, entonces: ¿cuál sería el proceso para encontrar la IP de la dirección web: http://www.debian.org/distrib/netinst?**

Hay 10 pasos:
1. Escribimos el nombre del dominio en un navegador y la consulta viaja por Internet y es recibida por una resolución DNS recursiva.
2. La resolución consulta un servidor de nombres raíz de DNS.
3. El servidor raíz responde con la dirección de un servidor DNS de dominios de primer nivel.
4. La resolución hará una solicitud al dominio de primer nivel.
5. El servidor de dominio de primer nivel responderá con la dirección IP del servidor de nombres de dominio.
6. La resolución recursiva envía una consulta al servidor de nombres de dominio
7. La dirección IP de **http://www.debian.org/distrib/netinst?** se devolverá a la resolución desde el servidor de nombres.
8. La resolución de DNS responderá al navegador web con la dirección IP del dominio solicitado inicialmente.
9. El navegador hará una solicitud de HTTP a la dirección IP.
10. El servidor en esa IP devuelve la página web para que se procese en el navegado

**¿Es posible si dispones de una conexión a Internet con IP dinámica ofrecer servicios en Internet?**
Es posible pero no recomendable porque cada vez que nos conectamos a Internet nuestra dirección IP cambia, por lo que tenemos que especificar cada vez que cambiamos la dirección IP.

**¿Qué es ICANN?**
**ICANN (Corporación de Internet para la Asignación de Nombres y Números)** es una organización que opera a nivel internacional y es la responsable de asignar las direcciones del protocolo IP, de los identificadores de protocolo, de las funciones de gestión del sistema de dominio y de la administración del sistema de servidores raíz.