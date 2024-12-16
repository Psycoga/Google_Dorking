**Low (Bajo)**  
   - Muy vulnerable. No hay protección contra ataques comunes.
   - Ideal para principiantes.

## Brute Force

- Lo primero de todo es identificar donde vamos a lanzar nuestro ataque de fuerza bruta, en este caso va a ser este login: 

![[Pasted image 20241216102517.png]]

### Hydra

Es una herramienta de fuerza bruta usada para probar contraseñas y autenticaciones en diversos protocolos como SSH, FTP y HTTP. Es rápida, personalizable y utilizada en pruebas de seguridad. Su uso sin permiso puede ser ilegal.

- El comando ha utilizar va a ser el siguiente: 
  `hydra -L /home/kali/Downloads/usuarios.txt -P /home/kali/Downloads/rockyou.txt 127.0.0.1 -s 42001 http-get-form "/vulnerabilities/brute/:username=^USER^&password=^PASS^&Login=Login:Username and/or password incorrect"`
#### Comando Hydra para Fuerza Bruta en DVWA

Explicación
- **-L**: Archivo con lista de usuarios (uno por línea).
- **-P:** Archivo con lista de contraseñas.
- **127.0.0.1:** IP del servidor objetivo.
- **-s 42001:** Puerto donde corre DVWA.
- **http-get-form:** Método HTTP usado (GET).
- **/vulnerabilities/brute/::** Ruta del formulario.
- **username=^USER^:** Hydra reemplaza ^USER^ con cada usuario.
- **password=^PASS^:** Hydra reemplaza ^PASS^ con cada contraseña.
- **Login=Login:** Nombre del botón de envío.
- **Username and/or password incorrect:** Texto de error al fallar el login. 
Una vez hydra termine nos va a dar este resultado: 
`1 of 1 target successfully completed, 13170 valid passwords found` 

**OPCIONAL** : Podemos meter los resultado en un archivo de texto plano, con -o y el nombre del archivo al que se la vamos a enviar, ejemplo: 
`-o resultados.txt`

**IMPORTANTE:** Para que hydra funcione correctamente es necesario ver el formulario de la página para que los parámetros se pongan correctamente.


### Command Injection

![[Pasted image 20241216111535.png]]

Es una vulnerabilidad de seguridad que ocurre cuando un atacante puede ejecutar comandos arbitrarios en el sistema operativo subyacente de un servidor o aplicación. Esto generalmente sucede cuando una aplicación no valida correctamente la entrada del usuario y permite que los datos ingresados se usen para formar un comando del sistema operativo.

Si ponemos una dirección ip como nos dice nos dará esto: 

![[Pasted image 20241216111653.png]]

- **Inyección básica** 

Repetimos lo anterior, pero esta vez vamos a utilizar un "pipe":
`8.8.8.8 | ls`

El resultado que vamos a esperamos es este: 
![[Pasted image 20241216111831.png]]

### Vulnerability: Cross Site Request Forgery (CSRF)





