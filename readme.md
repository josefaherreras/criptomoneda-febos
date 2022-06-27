<p align="center">
    <a href="https://vuejs.org" target="_blank" rel="noopener noreferrer"><img width="100" src="https://vuejs.org/images/logo.png" alt="Vue logo"></a>
    
    
</p>

<p align="center">
  <a href="https://getbootstrap.com/">
    <img src="https://getbootstrap.com/docs/5.2/assets/brand/bootstrap-logo-shadow.png" alt="Bootstrap logo" width="200" height="165">
  </a>
</p>



<p align="center">
  <a href="https://www.npmjs.com/package/vue"><img src="https://img.shields.io/npm/v/vue.svg?sanitize=true" alt="Version"></a>
  <a href="https://www.npmjs.com/package/vue"><img src="https://img.shields.io/npm/l/vue.svg?sanitize=true" alt="License"></a>
</p>

Vue.js + Bootstrap 5 - frontend
=== 
## Prueba técnica FEBOS - Desarrollo Front-end
La prueba técnica consiste en construir una aplicación web muy sencilla utilizando vue 2.x que sea capaz de lo siguiente:

- Mostrar información desde Wazirx exchange a nivel de cabezera y detalle.
- Todas las decisiones sobre layout, arquitectura e implementaciones es del postulante.
  (Las secciones no necesariamente estan separadas, aplicar lo que se desee para que sea amigable y visualmente atractivo)
 
Tendremos basicamente dos funcionalidades, una es mostrar de alguna forma el listado de mercados, y la otra es mostrar un mercado individual (misma pagina, tab, grilla y popup, como creas conveniente y amigable)

#### Funcionalidad 1: Wazirx Resumen/Listado

- Mostrar el listado "market summary" que es retornado en JSON desde la siguiente [API](https://api.wazirx.com/sapi/v1/tickers/24hr)
  (Market Summaries 24hrs API)

#### Funcionalidad 2: Mostrar datos individuales(market data)

- Dejar al usuario seleccionar un mercado desde Wazirxt el cual mostrara información del mercado individual seleccionado [Rest CALL ejemplo](https://api.wazirx.com/sapi/v1/ticker/24hr?symbol=btcinr)

Permite que el usuario pueda ver tantos markets como quiera en una pagina.


## Prerequisitos
Tu necesitas tener [Node.js](https://nodejs.org) version 6.0 o mayor instalado en su sistema.

## Setup

Obtenga el código clonando este repositorio mediante git

    > git clone https://github.com/josefaherreras/criptomoneda-febos.git
... o [descargando el código fuente](https://github.com/josefaherreras/criptomoneda-febos/archive/refs/heads/master.zip) como un archivo zip.


Una vez descargado, abra el terminal en el directorio del proyecto, y continúe con:

```
npm install
```

### Compilación y hot-reloads para desarrollo
```
npm run serve
```

### Consideraciones Importantes

¡También necesita habilitar `localhost:8080` en su configuración de CORS Origins! Ya sea a través de [management page](https://manage.sanity.io/) en `settings` o ejecutando esto en la carpeta del proyecto que configuraste con `sanity init`:

  > sanity cors add http://localhost:8080
Para una explicación más detallada de cómo funciona este ejemplo, consulte la [guia](http://vuejs-templates.github.io/webpack/) y  [documentación para vue-loader](http://vuejs.github.io/vue-loader).