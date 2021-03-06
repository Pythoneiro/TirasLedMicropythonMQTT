# Proyecto: tiras LED domotizadas con PIR y Arduino/ESP8266

## Descripción del proyecto

Se quieren instalar un conjunto de tiras LED de un sólo color, pegadas por los muebles de la cocina (principalmente por debajo y por arriba). Habrá un total de cuatro grupos de tiras LED que se podrán encender y apagar por separado.

Las tiras se podrán controlar tanto por Wifi (MQTT) como de forma automática, encendiéndose por movimiento con un PIR (de forma independiente, por lo que cualquier desconexión de la red Wifi o broker MQTT no dejará las luces sin funcionamiento).

El encendido y apagado de las tiras se realizará con un módulo de 4 relés. Las tiras serán de 12V.

El microcontrolador a utilizar será un ESP8266 (tipo Wemos D1 Mini). El código se realizará en Micropython.

## Requisitos

### Hardware

- Placa tipo Wemos D1 Mini
- Fuente 12Vcc
- Conversor 12Vcc > 5Vcc (preferiblemente Buck Converter ajustable)
- Tiras LED
- 4 relés (1 módulo de 4 relés, o 4 módulos de 1 relé) - preferiblemente SSR (relés de estado sólido)
- PIR
- Pin headers macho y hembra
- Conectores (fichas/clemas) con tornillo (varias de 2 pines mínimo)
- Placa THT (agujeros), cables, estaño, soldador / Breadboard y cables

### Software

- Firmware de Micropython

## Funcionamiento

- Cuando se detecte movimiento por el PIR, las tiras se encenderán
- Cuando no se detecte movimiento por el PIR, las tiras se apagarán tras cierto tiempo
- El funcionamiento debería poderse configurar por MQTT
- Adicionalmente se podrían implementar controles hardware (botones, pulsadores, interruptores)

## Esquema actual

- Los relés se conectan externamente
- La placa de relés es una placa con 4 relés sólidos
- Las conexiones se realizan todas con fichas de 2 pines con tornillo

![Esquema](ControladorLEDsCocina_SSR_schema.png)

## Esquema tipo breadboard (alpha)

- Primer prototipo
- La placa de relés sería una sola placa con 4 relés normales

![Esquema](ControladorLEDsCocina_bb.png)
