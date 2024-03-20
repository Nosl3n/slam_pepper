# SLAM para el Robot Pepper

Este repositorio contiene los paquetes necesarios para realizar Simultaneous Localization and Mapping (SLAM) utilizando el robot Pepper en un entorno ROS (Robot Operating System). Con este sistema, el robot puede crear un mapa del entorno mientras se localiza en él.

## Requisitos

- **Ubuntu 18:** Este repositorio ha sido probado en Ubuntu 18.
- **ROS Melodic:** Se requiere ROS Melodic para ejecutar los nodos y paquetes proporcionados aquí.
- **Paquetes ROS:**
  - `ros-melodic-teleop-twist-keyboard`: Para controlar el robot Pepper utilizando el teclado.
  - `ros-melodic-slam-gmapping`: Para realizar el mapeo utilizando el algoritmo GMapping.

## Instalación de dependencias

Para instalar los paquetes necesarios, ejecute los siguientes comandos en una ventana de terminal:

```bash
sudo apt update
sudo apt install ros-melodic-teleop-twist-keyboard
sudo apt install ros-melodic-slam-gmapping
```
## Uso

1. **Clonación del Repositorio:**
   Clone este repositorio dentro del directorio `src` de su espacio de trabajo de ROS:

   ```bash
   git clone <URL_DEL_REPOSITORIO> /ruta/a/tu/workspace/src
   ```
   
2. **Compilación:**
   Regrese al directorio de su espacio de trabajo y compile los paquetes utilizando catkin_make:
  
    ```bash
    cd /ruta/a/tu/workspace
    catkin_make
    ```
    
3. **Iniciar el Proceso de Fusión de Láseres:**
   Antes de iniciar el mapeo, inicie el proceso de fusión de láseres con el siguiente comando:
  
    ```bash
    roslaunch ira_laser_tools laserscan_multi_merger.launch
    ```
    
4. **Iniciar GMapping:**
   Una vez que el proceso de fusión de láseres esté en marcha, inicie GMapping con el siguiente comando:
  
    ```bash
    rosrun gmapping slam_gmapping scan:=/scan_multi
    ```

5. **Visualización con Rviz y control con teclado:**
   Para visualizar el mapeo en tiempo real, inicie Rviz con la configuración adecuada:
  
    ```bash
    roslaunch gmapping slam.launch
    ```
    
    Para controlar el robot puede usar:

    ```bash
    Reading from the keyboard  and Publishing to Twist!
    ---------------------------
    Moving around:
       u    i    o
       j    k    l
       m    ,    .
    
    For Holonomic mode (strafing), hold down the shift key:
    ---------------------------
       U    I    O
       J    K    L
       M    <    >
    
    t : up (+z)
    b : down (-z)
    
    anything else : stop
    
    q/z : increase/decrease max speeds by 10%
    w/x : increase/decrease only linear speed by 10%
    e/c : increase/decrease only angular speed by 10%
    
    CTRL-C to quit
    ```
5. **Guardar el Mapa::**
   Cuando esté satisfecho con el mapa generado, puede guardarlo utilizando el siguiente comando:
  
    ```bash
    rosrun map_server map_saver -f my_world_map
    ```
