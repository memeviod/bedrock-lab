```{=html}
<p align="center">
```
`<img src="https://raw.githubusercontent.com/memeviod/bedrock-lab/main/brand.webp" alt="Bedrock Lab" width="520">`{=html}
```{=html}
</p>
```
```{=html}
<h1 align="center">
```
Bedrock Lab
```{=html}
</h1>
```
```{=html}
<p align="center">
```
Descubre contenido para Minecraft Bedrock desde un solo lugar.
```{=html}
</p>
```
```{=html}
<p align="center">
```
`<a href="https://bedrock-lab-memeviod.onrender.com/">`{=html}Sitio
web`</a>`{=html} ·
`<a href="https://github.com/memeviod/bedrock-lab/releases">`{=html}Descargas`</a>`{=html}
·
`<a href="https://github.com/memeviod/bedrock-lab/issues">`{=html}Reportar
un problema`</a>`{=html}
```{=html}
</p>
```

------------------------------------------------------------------------

## Acerca del proyecto

**Bedrock Lab** es un catálogo multiplataforma creado para facilitar el
descubrimiento de contenido de **Minecraft Bedrock**. Reúne
publicaciones de distintas plataformas y permite explorarlas desde una
interfaz centralizada, con herramientas para buscar, filtrar, consultar
detalles y acceder a las fuentes originales.

El proyecto cuenta con una **versión web** y una **aplicación para
Android**.

## Características

-   **Catálogo unificado:** explora contenido procedente de distintas
    plataformas.
-   **Búsqueda y filtros:** encuentra publicaciones por nombre,
    categoría, fuente y versión.
-   **Categorías:** addons, texturas, mapas y skins.
-   **Fichas de contenido:** consulta descripciones, imágenes y datos
    disponibles de cada publicación.
-   **Favoritos y recientes:** conserva elementos en el almacenamiento
    local del dispositivo.
-   **Compartir y copiar enlaces:** vuelve fácilmente a las
    publicaciones originales.
-   **Traducción de descripciones:** solicita una traducción automática
    cuando está disponible.
-   **Herramientas complementarias:** acceso a un conversor externo y a
    una guía de instalación.
-   **Diseño adaptable:** interfaz preparada para móviles y pantallas de
    escritorio.

## Fuentes integradas

Bedrock Lab consulta contenido de las siguientes plataformas:

  ------------------------------------------------------------------------------------------------
  Plataforma                                                   Integración
  ------------------------------------------------------------ -----------------------------------
  [CurseForge](https://www.curseforge.com/minecraft-bedrock)   Consulta mediante API y acceso a
                                                               archivos elegibles.

  [MCPEDL](https://mcpedl.com/)                                Búsqueda y consulta de
                                                               publicaciones.

  [ModBay](https://modbay.org/)                                Consulta de publicaciones
                                                               disponibles.

  [McPack.cc](https://www.mcpack.cc/)                          Consulta del catálogo y acceso a
                                                               publicaciones.
  ------------------------------------------------------------------------------------------------

La disponibilidad y los datos mostrados dependen de cada plataforma. Si
una fuente presenta errores o no responde, los resultados de las demás
fuentes pueden seguir estando disponibles.

## Plataformas

### Web

La versión web permite explorar el catálogo desde un navegador:

**https://bedrock-lab-memeviod.onrender.com/**

### Android

Las versiones disponibles de la aplicación se publican en la sección de
Releases:

**[Consultar versiones de Bedrock
Lab](https://github.com/memeviod/bedrock-lab/releases)**

Las compilaciones de prueba y las versiones publicadas pueden tener
procesos de distribución diferentes. Consulta las notas de cada versión
para conocer sus cambios y requisitos.

## Tecnología

  Tecnología       Uso
  ---------------- -------------------------------------------------------------
  HTML             Estructura de la interfaz web.
  CSS              Diseño visual y adaptación a distintos tamaños de pantalla.
  JavaScript       Interacciones, búsqueda y funcionamiento del catálogo.
  Node.js          Servidor y comunicación con las fuentes externas.
  CurseForge API   Consulta de datos de CurseForge.
  GitHub Actions   Automatización de tareas de compilación.
  Render           Alojamiento de la versión web.

### Estructura principal

  -----------------------------------------------------------------------
  Archivo                             Función
  ----------------------------------- -----------------------------------
  `index.html`                        Interfaz web y lógica del cliente.

  `server.js`                         Servidor, rutas API e integraciones
                                      externas.

  `package.json`                      Dependencias, configuración y
                                      comandos del proyecto.

  `manifest.json`                     Metadatos de la aplicación web.

  `.github/workflows/`                Automatizaciones de GitHub Actions.
  -----------------------------------------------------------------------

## Instalación local

### Requisitos

-   Node.js 18 o superior.
-   Git.
-   Una clave de API de CurseForge para habilitar las consultas que la
    requieren.

### 1. Clonar el repositorio

``` bash
git clone https://github.com/memeviod/bedrock-lab.git
cd bedrock-lab
```

### 2. Configurar la clave de CurseForge

Configura la variable de entorno `CURSEFORGE_API_KEY`.

**Linux / macOS**

``` bash
export CURSEFORGE_API_KEY="TU_API_KEY"
```

**Windows PowerShell**

``` powershell
$env:CURSEFORGE_API_KEY="TU_API_KEY"
```

No incluyas claves privadas directamente en el código ni las publiques
en el repositorio.

### 3. Instalar dependencias e iniciar

``` bash
npm install
npm start
```

El servidor utiliza la variable `PORT` cuando está definida; de lo
contrario, emplea el puerto configurado por el proyecto.

## API del servidor

  -----------------------------------------------------------------------
  Método                  Ruta                    Descripción
  ----------------------- ----------------------- -----------------------
  `GET`                   `/api/search`           Busca contenido en las
                                                  fuentes disponibles.

  `GET`                   `/api/details`          Consulta información
                                                  ampliada de una
                                                  publicación.

  `GET`                   `/api/download`         Gestiona descargas
                                                  elegibles de CurseForge
                                                  o redirige a la
                                                  publicación original.

  `GET`                   `/manifest.json`        Entrega los metadatos
                                                  de la aplicación web.
  -----------------------------------------------------------------------

Los parámetros aceptados y el comportamiento de cada ruta están
definidos en `server.js`.

## Rendimiento y manejo de solicitudes

El proyecto incorpora mecanismos para gestionar las consultas y evitar
trabajo innecesario, entre ellos:

-   Consultas a varias fuentes de forma concurrente.
-   Caché temporal para determinadas respuestas.
-   Límites de tamaño y concurrencia en las solicitudes.
-   Tiempos máximos para conexiones externas.
-   Gestión de solicitudes que dejan de ser necesarias.
-   Carga diferida de imágenes y búsqueda con espera breve antes de
    consultar.

Estas medidas ayudan a controlar el funcionamiento del servicio. El
consumo real de recursos depende del tráfico, las respuestas de las
plataformas externas y la infraestructura de alojamiento.

## Contenido y atribución

Bedrock Lab es un proyecto de descubrimiento y organización de
contenido. Los addons, mapas, texturas, skins, imágenes y demás
publicaciones pertenecen a sus respectivos autores y titulares.

Bedrock Lab no reclama la propiedad de esos recursos. Para consultar
permisos, requisitos, compatibilidad, créditos o descargar una
publicación, visita siempre su **fuente original**.

La disponibilidad de enlaces y archivos puede cambiar según las
decisiones de cada plataforma o creador.

## Reportar problemas

¿Encontraste un error o tienes una sugerencia?

Abre un reporte en **[GitHub
Issues](https://github.com/memeviod/bedrock-lab/issues)** e incluye,
cuando sea posible:

-   Una descripción clara del problema.
-   Los pasos para reproducirlo.
-   La fuente o sección afectada.
-   La versión del navegador o de la aplicación.

No incluyas claves API, contraseñas, tokens ni información privada en
los reportes.

## Créditos

**Dirección del proyecto:** MEMEVIOD

**Desarrollo:** reconocimiento especial a **Zapia**, cuya contribución
representa más del 80 % del trabajo de desarrollo de Bedrock Lab.

Gracias también a los creadores de contenido y a las plataformas que
forman parte del ecosistema de Minecraft Bedrock.

------------------------------------------------------------------------

```{=html}
<p align="center">
```
`<strong>`{=html}Bedrock Lab`</strong>`{=html}`<br>`{=html} Hecho para
explorar el universo de Minecraft Bedrock.
```{=html}
</p>
```
