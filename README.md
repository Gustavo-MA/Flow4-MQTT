# Flow4-MQTT
Actividad del flow 4 utilizando MQTT por mosquitto

Introduccion

Se crea un flow quemuestra los datos de fecha y hora en el navegador cada en pantalla utilizando noteRed y dashboard

Material Necesario

-Ubuntu 20.04 NodeJS NPM NodeRed Nodos Dashboard
-MQTT (Mosquito)

Instrucciones y requisitos previos (Previamente instalados)

Para que el flow arranque , se deben instalar los siguientes requisitos:

Instalación de NodeJS. Se recomienda tener instalado NodeJS en alguna versión LTS. Al momento de creación de este documento, se usó la versión 16.17.0LTS. Esta instalación debe incluir las Build-Tools para hacer uso de NPM Instalación de NodeRed. La instalación se realiza por NPM. Al momento de la creación de este contenido, se usó la versión 3.0.2

-sudo apt install curl curl -curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash - sudo apt-get install -y nodejs sudo apt-get install -y bulid -esential sudo npm install -g -unsite-perm node-red node red --version
Instrucciones de preparación del entorno


Introduccion

Se crea un flow en notered que es capaz de mostrar los datos de clima que recibe mediante MQTT y los grafica en un dashboard utilizando graficas  e indicadores conn un historico chart.
Material Necesario


Ubuntu 20.04 NodeJS NPM NodeRed Nodos Dashboard

Instrucciones y requisitos previos (Previamente instalados)

Para que el flow arranque , se deben instalar los siguientes requisitos:

Instalación de NodeJS. Se recomienda tener instalado NodeJS en alguna versión LTS. Al momento de creación de este documento, se usó la versión 16.17.0LTS. Esta instalación debe incluir las Build-Tools para hacer uso de NPM Instalación de NodeRed. La instalación se realiza por NPM. Al momento de la creación de este contenido, se usó la versión 3.0.2

-sudo apt install curl curl -curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash - sudo apt-get install -y nodejs sudo apt-get install -y bulid -esential sudo npm install -g -unsite-perm node-red node red --version

Instrucciones de preparación del entorno
Para ejecutar este flow, es necesario lo siguiente crear los siguientes nodos en node-red
![image](https://user-images.githubusercontent.com/111370930/188941442-9fd73fd0-a82d-4d5f-9bde-b16e9f4817bf.png)
se debe agregar dentro de los modulos de funcion las siguientes intrsucciones:

Para temperatura:
msg.payload=msg.payload.temp;
msg.topic="Temperatura";
return msg;

Para humedad:
msg.payload=msg.payload.hum;
msg.topic="Humedad"
return msg;

-----------------------------------
Creamos un dasboard que se llame FLow4-MTT
y agregamos los modulos anteriomente creados al nuevo dashboard (Temperatura, Humedad e Historico)
Y damos clic sobre done.
Y hacemos deploy
Y nos dirigimos al dashboard en hhtp:/localhost/1808/ui
Se mostrará el resultado del flow 4 visualizando3 graficas, 1 para el clima,  1 para humedad y uno que guarda el hitorico de ambas.

Instrucciones de operación

Para poder visualizar los resultados es necesario abrir una terminal de mosquito y ejecutar los commandos para mandar la informacion a un JSON mediante el puerto local, local host como se muestra a continuacion:


Resultados

A continuación puede verse una vista previa del resultado de este flow. 
![image](https://user-images.githubusercontent.com/111370930/188941684-f1dfba58-71cf-4746-9450-b529d5c658a6.png)

--------------------------
La imagen anterior muestra el primer resultado que se manda por la terminal mediante MQTT

![image](https://user-images.githubusercontent.com/111370930/188941745-8720615a-0a73-4518-8375-2625f76ffde0.png)

Podemos observar que para varios resultados la grafica historico toma significancia, pues se van ordenando los nuevos resultados a los resultados anteriormente obtenidos.

Evidencias

Repositorio github: https://github.com/Gustavo-MA/Flow4-MQTT/blob/main/README.md

Créditos

Desarrollado por Gustavo Medina e-mail: gustavo.medina@uaem.edu.mx
Introduccion
