# Mi Bóveda y Contenedor Seguro Fundamental
## Introducción y herramientas
Para esta entrega se integrará los conceptos de Gestión de identidad con cifrado de datos. Construiremos un entorno donde los accesos estén protegidos y los archivos más sensibles permanezcan inaccesibles, incluso al perder el control físico del dispositivo. 
Utilizaremos la máquina virtual, que creamos en anteriores entregas, para construir el entorno seguro de nuestros accesos y archivos. Además de incluir herramientas como KeePassXC, Bitwarden y VeraCrypt mostrando como se utilizan estas herramientas y explicando las razones de utilizarlas.

## 1 - Configuración de la Bóveda de Identidad
Para este apartado, vamos a usar dos herramientas muy similares, que son Bitwarden y KeePassXC. En un entorno real, no es necesario usar las dos herramientas, podemos elegir una sola. Pero en este caso elijo las dos para mostrar paso a paso de su funcionamiento. 
En el caso de Bitwarden vamos a usar la opción en la nube, agregando una extensión en el navegador. Y en el caso de KeePassXC lo vamos a usar de manera local instalando su versión Desktop. Además, a las dos herramientas vamos a agregarles métodos de protección adicional. 

Estas dos herramientas mencionadas son gestores de contraseñas. Actúan como una caja fuerte guardando todas las “llaves” de acceso, como por ejemplo: la contraseña de tu homeBanking o de tu cuenta de Google. El gestor de contraseña requiere una contraseña maestra para acceder a la "caja fuerte". Esta misma debería ser una frase de contraseña, es decir un conjunto de palabras fácil de recordar, pero imposible de adivinar por una máquina (por ejemplo: "CursoDeCiberseguridad2026Github#"). Otra ventaja que nos da el gestor de contraseñas es que nos puede generar de manera automática contraseñas variadas, sin que tengamos que pensar alguna en particular. 

La diferencia entre las dos herramientas es que Bitwarden se sincroniza en la nube, pudiendo ser utilizada en cualquier dispositivo (computadora, smartphone o tablet) de manera sencilla. En cambio, KeePassXC no usa la nube, sino que crea un archivo en el dispositivo que contiene una base de datos con las contraseñas, y para poder pasar ese gestor de contraseñas a otro dispositivo deberíamos mover ese archivo. La ventaja de este último es que hay menos riesgos de brechas en servidores externos. 
