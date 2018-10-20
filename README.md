# El Proyecto JADE
## (Just Another Development Engine)
> Por Antonio Ramírez Santander

> JADE es un motor para la automatización de la generación de código fuente mediante el uso
> de modelos de negocio (classes) definidos en un metalenguaje llamedo ML (Modeling Language) y 
> mediante el uso de un lenguaje de plantillas T4U (Time For You).
> Este motor leer archivos de texto plano y reconoce los siguientes tipo de elementos
> identificados en una instruccion bloque. Los elementos son los siguientes: 

## Instruccion Bloque 
> Es la instrucción que permite indentificar los distintos elementos de un archivo jade
```jade

JADE_ITEM_NAME::{}[]{{
## Aqui va la definicion
}}

```
> Los Jade Items pueden ser los siguintres:

|Item|Descripción|
|----|----|
| jade| Otro archivo jade |
|setting| Configuración local para las salida de los archivos fuentes|
|sequence| Secuencia de manufactura de código |
|listener| Escucha cambios |
|model| Modelo de Negocio |
|tt| Template |
|type| Mapeo de tipos de datos |
|name| Mapeo entre un Modelo y el nombre de una Coleccion |
|ui| Texto para una interfaz de usuario|
|key| Texto Fijo que depende del tipo|
|group|Grupo de propiedades|


## Los Workspaces 

> Son espacios de trabajo, proyectos o contenedores que agrupan cierto tipo de clases de negocio. 
>

## Usuarios

> Es la informacion del developer

## Los Archivos JADE

 Son archivos de texto que incluyen, modelos, templates, configuraciones, tipos, etc. usualmente 
 usan lenguaje MARKDOWN para poder presentarse como autodocumentacion.

## Las Configuraciones


Son la configuraciones generales de cada WOKSPACE

## Las Secuencias

Son la instrucciones para la generacion de archivos de codigo

## Los Listeners

Son el alcance de la manufactura en los modelos

## Los modelos

Son las clases de negocio expresados en lenguaje ML 

## Las Plantillas

Son texto plano con instrucciones PQL para la seleccion de propiedades en los modelos
 
## Los Tipos de Datos

Son la equivalencia de los tipos base del lenguaje ML en el lenguaje de programacion final.
 
## Los Nombres

Son los nombres en plural de las colecciones de modelos.  

## Los Nombres de ui

Son los nombres de las propiedades de un modelo, en una interfaz de usuario.

## Las Keys

Son texto fijo en los templates...

## Los Grupos de propiedades 

Son las agrupaciones de propiedades de modelos

## Los Recursos 


## Los Partners

Son los demas developer en los que se puede confiar como recurso adicionales(jades remotos)

## Las Precedencias

Existe una precedencia en la seleccion de los elementos...

## Los Cambios

Los cambios en los modelos disparan la generacion de codigo.

## La Publicacion

## Los Guardas de datos

Ciertos datos sensibles...