# DVWA (Damn Vulnerable Web Application)

**DVWA** es una aplicación web vulnerable diseñada para aprender y practicar hacking ético. Se utiliza para probar ataques comunes como inyección SQL, XSS, y fuerza bruta.

## Niveles de seguridad en DVWA

1. **Low (Bajo)**  
   - Muy vulnerable. No hay protección contra ataques comunes.
   - Ideal para principiantes.

2. **Medium (Medio)**  
   - Algunas protecciones básicas, como bloqueo de intentos fallidos.
   - Apto para usuarios intermedios.

3. **High (Alto)**  
   - Muchas protecciones, como validaciones de entrada y CSRF.
   - Para usuarios avanzados.

4. **Impossible (Imposible)**  
   - Nivel más seguro, casi invulnerable.
   - Reto para expertos.

### Configuración de niveles de seguridad

Puedes cambiar el nivel de seguridad de DVWA desde la página de configuración, generalmente ubicada en `http://127.0.0.1/dvwa/security.php`. 

Cada nivel de seguridad está diseñado para ayudar a los usuarios a practicar diferentes técnicas de explotación y a mejorar sus habilidades en ciberseguridad.

### Lanzar página desde kali

- Clonamos el repositorio
`git clone https://github.com/digininja/DVWA.git`

- Instalamos depencias
`sudo apt update`
`sudo apt install apache2 php php-mysqli mariadb-server`

- Lanzamos desde el terminal
`dvwa-start`
- Si queremos pararlo: 
`dvwa-stop`
