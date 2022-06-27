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

## Prerequisites
You will need [Node.js](https://nodejs.org) version 6.0 or greater installed on your system.

## Setup

Obtenga el código clonando este repositorio mediante git

    > git clone https://github.com/josefaherreras/criptomoneda-febos.git
... o [descargando el código fuente](https://github.com/josefaherreras/criptomoneda-febos/archive/refs/heads/main.zip) como un archivo zip.

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