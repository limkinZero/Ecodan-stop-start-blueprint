# Ecodan stop-start blueprint

Blueprints para el control de paradas/arranque de aerotermia Mitsubishi Ecodan. Controla si la máquina realiza más de ún numero paradas configurable en un periodo de tiempo y la apaga. Trascurrido un tiempo configurable la vuelve a encender. Tiene en cuenta que no esté haciendo desescarches.

Blueprints:

- Ecodan_registro_paradas.yaml
- Ecodan_acción_parar_notificar.yaml


🧩 Helpers para Mitsubishi Ecodan

🔁 Es necesario crear dos helpers. Están disponibles en el fichero `Helpers.yaml`. Asegúrate de que en el blueprint uses "Mitsubishi Ecodan" (con ese nombre exacto) en el campo nombre_dispositivo para que los nombres coincidan correctamente o ajústalos según el nombre que le des luego en la configuración del blueprint:

```yaml
counter:
  mitsubishi_ecodan_paradas_contador:
    name: Contador de paradas Mitsubishi Ecodan
    min: 0
    max: 10
    step: 1
    initial: 0

timer:
  mitsubishi_ecodan_monitor_tiempo:
    name: Rango temporal para el control del número de paradas
    duration: "00:30:00"
```

📥 Importar los Blueprint desde una URL

Accede a Home Assistant y navega a Configuración > Automatizaciones y Escenas > Blueprints.

Haz clic en el botón "Importar Blueprint" en la esquina inferior derecha.

En el campo de URL, pega la siguiente dirección:

`Ecodan_registro_paradas.yaml`

https://github.com/limkinZero/Ecodan-stop-start-blueprint/blob/main/Ecodan_registro_paradas.yaml


`Ecodan_acción_parar_notificar.yaml`

https://github.com/limkinZero/Ecodan-stop-start-blueprint/blob/main/Ecodan_acción_parar_notificar.yaml


⚙️ Configurar blueprints

Al crear una nueva automatización basada en el blueprint, se te solicitará que completes los siguientes campos:

- Sensor de potencia: Selecciona el sensor que mide el consumo de la Mitsubishi Ecodan.

- Umbral de consumo (W): Valor en vatios (W) por debajo del cual se considera una parada.

- Unbral de activación: Valor de W anterior al descenso (ej. >400W → <100W) para considerar que realmente estaba funcionando antes.

- Interruptor del dispositivo: Selecciona el switch que controla la alimentación de la Mitsubishi Ecodan.

- Sensor binario de desescarche: Selecciona el sensor que indica si el dispositivo está en modo desescarche.

- Servicio de notificación móvil: Introduce el servicio de notificación que utilizas, por ejemplo, notify.mobile_app_tu_telefono.

- Nombre del dispositivo: Introduce "Mitsubishi Ecodan".

- Tiempo de apagado antes de encender (HH:MM:SS): Establece el tiempo deseado, por ejemplo, 02:00:00.