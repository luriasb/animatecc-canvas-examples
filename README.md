# animatecc-canvas-examples
Ejemplos de como usar acciones en Animate CC HTML5 Canvas

## Ejemplos

### Parar la linea the tiempo

Para parar la linea de tiempo en un determinado *frame* hay que poner:

```

this.stop();

```

### Reproducir un Movie Clip

### Especificando el número del frame a reproducir

Para reproducir un *Movie Clip* (*MC*) espcificando el número del frame a reproducir se puede hacer con la siguiente instrucción:

```

this.nombre_de_la_instancia_del_mc.gotoAndPlay(1);

```

*En canvas los MC comienzan con el frame 0, por lo cual si un MC se quiere reproducir desde el segundo frame hay que especificar que se reproduzca desde el frame 1.*

### Especificando un tah

Si se desea reproducir un *frame* especificando un *tag*, por ejemplo el *tag* _inicio_ se puede hacer de la siguiente forma:

```

this.nombre_de_la_instancia_del_mc.gotoAndPlay('inicio');

```

### Click

Si se le desea añadir a un *MC* el *event click* se puede hacer así:  

```

this.btn01.on('click', function(){
    
    // Poner las acciones aquí
    
}, this);

```

Si se tiene un *movie clip* (*mc*) en la linea de tiempo llamado _contenido_ con una etiqueta llamada _inicio_ se puede mandar llamar de la siguiente forma:

```

this.btn01.on('click', function(){
    
    this.contenido.gotoAndPlay('inicio');
    
}, this);

```

Si se tiene un *mc* llamado _titulo_ dentro del *mc* al que se le está poniendo la acción se puede mandar llamar de la siguiente forma:

```

this.btn01.on('click', function(){
    
    this.contenido.gotoAndPlay('inicio');
    
});

```

En este caso, hay que hacer notar que no se pasa como parametro *this* en la última linea del código

### Roll over

