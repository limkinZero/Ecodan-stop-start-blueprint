# Ecodan stop-start blueprint
Blueprint para el control de paradas/arranque de aerotermia Mitsubishi Ecodan. Controla si la máquina realiza más de 3 paradas en un periodo de tiempo y la apaga. Trascurrido un tiempo configurable la vuelve a encender. Tiene en cuenta que no esté haciendo desescarches.

🧩 Helpers para Mitsubishi Ecodan

🔁 Es necesario crear dos helpers. Están disponibles en el fichero `Helpers.yaml`. Asegúrate de que en el blueprint uses "Mitsubishi Ecodan" (con ese nombre exacto) en el campo nombre_dispositivo para que los nombres coincidan correctamente o ajustalos según el nombre que le des luego en la configuración del blueprint:

```yaml
input_number:
  mitsubishi_ecodan_paradas_contador:
    name: Contador de paradas Mitsubishi Ecodan
    min: 0
    max: 20
    step: 1
    initial: 0

timer:
  mitsubishi_ecodan_monitor_tiempo:
    name: Rango temporal para el control del número de paradas
    duration: "00:30:00"
```

📥 Importar el Blueprint desde una URL

Accede a Home Assistant y navega a Configuración > Automatizaciones y Escenas > Blueprints.

Haz clic en el botón "Importar Blueprint" en la esquina inferior derecha.

En el campo de URL, pega la siguiente dirección:

https://gist.github.com/limkinZero/Ecodan-stop-start-blueprint/blob/main/Blueprint_ecodan_stops_start

