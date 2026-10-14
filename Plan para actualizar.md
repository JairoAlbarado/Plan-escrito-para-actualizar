# Mi plan para solucionar las vulnerabilidades de Computer Wizard

## 1. Identificar las vulnerabilidades

Primero revisaría qué vulnerabilidades tiene Computer Wizard y qué dependencias están siendo afectadas. Para eso utilizaría `npm audit`, ya que me permite conocer los problemas de seguridad que se han detectado y las versiones afectadas.

## 2. Investigar las dependencias afectadas

Si encuentro una dependencia que no conozco o no sé qué paquete la está utilizando, usaría `npm explain` para investigar de dónde viene y si es una dependencia directa o transitiva.

De esta manera podría entender qué paquete está solicitando esa dependencia y qué otras dependencias podrían verse afectadas si se actualiza.

## 3. Buscar posibles soluciones

Después ejecutaría `npm audit fix --dry-run` para ver qué cambios me propone `npm` sin aplicarlos todavía.

Según los resultados, investigaría las versiones que propone y revisaría la documentación oficial para comprobar si realmente solucionan las vulnerabilidades y si son compatibles con las dependencias que tengo instaladas.

No actualizaría una dependencia solamente porque existe una versión más reciente, primero verificaría qué problema soluciona y qué cambios podría ocasionar.

## 4. Elegir qué versión actualizar

Dependiendo de lo que investigue, evaluaría si la vulnerabilidad se puede solucionar con una actualización *patch*, *minor* o *major*.

Si una versión *minor* corrige la vulnerabilidad y es compatible con el proyecto, intentaría priorizar esa opción antes de realizar una actualización *major* que pueda requerir cambios en el código.

Si la solución necesita una actualización *major*, investigaría qué cambios incompatibles introduce y qué tendría que modificar en el proyecto antes de decidir si conviene realizarla.

## 5. Aplicar los cambios y comprobar que funcione

Una vez que haya investigado las versiones y elegido una solución, realizaría los cambios correspondientes.

Después volvería a ejecutar `npm audit` para verificar si las vulnerabilidades se solucionaron. También ejecutaría `npm run build` para comprobar que el proyecto compile correctamente y probaría las funcionalidades importantes para verificar que sigan funcionando.

Si todavía quedan vulnerabilidades, volvería a investigar las dependencias afectadas y las posibles soluciones.

## 6. Documentar los resultados

Finalmente documentaría qué vulnerabilidades encontré, qué versiones investigué, qué cambios realicé y qué resultados obtuve.
Si alguna vulnerabilidad no se puede solucionar con una actualización compatible, investigaría las alternativas disponibles y documentaría el riesgo que queda pendiente y por qué tomé esa decisión.

Si alguna vulnerabilidad no se puede solucionar con una actualización compatible, investigaría las alternativas disponibles y documentaría el riesgo que queda pendiente y por qué tomé esa decisión, para poder revisarlo con Paul.
