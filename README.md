[![GitHub release (latest by date)](https://img.shields.io/github/v/release/Carlos-uy/custom-brand-icons?style=for-the-badge)](https://github.com/Carlos-uy/custom-brand-icons/releases/latest)
[![GitHub Downloads](https://img.shields.io/github/downloads/Carlos-uy/custom-brand-icons/total?style=for-the-badge)](https://github.com/Carlos-uy/custom-brand-icons/releases)
[![MIT License][mit-shield]][mit-license]
![GitHub file size in bytes](https://img.shields.io/github/size/Carlos-uy/custom-brand-icons/dist/custom-brand-icons.js?label=tamaño%20del%20plugin&style=for-the-badge)
![GitHub last commit](https://img.shields.io/github/last-commit/Carlos-uy/custom-brand-icons?style=for-the-badge)

[mit-license]: https://opensource.org/licenses/MIT
[mit-shield]: https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge

# Custom brand icons

#### Custom brand icons usa el prefijo `phu:`
#### Agrega el nombre (del icono) después de `phu:`
- Ejemplo: `phu:eggs` <img src="/icon-svg/eggs.svg" title="Vista previa" alt="Vista previa" width="24"/>
- Ejemplo: `phu:chicken` <img src="/icon-svg/chicken.svg" title="Vista previa" alt="Vista previa" width="24"/>

---

# Solicitudes de iconos

¿Quieres un icono? Abre una [solicitud de icono personalizado](https://github.com/Carlos-uy/custom-brand-icons/issues/new?assignees=Carlos-uy&labels=icon-request&template=insertion-of-new-icons.md&title=Solicitud+de+icono+personalizado) o [contribuye al proyecto](#flujo-de-trabajo-para-desarrolladores).
- Proporciona un **archivo SVG y un logo JPG de tu solicitud** (no somos lectores de mentes y no conocemos todos los iconos del mundo; si no se indica ningún nombre, agrégalo o la solicitud será ignorada) y una imagen junto con tu solicitud.
- Los enlaces a SVG o imágenes serán ignorados: debes subir los archivos dentro de tu solicitud y deben ser visibles en la publicación. `IGNORAR ESTA SIMPLE PETICIÓN RESULTARÁ EN QUE TU SOLICITUD SEA IGNORADA Y CERRADA` (si no quieres tomarte unos minutos para hacerlo, ¿por qué deberíamos nosotros dedicar tiempo a buscarlo y crearlo?).
- Aquellos que [hicieron sus propios iconos](#flujo-de-trabajo-para-desarrolladores) deben abrir pull requests en la **[rama dev](https://github.com/Carlos-uy/custom-brand-icons/pulls)**.

### Asegúrate de [instalar](#métodos-de-instalación) `custom-brand-icons.js` en `configuration.yaml` o `ui-lovelace.yaml`

## Iconify

Todos los iconos están disponibles en el [framework Iconify](https://github.com/iconify). Puedes usar los iconos con el prefijo `cbi`. Cualquiera que use este conjunto de iconos a través del framework debe cumplir con la licencia.

- Para toda la información, visita el sitio web https://iconify.design
- Para el uso, visita https://iconify.design/docs/usage/
- Explora los iconos en https://icon-sets.iconify.design/cbi/

## Iconos disponibles

Para ver todos los iconos disponibles, puedes ir a la siguiente dirección. El visor de iconos también te permite generar un `custom-brand-icons.js` solo con los iconos que quieras, lo que te permite reducir el paquete de iconos y eliminar problemas de carga.

 -  [Buscador de iconos](https://carlos-uy.github.io/custom-brand-icons/)

# Métodos de instalación

#### HACS

Recomendamos instalar la tarjeta Custom brand icons mediante el [Home Assistant Community Store](https://hacs.xyz)
[![Abre tu instancia de Home Assistant y abre un repositorio dentro de Home Assistant Community Store.](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=Carlos-uy&repository=custom-brand-icons&category=frontend)

Después de instalarlo a través de HACS:
1. Agrega las siguientes líneas a tu `configuration.yaml`

    ```yaml
    frontend:
      extra_module_url:
        - /local/community/custom-brand-icons/custom-brand-icons.js
    ```

2. (Opcional) Usuarios en modo YAML. Agrega lo siguiente a tu configuración de Lovelace usando el editor Raw Config en Configurar UI o en `ui-lovelace.yaml`.

    ```yaml
    resources:
      - type: js
        url: /local/community/custom-brand-icons/custom-brand-icons.js
    ```

#### Instalación manual

Para agregar repositorios personalizados, sigue [esta guía](https://hacs.xyz/docs/faq/custom_repositories/). Establece la URL en `https://github.com/Carlos-uy/custom-brand-icons` y la categoría en `Lovelace`.

1. Descarga el archivo `custom-brand-icons.js` desde la [última versión](/releases/latest).
2. Copia el archivo `custom-brand-icons.js` en el directorio `<config>/www/`, donde se encuentra tu `configuration.yaml`.

3. Agrega lo siguiente a la sección `frontend` de tu `configuration.yaml`

    ```yaml
    frontend:
      extra_module_url:
        - /local/custom-brand-icons.js
    ```

4. (Opcional) Usuarios en modo YAML. Agrega lo siguiente a tu configuración de Lovelace usando el editor Raw Config en Configurar UI o en `ui-lovelace.yaml`.

    ```yaml
    resources:
      - type: js
        url: /local/custom-brand-icons.js
    ```

5. Reinicia Home Assistant.

---

# Manual de usuario

#### Custom brand icons usa el prefijo `phu:`
#### Agrega el nombre (del icono) después de `phu:`
- Ejemplo: `phu:eggs` <img src="/icon-svg/eggs.svg" title="Vista previa" alt="Vista previa" width="24"/>
- Ejemplo: `phu:chicken` <img src="/icon-svg/chicken.svg" title="Vista previa" alt="Vista previa" width="24"/>

Ejemplo de custom brand icons en una tarjeta de Lovelace:

```yaml
entities:
  - entity: light.lampada_entrance
    icon: 'phu:go'
    name: Go
  - entity: light.monitor_2_right
    icon: 'phu:play'
    name: play 1
  - entity: light.monitor_2_left
    icon: 'phu:play'
    name: play 2
show_header_toggle: false
title: Custom brand icons
type: entities
```

---

# ¿No ves el icono?

### Problema de caché en Home Assistant 2024.1.1

Algunos complementos (incluidos los oficiales) han tenido problemas de caché desde la versión 2024.1.1; aquí tienes algunas soluciones para probar.

1. Primero ve a Ajustes, panel y los 3 puntos, haz clic en recursos, agregar recurso

    ```yaml
    /hacsfiles/custom-brand-icons/custom-brand-icons.js?hacstag=366862031202420
    ```

2. Agrega también este segundo recurso
    ```yaml
    /local/community/custom-brand-icons/custom-brand-icons.js
    ```


#### Recarga completa (problema de caché del navegador)
- Recarga el navegador manteniendo presionado CTRL y pulsando F5.
- En Mac, mantén presionado ⌘ CMD y ⇧ SHIFT, y pulsa R.

#### Volver a descargar el componente
1. En la barra lateral izquierda, selecciona *HACS*.
2. Selecciona *Integraciones*.
3. En la barra superior (Integraciones, Frontend), selecciona *Frontend*.
4. Busca *custom-brand-icons* en la barra de búsqueda.
5. Selecciona *Custom brand icons*.
6. En la esquina superior derecha, selecciona los 3 puntos verticales que abren un menú desplegable.
7. Selecciona *Volver a descargar* (Redownload).
8. **Recarga por completo** el navegador.

#### Reinstalar el componente
1. Abre el menú desplegable desde el **Paso 6** de **Volver a descargar el componente**.
2. Selecciona *Eliminar* (Remove) y luego selecciona *Eliminar* de nuevo en la ventana emergente.
3. Esto debería devolverte a /hacs/frontend
4. En la esquina superior derecha, selecciona los 3 puntos verticales que abren un menú desplegable.
5. Selecciona *Repositorios personalizados* (Custom repositories).
6. Busca *Custom brand icons* y selecciónalo.
7. En la esquina inferior derecha, selecciona el icono azul grande de *Descargar*.
8. **Recarga por completo** el navegador.


#### Crear una versión más pequeña del paquete de iconos

1. Ve al [visor de iconos](https://carlos-uy.github.io/custom-brand-icons/)
2. Selecciona todos los iconos que quieras agregar a tu instancia de HA
3. Descarga el archivo JS e instálalo manualmente en Home Assistant

---

# Flujo de trabajo para desarrolladores

### Crea tu propio icono en `svg`

- Para crear un icono en formato SVG puedes usar diferentes programas, desde Illustrator, Inkscape o [Inkscape](https://inkscape.org/).
- Verifica que los iconos `svg` estén configurados correctamente usando el editor de texto que prefieras ([Notepad++](https://notepad-plus-plus.org/), Notepad o Visual Studio Code).
- Las reglas sobre el tamaño y las restricciones del icono se detallan en los puntos siguientes.
- El código `svg` debe contener **viewBox**. Sin transform, translate ni scale.
- Asegúrate de agregar el color: **#44739e**. Todos los iconos personalizados usan este color.
- Todos los iconos deben tener una nomenclatura que NO esté en camelCase, sino del tipo `part1name-part2name`.
- Cuando termines, agrega el archivo SVG en la carpeta `icon-svg` que se encuentra en la raíz del repositorio.

- el icono ***no debe estar compuesto por múltiples paths sino por uno solo***, como se muestra en el ejemplo de abajo

Ejemplo de archivo SVG:

```svg
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<!-- Created with Inkscape (http://www.inkscape.org/) -->
<!-- path d="..." es único para cada icono -->

<svg
   width="24"
   height="24"
   viewBox="0 0 24 24"
   version="1.1"
   xmlns="http://www.w3.org/2000/svg"
   xmlns:svg="http://www.w3.org/2000/svg">
   <path
     style="fill:#44739e"
     d="..."
    \>
  </svg>
```


### (opcional) Si quieres generar el paquete de iconos localmente

> [!WARNING]  
> Necesitas tener Node.js instalado para usar la generación automática.

Ve a la carpeta local donde se encuentra el archivo `custom-icons-builder.js` y ejecuta `node custom-icons-builder.cjs`. El script generará un nuevo archivo `custom-brand-icons` con los iconos actualizados.

Si todo salió bien verás un mensaje como este:

```js
✅ Build completed
📁 Generated file: dist/custom-brand-icons.js
🔢 Total icons: XXXX
```

(Opcional) Si quieres crear tu propio prefijo, puedes editar la última línea de `custom-brand-icons.js`

```js
window.customIconsets["yourprefix"] = getIcon;
```

### Script de normalización

> [!WARNING]  
> Necesitas tener Node.js instalado para usarlo.

> [!NOTE]  
> Este procedimiento se puede realizar localmente para verificar que los iconos cumplen los requisitos necesarios y que son compatibles y minimizados de la mejor manera posible.

Se ha introducido un script `normalize-icons.mjs` que realiza las siguientes operaciones:

- `viewBox="0 0 24 24"`
- geometría escalada para caber dentro de `MAX_GEO` x `MAX_GEO` (conservando la relación de aspecto), por defecto 20x20
- geometría centrada en `viewBox / 2`, por defecto 12,12
- solo se emiten paths, con coordenadas ya aplicadas, sin transforms
- el color de relleno se fija a BRAND_FILL, por defecto `#44739e`
- --clean: svgo --> normalize --> svgo (porque la normalización expande los datos de los paths)
- --vrt: ImageMagick montage ... --> script/vrt.png como "Prueba de regresión visual"
- entrada/salida por defecto (si no se especifica): custom-brand-icons/icon-svg


#### Instalación y uso:
* Ejecuta `npm i` en la carpeta `custom-brand-icons` para instalar los requisitos
* Ejecuta `npm run clean:vrt` para limpiar los iconos actuales (serán sobrescritos). También crea `vrt.png` en la carpeta `scripts` como "Prueba de regresión visual". Esto requiere tener ImageMagick instalado.


### Ejecución local usando Docker
Este repositorio contiene un archivo docker-compose que realiza las dos tareas anteriores:
1. Ejecuta el script `node custom-icons-builder.cjs` usando node 22 para generar los iconos personalizados.
2. Construye una imagen local de Docker con node 22 y ImageMagick y luego normaliza y limpia los archivos generados usando `npm run clean:vrt`.

Para realizar estas tareas, ejecuta uno de los siguientes comandos:
```sh
docker compose up build
docker compose up normalize --build
```


### Contribuciones y Pull Requests

> [!IMPORTANT]
> **Reglas de contribución:** Todos los Pull Requests deben apuntar a la rama `dev`.
> Los PRs abiertos contra `main` serán cerrados automáticamente.

Después de agregar tu icono SVG en la carpeta `icon-svg`, abre un pull request en la **[rama dev](https://github.com/Carlos-uy/custom-brand-icons/pulls)**. Debes crear una **nueva rama de funcionalidad** en tu fork (por ejemplo, `feat/add-new-icon`) y enviar tu PR desde ahí.
