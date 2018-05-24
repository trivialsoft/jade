## ARCHIVO EJEMPLO JADE
## *Copyright(c) Antonio Ramírez Santander(@AntonioRamsan).*
## *Copyright(c) TrivialSoft.*
### CONFIGURACIONES - CONFIGURATIONS
```jade
setting::{}[]{{
common.out=c:/common/out/
}}
```
### DEFINICIÓN DE TIPOS - DEFINITION OF DATA TYPE 
```jade
type::{}[]{{
ESP:*i =Long
ESP:i =Long
ESP:*# =Long
ESP:ts =String
ESP:d =Date
}}```
### SEQUENCIA DE MANUFACTURA - SEQUENCE OF MANUFACTURING
```jade
sequence::{esp}[TS_CLASS]{{
class.tpl esp tsoft/esp/{classname}.txt
}}
```
### ESCUCHA DE CAMBIOS  - LISTENER
```jade
listener::{common}[LS_ANYCHANGE]{{
TS_CLASS esp *,!Factory
}}
```

### TEMPLATES 
```jade
tt::{}[esp.class.tpl]{{

   > La clase {classname}
   > Tiene las siguientes propiedades:
   
   tt::{with(anyproperty)}[props.tpl]{{
   > {propertyname} de tipo {type} }}
   tt::{...}[po.props.tpl]{{
   > {propertyname} de tipo {type}  OBJETO }} 
   
}}
```
### MODELOS - DOMAIN MODELS

```jade
model::{}[]{{



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
Continente:auto
UsuarioAlta:i
FechaAlta:d
UsuarioMod:i
FechaMod:d

}}
```
