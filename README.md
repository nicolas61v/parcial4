# Generador de Códigos QR
### Por Juan Nicolas Vasquez Ocampo - Universidad EAFIT

Profe, aqui esta mi implementacion del generador de codigos QR. Me base en el video que nos dejo y en algunas investigaciones adicionales que hice sobertodo con Stackoverflow. La idea era crear algo sin usar librerias externas, asi que tuve que tome como base el ejemplo que dejo.

## Como funciona

El codigo esta dividido en varias partes principales que hacen diferentes trabajos:

1. **Conversion de texto a binario**: 
   - Primero agarra el texto que le metes y lo convierte a numeros usando un diccionario que arme
   - Despues lo pasa a binario siguiendo las reglas del modo alfanumerico que investigué
   - Le meti algunos bits extra al principio para indicar que es modo alfanumerico y cuanto mide el texto

2. **Armado de la matriz**:
   - Cree una matriz de 21x21 que es el tamaño basico de un QR
   - Le puse los patrones de posicion que son esos cuadrados que van en las esquinas
   - Tambien meti los patrones de timing que son las lineas que ayudan a que el lector se ubique
   - Le agregue el patron de alineamiento en el centro que ayuda a que no se deforme

3. **Manejo de datos y mascara**:
   - Los datos binarios los voy metiendo en zigzag de abajo hacia arriba
   - Le puse una mascara simple que va alternando bits para que no queden muchos modulos del mismo color juntos
   - Al final relleno los espacios que sobran

Profe, se que el sistema de correccion de errores podria ser mas elaborado, pero implemente una version simple que cumple con lo basico que necesitamos. La idea era mostrar que se como funciona la estructura fundamental de un QR y ademas eso casi no me da.

## Como usarlo

Es bastante simple:
1. Ejecutas el codigo
2. Te pide que metas un texto (como "HELLO123")
3. Te muestra la matriz del QR usando B para blanco y N para negro

## Por que lo hice asi

La verdad profe, pense en hacerlo mas complejo con mas patrones de mascara y un sistema de correccion de errores mas avanzado, pero me parecio que esto demostraba bien lo que se pedia:
- Como se estructura un QR
- Como se codifican los datos
- Como funcionan los patrones de posicion y alineamiento
- Como se aplican las mascaras

No use librerias externas como lo decia y todo esta hecho con python en vanilla. Cada parte esta comentada para que se pueda ver el proceso de pensamiento.

## Limitaciones

Para ser honesto hay algunas cosas que se podrian mejorar:
- El sistema de correccion de errores es bastante basico
- Solo tiene un patron de mascara
- No maneja caracteres especiales

## Modo de uso

profe lo puede correr directamente en colab por ello acá le dejo el link donde esta explicado y donde lo puede correr
LINK --> https://colab.research.google.com/drive/1JghSmfSf4Qtnl4aIKQrtiXj8oKrylhfR?usp=sharing

sino tambien esta la parte del mero codigo limpio lo copia y lo pega donde quiera.

## NOTA
Por otro lado profe, muchas gracias por las clases, la verdad nunca habia ido tanto a clases, y la verdad es porque usted hace que sean mas entretenidas y den ganas de seguir yendo, agradezco mucho lo que nos enseño y gracias por los repositorio porque los voy a estar mirando mucho, espero profe verlo por ahi en la U y muchas gracias de nuevo, es usted muy amable y me gusto mucho el curso. Dios lo bendiga.

Pero considero que cumple con los requisitos del trabajo y demuestra que entiendo los conceptos principales de como funcionan los codigos QR.

Si necesita que mejore algo o tiene sugerencias, me avisa!
