# Archivo JADE de ejemplo

### IMPORTA LOS TIPO DE DATOS 


jade::{}[conf/types.jade](conf/types.jade){{}}

### LAS CONFIGURACIONES DE LOS WORKSPACES
```jade
setting::{}[]{{
common.out=c:/common/out/
ts.out=c:/ts/out/
}}
```
### IMPORTAR CADA UNO DE LOS TEMPLATES 
```jade
jade::{}[templates/template.php.class.jade]{{}}
jade::{}[templates/template.php.controller.jade]{{}}
jade::{}[templates/template.html.form.jade]{{}}
```

### SEQUENCIA DE MANUFACTURA
```jade
sequence::{php}[TS_CLASS]{{
class.tpl php tsoft/model/{classname}.php
controller.tpl php tsoft/controller/{classname}Controller.php
form.tpl html tsoft/layout/_{classname}.html
}}
```

### ESCUCHA DE CAMBIOS 
```jade
listener::{common}[LS_ANYCHANGE]{{
TS_CLASS php *,!Factory
}}
```

### OTRA SEQUENCIA DE MANUFACTURA
```jade
sequence::{c#}[TS_CLASS_2xxxx]{{
class.tpl c# tsoft/model/{classname}.cs
}}
```
### OTRA ESCUCHA
```jade
listener::{common}[LS_ANYCHANGE_2]{{
TS_CLASS_2 c# *,!Factory
}}
```

### DEFINICION DE PLURALES DE MODELOS
```jade
name::{}[]{{
Persona=Personas
Key=Keys
Mouse=Mice
}}
```


### MODELO DE NEGOCIO SI NO SE ESPECIFICA UN WORKSPACES

```jade
model::{}[]{{


Articulo:c
Articulo:*#
Nombre:ts
SKU:s
Linea:auto
UsuarioAlta:i
FechaAlta:d
UsuarioMod:i
FechaMod:d

Colonia:c
Colonia:*#
Nombre:ts
Ciudad:auto
UsuarioAlta:i
FechaAlta:d
UsuarioMod:i
FechaMod:d

Casa:c
Casa:*#
Nombre:ts

Linea:c
Linea:*#
Nombre:ts


Estado:c
Estado:*#
Nombre:ts
Pais:auto
UsuarioAlta:i
FechaAlta:d
UsuarioMod:i
FechaMod:d 

Pais:c
Pais:*#
Nombre:ts
UsuarioAlta:i
FechaAlta:d
UsuarioMod:i
FechaMod:d
Estados:*Estado?Pais:i

Usuario:c
Usuario:*#
Nombre:ts{Nombre de Usuario}
NombreCompleto:s{Nombre Completo}
Descripcion:s
Password:s{ContraseÃ±a}
Email:s{Correo}
Ciudad:auto
TipoUsuario:auto
Activo:0
UsuarioAlta:i
FechaAlta:d
UsuarioMod:i
FechaMod:d


}}
```

### un template embebido
```jade
tt::{}[sql.class.tpl]{{

CREATE TABLE {classname.plural.lower}(
tt::{with(anyproperty)join(,)}[bassaa.tpl]{{
   {propertyname} {type}
}}
)

}}
```
```jade
### SEQUENCIA DE MANUFACTURA
sequence::{sql}[TS_SQL]{{
class.tpl sql tsoft/sql/{classname}.sql

}}
### ESCUCHA DE CAMBIOS 
listener::{common}[LS_ANYCHANGE2]{{
TS_SQL sql *,!Factory
}}

```











