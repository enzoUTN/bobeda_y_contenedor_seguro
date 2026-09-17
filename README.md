# Mi Bóveda y Contenedor Seguro Fundamental
## Introducción y herramientas
Para esta entrega se integrará los conceptos de Gestión de identidad con cifrado de datos. Construiremos un entorno donde los accesos estén protegidos y los archivos más sensibles permanezcan inaccesibles, incluso al perder el control físico del dispositivo. 
Utilizaremos la máquina virtual, que creamos en anteriores entregas, para construir el entorno seguro de nuestros accesos y archivos. Además de incluir herramientas como KeePassXC, Bitwarden y VeraCrypt mostrando como se utilizan estas herramientas y explicando las razones de utilizarlas.

## 1 - Configuración de la Bóveda de Identidad
Para este apartado, vamos a usar dos herramientas muy similares, que son Bitwarden y KeePassXC. En un entorno real, no es necesario usar las dos herramientas, podemos elegir una sola. Pero en este caso elijo las dos para mostrar paso a paso de su funcionamiento. 
En el caso de Bitwarden vamos a usar la opción en la nube, agregando una extensión en el navegador. Y en el caso de KeePassXC lo vamos a usar de manera local instalando su versión Desktop. Además, a las dos herramientas vamos a agregarles métodos de protección adicional. 

Estas dos herramientas mencionadas son gestores de contraseñas. Actúan como una caja fuerte guardando todas las “llaves” de acceso, como por ejemplo: la contraseña de tu homeBanking o de tu cuenta de Google. El gestor de contraseña requiere una contraseña maestra para acceder a la "caja fuerte". Esta misma debería ser una frase de contraseña, es decir un conjunto de palabras fácil de recordar, pero imposible de adivinar por una máquina (por ejemplo: "CursoDeCiberseguridad2026Github#"). Otra ventaja que nos da el gestor de contraseñas es que nos puede generar de manera automática contraseñas mas seguras, sin que tengamos que pensar algun patron seguro. 

La diferencia entre las dos herramientas es que Bitwarden se sincroniza en la nube, pudiendo ser utilizada en cualquier dispositivo (computadora, smartphone o tablet) de manera sencilla. En cambio, KeePassXC no usa la nube, sino que crea un archivo en el dispositivo que contiene una base de datos con las contraseñas, y para poder pasar ese gestor de contraseñas a otro dispositivo deberíamos mover ese archivo. La ventaja de este último es que hay menos riesgos de brechas en servidores externos. 

### KeePassXC
Descargamos e instalamos KeePassXC desde la pagina oficial para el sistema operativo utilizado (en este caso linux).

![Descarga KeePassXC](https://github.com/user-attachments/assets/78a6d929-5e88-4356-9c85-08102fa3e9b9)

En la siguiente imagen podemos observar como es la interfaz de KeePassXC en su primer inicio.

![KeePassXC](https://github.com/user-attachments/assets/c969ba60-d948-4bdc-91a8-52966e1a912a)

Vamos a crear la base de datos en donde se guardaran los usuarios y contraseñas. Hacemos Click en Create Database. Nos pedira ingresar el nombre de la base de datos y una descripcion opcional. En este caso la base de datos se llamara ciberseguridad.

![databases](https://github.com/user-attachments/assets/4a0f1b57-2730-4c1f-8e68-5fb2e840ee78)

Mas adelante nos pedira agregar una contraseña a la base de datos. Esta es la contraseña maestra que mencionamos anteriormente. Introducimos una contraseña de tipo frase, en donde sean palabras facil de recordar pero dificil de adivinar por una maquina (ejemplo: CursoDeCiberseguridad2026Github#). En este apartado tambien podemos agregar la proteccion adicional, pero lo vamos a hacer mas adelante. Importante no olvidar la contraseña maestra. 

![databases password](https://github.com/user-attachments/assets/0def401e-407e-451c-9f63-67158aa33c60)

Finalmente nos genera un archivo .kbdx que guardaremos en una carpeta segura. 

Proseguimos a cargar las credenciales y generaremos las contraseñas desde la misma aplicacion. En este caso vamos simular 3 credenciales:

![databases password](https://github.com/user-attachments/assets/f29395c5-5a14-4d39-af72-4917ccb0fdfd)

En la anterior imagen observamos la ventana para agregar una credencial y ademas al lado del password hay un icono de extension en donde nos permite generar una contraseña con distintos parametros (cantidad de caracteres, longitud, tipo de caracter, etc). En este caso las contraseñas van a tener una longitud de 20 y de tipo ASCII. Cabe aclarar que la contraseña de la imagen es solo de ejemplo, no es la contraseña real que vamos a ingresar, ya que nunca se debe mostrar publicamente una contraseña por mas segura que sea. 

Agregamos las 3 credenciales de ejemplo con las contraseñas generadas por la misma aplicacion. 

![credenciales](https://github.com/user-attachments/assets/ab433131-ed27-4e4e-ad03-5de9d1dcd370)

De esta forma vamos a ir agregando las credenciales que necesitamos o si requerimos generar una nueva credencial, podemos utilizar el generador nativo que trae KeepassXC. 

Finalmente vamos a agregar una proteccion adicional: Vamos a Databases -> Databases Settings -> Security -> Add addition Protection -> Add Key File. Hacemos Click en generar y nos pedira guardar el archivo en una carpeta. De esta forma se genera un archivo adicional, que el gestor requerira para su uso y acceso.   

![credenciales keyfile](https://github.com/user-attachments/assets/c951e839-4dd5-48e5-bc3d-a032509a0bd9)

### Bitwarden











