
## Acceso a la configuración de un servidor
- `intext:"dhcpd.conf" "index of"`
### ¿Cómo funciona?

Busca archivos **`dhcpd.conf`** (configuraciones DHCP) expuestos en servidores que permiten el **listado de directorios** ("index of"). Google encuentra estos archivos porque los servidores están mal configurados, mostrando archivos públicos que no deberían ser accesibles sin restricciones.
### ¿Cómo evitarlo?

- **Deshabilitando el listado** de directorios en el servidor web.
- **Configurando correctamente los permisos** de archivos y directorios de la página web
- **Usar autenticación** para restringir el acceso a directorios importantes.

## Configuración ssh de un servidor
`intitle:index of /etc/ssh`

### ¿Cómo funciona?

Busca servidores que tienen habilitado el **listado de directorios** y exponen el contenido del directorio **`/etc/ssh`**, que generalmente contiene configuraciones sensibles del servicio **SSH** (como `sshd_config`, claves, etc.). Esto ocurre cuando un servidor está mal configurado, permitiendo a Google indexar y mostrar directorios que deberían estar protegidos.

### ¿Cómo evitarlo?

- **Cambiar el Puerto por Defecto de SSH**: Cambia el puerto por defecto (22) a uno menos común para reducir el riesgo de ataques automáticos.
- **Usar Autenticación basada en Claves**: Deshabilita la autenticación por contraseña y utiliza claves SSH para mejorar la seguridad.
- **Limitar el Acceso SSH**: Configura el archivo de configuración de SSH (`/etc/ssh/sshd_config`) para permitir solo conexiones desde direcciones IP específicas si es posible.


## Acceso a una cámara por IP

`intitle:"Device(IP CAMERA)" "language" -com|net`

### ¿Cómo funciona?

Como todos los dorks que estamos haciendo, simplemente filtra la información que necesitamos, en este caso cogemos las ips que están públicas, y que este relacionadas con una cámara. Nos saldría algo como esto: 

![[Screenshot from 2024-10-22 13-27-55.png]]

