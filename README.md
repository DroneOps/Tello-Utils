# Utilidades para DJI Tello

Este repositorio contiene scripts rápidos para facilitarte la vida al momento de volar y diagnosticar los drones Tello. 

## Instalación

Solo necesitas instalar las librerías de Python requeridas para comunicarte con el dron y generar gráficas:

```bash
pip install -r requirements.txt
```

*(Recuerda conectarte al WiFi del dron antes de correr los scripts).*

## ¿Qué hace cada script?

### 1. Revisor de Estado Seguro (`check_status.py`)
¡Úsalo siempre antes de tu primer vuelo! Se conecta al dron para revisar que la batería tenga suficiente carga (más del 10%) y que la temperatura interna no esté a punto de quemar la placa. Si algo está mal, el script bloqueará la ejecución por seguridad.

```bash
python3 check_status.py
```

### 2. Prueba de Motores y Ejes (`axis_test.py`)
Sirve para hacer una prueba rápida de movimiento en un solo eje. Al terminar, te genera una gráfica automática en la carpeta `docs/axis_test_plots/` para que veas cómo se comportó la velocidad y altura.
> **Advertencia:** El dron va a volar físicamente al correr esto. Asegúrate de tener espacio abierto y sin obstáculos.

```bash
python3 axis_test.py
```

### 3. Conexión WiFi Automática (`connect_wifi.sh` y `tello.conf`)
Lee el nombre de la red del dron desde el archivo `tello.conf` e intenta conectar tu computadora automáticamente a él. 
> **Ojo:** Este script de bash usa comandos internos de Linux (`nmcli`). Si estás en Windows o Mac, es mejor que te conectes al WiFi del Tello manualmente haciendo clic en el ícono de red de tu computadora.

```bash
./connect_wifi.sh
```

## Autor
Alejandro Mojarras - mojarrasalejandro@gmail.com

Project developed for the technical advancement and benefit of the **DroneOps** student group at **Tecnológico de Monterrey (ITESM), Campus Guadalajara**.
