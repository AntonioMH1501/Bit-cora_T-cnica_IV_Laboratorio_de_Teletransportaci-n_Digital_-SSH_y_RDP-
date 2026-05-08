# Bit-cora_T-cnica_IV_Laboratorio_de_Teletransportaci-n_Digital_-SSH_y_RDP-

## PREPARACIÓN DE ENTORNO

El primer paso era crear una carpeta en el escritorio, con el nombre SI_BitácoraIV_AntonioMuñozHerrera. Más adelante, tuve que crear un archivo docker-compose dentro, con el código facilitado en la actividad. Más adelante, lo abrí en VisualStudio y dentro de terminal, añadí el comando docker-compose up -d, creando el contenedor. 

## FASE DE EJECUCIÓN

En el primero de los pasos era abrir PowerShell y conectar a través del comando ssh alumno@localhost -p 2222. El primero de los probleas llegó cuando el mensaje que salió en terminal fue el siguiente: 
<img width="770" height="336" alt="image" src="https://github.com/user-attachments/assets/a61e67a5-443c-4fb5-b36c-e0d436968817" />

Para solucionar esto, había que cambiar la parte del comando de localhost por la IP de localhost, que es 127.0.0.1, tras esto, ya pedía ingresar la contraseña y me permitió conectar. 

El siguiente paso era crear una llave, para lo que se usó el siguiente comando: ssh-keygen -t ed25519 -C "antoniomunoz.25@campuscamara.es", tras lo cuál me pidió un archivo para hacer copia, que dejé en blanco y me dió el certificado requerido:

<img width="633" height="488" alt="image" src="https://github.com/user-attachments/assets/35aabfe7-8970-4f2f-87f4-6eb383ea02ab" />

Más adelante, se me pedía que copiase mi llave pública al servidor, tarea que hice poniendo el siguiente comando: ssh-keygen -t ed25519 -C "tu_correo@ejemplo.com"

<img width="641" height="303" alt="image" src="https://github.com/user-attachments/assets/36db74c8-e14d-4cec-b081-8e759aafa7cc" />

## RDP: Escritorio en tu Navegador

Una vez completado el mantenimiento desde terminal, se pedía que se realizasen una serie de tareas desde el navegador y el escritorio remoto. La primera de ellas era abrir el escritorio remoto y apuntar hacia localhost:3389, pero daba el siguiente error: 

<img width="664" height="530" alt="image" src="https://github.com/user-attachments/assets/8881a2a5-2d40-46af-a96d-e12d5858116c" />

La alternativa a esto era dirigirse desde el navegador a localhost:3000, que muestra un escritorio de Ubuntu gracias a Apache Guacamole. Dentro de este debíamos crear un archivo de texto llamado PRUEBA_LOGRADA.txt

<img width="955" height="825" alt="image" src="https://github.com/user-attachments/assets/56d46de6-f467-49fd-890f-2f3d1a05bdae" />

## MODIFICACIONES DE SSHD_CONFIG

Por último, pedía hacer modificaciones dentro de sshd_config, para lo que había que poer lo siguiente en terminal: sudo nano sshd_config, tras lo que pedía la contraseña, que introduje igual que en los pasos anteriores. Tras ello, me devolvió el siguiente mensaje:

<img width="508" height="261" alt="image" src="https://github.com/user-attachments/assets/12fc8a1b-f219-4e99-9c1e-69f8932a0f7a" />

Esto significa que alumno no se encuentra dentro de los archivos sudoers

## REFLEXIONES

Durante la actividad, me he dado cuenta de que trabajar mediante SSH es más cómodo y sencillo, ya que permite las conexiones desde el anfitrión, dando facilidades como copiar y pegar o tener múltiples ventanas al mismo tiempo. Además, he descubierto la posibilidad de acceder a un escritorio remoto de Ubuntu a través del navegador
