# Mi Bóveda y Contenedor Seguro Fundamental
## Introducción y herramientas
Para esta entrega se integrará los conceptos de Gestión de identidad con cifrado de datos. Construiremos un entorno donde los accesos estén protegidos y los archivos más sensibles permanezcan inaccesibles, incluso al perder el control físico del dispositivo. 
Utilizaremos la máquina virtual, que creamos en anteriores entregas, para construir el entorno seguro de nuestros accesos y archivos. Además de incluir herramientas como KeePassXC, Bitwarden y VeraCrypt mostrando como se utilizan estas herramientas y explicando las razones de utilizarlas.

## 1 - Configuración de la Bóveda de Identidad
Para este apartado, vamos a usar dos herramientas muy similares, que son Bitwarden y KeePassXC. En un entorno real, no es necesario usar las dos herramientas, podemos elegir una sola. Pero en este caso elijo las dos para mostrar paso a paso de su funcionamiento. 
En el caso de Bitwarden vamos a usar la opción en la nube, agregando una extensión en el navegador. Y en el caso de KeePassXC lo vamos a usar de manera local instalando su versión Desktop. Además, a las dos herramientas vamos a agregarles métodos de protección adicional. 

Estas dos herramientas mencionadas son gestores de contraseñas. Actúan como una caja fuerte guardando todas las “llaves” de acceso, como por ejemplo: la contraseña de tu homeBanking o de tu cuenta de Google. El gestor de contraseña requiere una contraseña maestra para acceder a la "caja fuerte". Esta misma debería ser una frase de contraseña, es decir un conjunto de palabras fácil de recordar, pero imposible de adivinar por una máquina (por ejemplo: "CursoDeCiberseguridad2026Github#"). Otra ventaja que nos da el gestor de contraseñas es que nos puede generar de manera automática contraseñas mas seguras, sin que tengamos que pensar algun patron seguro. 

La diferencia entre las dos herramientas es que Bitwarden se sincroniza en la nube, pudiendo ser utilizada en cualquier dispositivo (computadora, smartphone o tablet) de manera sencilla. En cambio, KeePassXC no usa la nube, sino que crea un archivo en el dispositivo que contiene una base de datos con las contraseñas, y para poder pasar ese gestor de contraseñas a otro dispositivo deberíamos mover ese archivo. La ventaja de este último es que hay menos riesgos de brechas en servidores externos. 

Aclaración: Todas las contraseñas mostradas en las capturas son solo de ejemplo, con el objetivo de mostrar el formato para tener una contraseña lo menos vulnerable posible. Nunca hay que mostrar la contraseña, ni en capturas ni en mensajes. 

### KeePassXC
Descargamos e instalamos KeePassXC desde la página oficial para el sistema operativo utilizado (en este caso Linux).

![Descarga KeePassXC](https://github.com/user-attachments/assets/78a6d929-5e88-4356-9c85-08102fa3e9b9)

En la siguiente imagen podemos observar como es la interfaz de KeePassXC en su primer inicio.

![KeePassXC](https://github.com/user-attachments/assets/c969ba60-d948-4bdc-91a8-52966e1a912a)

Vamos a crear la base de datos en donde se guardaran los usuarios y contraseñas. Hacemos Click en Create Database. Nos pedirá ingresar el nombre de la base de datos y una descripción opcional. En este caso la base de datos se llamará ciberseguridad.

![databases](https://github.com/user-attachments/assets/4a0f1b57-2730-4c1f-8e68-5fb2e840ee78)

Más adelante nos pedirá agregar una contraseña a la base de datos. Esta es la contraseña maestra que mencionamos anteriormente. Introducimos una contraseña de tipo frase, en donde sean palabras facil de recordar, pero difícil de adivinar por una máquina (ejemplo: CursoDeCiberseguridad2026Github#). En este apartado también podemos agregar la proteccion adicional, pero lo vamos a hacer más adelante. Importante no olvidar la contraseña maestra. 

![databases password](https://github.com/user-attachments/assets/0def401e-407e-451c-9f63-67158aa33c60)

Finalmente, nos genera un archivo .kbdx que guardaremos en una carpeta segura. 

Proseguimos a cargar las credenciales y generaremos las contraseñas desde la misma aplicacion. En este caso vamos a simular 3 credenciales:

![databases password](https://github.com/user-attachments/assets/f29395c5-5a14-4d39-af72-4917ccb0fdfd)

En la anterior imagen observamos la ventana para agregar una credencial y además al lado del password hay un icono de extensión en donde nos permite generar una contraseña con distintos parámetros (cantidad de caracteres, longitud, tipo de carácter, etc.). En este caso las contraseñas van a tener una longitud de 20 y de tipo ASCII. Cabe aclarar que la contraseña de la imagen es solo de ejemplo, no es la contraseña real que vamos a ingresar, ya que nunca se debe mostrar públicamente una contraseña por más segura que sea. 

Agregamos las 3 credenciales de ejemplo con las contraseñas generadas por la misma aplicación. 

![credenciales](https://github.com/user-attachments/assets/ab433131-ed27-4e4e-ad03-5de9d1dcd370)

De esta forma vamos a ir agregando las credenciales que necesitamos o si requerimos generar una nueva credencial, podemos utilizar el generador nativo que trae KeepassXC. 

Finalmente, vamos a agregar una protección adicional: Vamos a Databases -> Databases Settings -> Security -> Add addition Protection -> Add Key File. Hacemos Clic en generar y nos pedirá guardar el archivo en una carpeta. De esta forma se genera un archivo adicional, que el gestor requerirá para su uso y acceso.   

![credenciales keyfile](https://github.com/user-attachments/assets/c951e839-4dd5-48e5-bc3d-a032509a0bd9)

### Bitwarden

Para esta herramienta vamos a instalar su extensión en el navegador Firefox.

![bitwarden extend](https://github.com/user-attachments/assets/07f01c6f-26d7-4cd2-888c-7bdc28312f2d)

Vamos a crear una cuenta en Bitwarden y configurarla desde la misma extensión.

![bitwarden extend4](https://github.com/user-attachments/assets/5b226fbc-da8f-4e2e-bdd0-caacf108662b)
![bitwarden extend3](https://github.com/user-attachments/assets/5b5ffbc3-da08-480e-ba84-94c100e286c4)

Nos pedirán confirmar la creación del usuario a través del mail que tipeamos:

![bitwarden extend2](https://github.com/user-attachments/assets/4d956016-837e-4cd2-a60e-b637a26ff768)

Una vez verificado el mail, nos redireccionará a introducir la contraseña maestra de la que estuvimos hablando y una pista de la contraseña. Para la contraseña maestra utilizamos el mismo criterio que con KeepassXC.

![bitwarden extend2s](https://github.com/user-attachments/assets/9c3c9bae-c6c1-4f52-83ff-220aecc1e544)

Cabe aclarar nuevamente que la contraseña mostrada no es la que se va a utilizar, solo es un ejemplo para mostrar el criterio de la contraseña.

Una vez creada la cuenta introducimos el usuario y contraseña maestra en la extensión de Bitwarden. Y así se vería la extensión cuando iniciamos sesión: 

![bitwarden extend2s2](https://github.com/user-attachments/assets/19bed9dc-3454-4619-bf19-c6c45ce9d838)

Proseguimos a crear 3 credenciales en la extensión: Add -> Login.

![bitwarden extend2s2s](https://github.com/user-attachments/assets/f008964f-c2c2-4022-8648-25de7a9e13dd)

Donde introducimos el password hay un icono que nos permite generar una contraseña:

![bitwarden extend2sss2s](https://github.com/user-attachments/assets/339f2a1f-48bb-413e-b279-53cc9041d458)

Hacemos click en use this password -> Save. Así con las otras 3 credenciales. Cabe aclarar que no es necesario generar una contraseña nueva, se puede guardar las que ya tienen. 

![bitwarden extend2sss2s](https://github.com/user-attachments/assets/5c83c683-2cc7-448b-9d14-0708be67822f)

![bitwarden extend2sss2s](https://github.com/user-attachments/assets/9236a009-422d-478e-8524-53c270aa6f4c)

Finalmente, vamos a agregar un método de protección adicional. En este caso vamos a activar la MFA usando la app Google Authenticator. Esto funciona de la siguiente forma: cuando un usuario quiera ingresar al baúl de contraseñas por primera vez en el dispositivo, no solo le va a pedir la contraseña maestra, sino también un código de verificación que se va a ir actualizando cada cierto tiempo en la app de Google Authenticator. De esta forma le estamos dando una doble capa de seguridad a nuestro gestor de contraseñas.

Para eso entramos a la página oficial de Bitwarden -> Iniciamos sesión con el usuario y contraseña maestra -> Settings -> Security -> Two-step Login y seleccionamos la opcion Authenticator App.  

![bitwarden extend2ssss2s](https://github.com/user-attachments/assets/966b4416-a8ad-448c-95b6-7138a1c7e099)

Introducimos la contraseña maestra y nos mostrara un qr que tenemos que escanear con la aplicacion deseada, en este caso Google Authenticator. Confirmamos agregando un codigo de 6 digitos (que nos otorga Google Authenticator) en Bitwarden. 

![bitwarden extend2ssss2s](https://github.com/user-attachments/assets/c988ed12-798e-46cc-8295-b1c1f3ff6c54)

De esta forma, queda vinculada la App Authenticator con el gestor de contraseñas. 

![bitwarden extend2ssss2s](https://github.com/user-attachments/assets/1270cf51-6e29-4fbf-bc08-7e2af6aae8f9)

## 2 - Creación del Contenedor Cifrado con VeraCrypt



















