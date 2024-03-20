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
