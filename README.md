# SLAM PEPPER ROBOT

## Requisitos
1. Para que este repositorio funcione se necesitaran los siguientes paquetes:
   slam gmapping y teleop twist keyboard
2. Abra una ventana de comandos:
   `sudo apt update`
   `sudo apt-get install ros-melodic-teleop-twist-keyboard`
   una vez que termine la instalación haga:
   `sudo apt install ros-melodic-slam-gmapping`
   
3. Ubuntu es la 18 y ROS Melodic 
## Cómo usar

1. Clona este repositorio en la carpeta src del ws.
2. Regresa al ws y ejecuta el comando `catkin_make`.
3. Iniciar el merge:
   `roslaunch ira_laser_tools laserscan_multi_merger.launch`
4. Iniciar Gmapping:
   `rosrun gmapping slam_gmapping scan:=/scan_multi`
5. Iniiciar rviz:
   `roslaunch gmapping slam.launch`
   Se puede usar el teclado para que pepper se mueva: i (adelante), j (giro izq), l (giro derecha), m(atras) y k (detener)
6. Guardar mapa:
   `rosrun map_server map_saver -f my_world_map`
