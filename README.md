# animatecc-canvas-examples
Ejemplos de como usar acciones en Animate CC HTML5 Canvas

## Ejemplos

### Parar la linea the tiempo

Para parar la linea de tiempo en un determinado *frame* hay que poner:

```

this.stop();

```

### Reproducir un Movie Clip

#### Especificando el número del frame a reproducir

Para reproducir un **Movie Clip** (**MC**) espcificando el número del frame a reproducir se puede hacer con la siguiente instrucción:

```

this.nombre_de_la_instancia_del_mc.gotoAndPlay(1);

```

**En canvas los MC comienzan con el frame 0, por lo cual si un MC se quiere reproducir desde el segundo frame hay que especificar que se reproduzca desde el frame 1.**

#### Especificando un tag

Si se desea reproducir un **frame** especificando un **tag**, por ejemplo el **tag** _inicio_, se puede hacer de la siguiente forma:

```

this.nombre_de_la_instancia_del_mc.gotoAndPlay('inicio');

```

### Click

Si se le desea añadir a un **MC** el **event click** se puede hacer así:  

```

this.btn01.on('click', function(){
    
    // Poner las acciones aquí
    
}, this);

```

Si se tiene un **movie clip** (**mc**) en la linea de tiempo llamado _contenido_ con una etiqueta llamada _inicio_ se puede mandar llamar de la siguiente forma:

```

this.btn01.on('click', function(){
    
    this.contenido.gotoAndPlay('inicio');
    
}, this);

```

Si se tiene un **mc** llamado _titulo_ dentro del **mc** al que se le está poniendo la acción se puede mandar llamar de la siguiente forma:

```

this.btn01.on('click', function(){
    
    this.contenido.gotoAndPlay('inicio');
    
});

```

En este caso, hay que hacer notar que no se pasa como parametro *this* en la última linea del código.

Puedes descargar un archivo de ejemplo [aquí](./examples/ex_btns_click.fla).

### Modificar el cursor del ratón al pasar sobre un botón

Para hacer que al pasar el ratón sobre un **MC** el cursor cambie por la clásica "manita" se tiene que asignar el valor `pointer` a la propiedad `cursor` del **MC**:

```

this.btn01.cursor = 'pointer';

```

**Animate CC** no reconoce que se quiere trabajar con **Events** del ratón y no añade la instrucción `stage.enableMouseOver();` en el momento de la carga del archivo, una forma de forzar a que sí lo haga es poniento un clip del típo **button** fuera del **stage** como se muestra en este [ejemplo](./examples/ex_btns_click.fla).

Si no se quiere poner la instrucción mencionada arriba se puede convertir el **MC** en **Button**.

Tamién se puede modificar el archivo **html** generado por **Animate CC** añadiendo la línea `stage.enableMouseOver()` después de `
stage.addChild(exportRoot)` en la función `handleComplete()`.

### Hit Area

Al igual que con las antiguas versiones de Flash, se puede especificar el área donde se puede dar click dentro del **MC** creando un nuevo **MC** con nombre de instancia **hitArea**

### Roll over

Si se desea poner la funcionalidad de Roll Over a un **MC** se puede hacer con los **events** **mouseover** y **mouseout**:

```

this.btn01.on('mouseover', function(){

  this.titulo.gotoAndPlay('over');

});

this.btn01.on('mouseout', function(){

  this.titulo.gotoAndPlay('out');
  
});

```

En este ejemplo en el **mouseover** se manda a reproducir a el **tag** 'over' del **MC** _titulo_ que se encuentra adentro del **MC** _btn01_.

[Ejemplo](./examples/ex_btns_mouseover.fla)


