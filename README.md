# Desarrollo del _inflight software_ para la OBC secundaria del Satélite Quetzal-2

## Descripción

El Quetzal-2 es un nanosatélite CubeSat 2U desarrollado como proyecto académico
por estudiantes y _staff_ de la Universidad del Valle de Guatemala el cual pone
a prueba una _On-Board Computer_ (OBC) diseñada localmente que ejecuta una
inteligencia artificial capaz de identificar nubes. Este nanosatélite cuenta con
una computadora a bordo compuesta de por dos unidades de procesamiento, una OBC
principal basada en hardware comercial de GomSpace y otra OBC secundaria
desarrollada localmente utilizando Portentas H7 de Arduino.

Las OBC son sistemas vitales dentro de una misión espacial puesto que gestionan
todos los subsistemas del satélite así como la comunicación entre estos. Este
proyecto se centra en las bases de esta OBC local a nivel de _software_,
sentando las bases para los distintos modos de operación que necesita la misión,
la toma de fotografías y la interoperabilidad entre las dos unidades de
procesamiento que componen la OBC completa.

El impacto de esta OBC desarrollada localmente representa un gran punto de
inicio para próximas misiones espaciales, bajando aún más la barrera económica
de entrada para desarrollar misiones espaciales con respecto a soluciones
_of-the-shelf_, puesto que demuestra que no es necesario el uso de _hardware_
altamente costoso con muchas más protecciones para llevar a cabo una misión
exitosa.

## Tecnologías Utilizadas

- C/C++
- Make
- Arduino IDE
- AFL++

## Requisitos Previos

- Sistema operativo Linux.

- [Nix](https://nixos.org/) 2+.

- Habilita [Nix Flakes](https://nixos.wiki/wiki/flakes).

- Si no se quiere/puede usar Nix, entonces se recomienda leer el archivo
  `./src/flake.nix`. Específicamente la lista que inicia en la línea 22. La cual
  lista todas las dependencias del proyecto a instalar manualmente.

## Instalación

1. Clonar el repositorio:

   ```bash
   git clone https://github.com/GraduacionesUVG/2026-22386-flavio-andre-galan-donis.git
   cd 2026-22386-flavio-andre-galan-donis/src
   ```

1. Instalar dependencias:

   ```bash
   nix develop
   ```

1. Compilar librerias y _frameworks_:

   ```bash
   xc lib
   xc unity
   ```

1. Compilar el código para el core M4 y M7:

   ```bash
   xc m4
   xc m7
   ```

1. Flashear el código en el M7 y luego en la M4 de una Portenta conectada:

   ```bash
   xc flash m4
   xc flash m7
   ```

## Capturas

Las capturas de pantalla del sistema se encuentran en [`/capturas`](capturas/)
(mínimo 10)

## Demo

El video demostrativo se encuentra en [`/demo/demo.mp4`](demo/demo.mp4)

## Documentación

El informe final del proyecto está disponible en
[`/docs/informe_final.pdf`](docs/informe_final.pdf)

El consentimiento de uso de foto y video firmado se encuentra en
[`/docs/consentimiento_firmado.pdf`](docs/consentimiento_firmado.pdf)

## Autores

- Flavio André Galán Donis
- 22386

## Licencia

MIT
