<!--
  <<< Notas del autor: Paso 4 >>>
  Comienza este paso reconociendo el paso anterior.
  Define los términos y enlaza a docs.github.com.
-->

## Paso 4: Agregar protecciones de rama

_¡Excelente trabajo subiendo informes de prueba! :partying_face:_

Echa un vistazo al cuadro de fusión, notarás que puedes fusionar esto incluso si el proceso de revisión no se ha cumplido.

Las ramas protegidas aseguran que los colaboradores en tu repositorio no puedan realizar cambios irrevocables en las ramas. Habilitar ramas protegidas también te permite habilitar otros controles y requisitos opcionales, como revisiones requeridas y verificaciones de estado requeridas.

### :keyboard: Actividad: Agregar protecciones de rama

1. Ve a la configuración de **Ramas**. Puedes navegar a esa página manualmente seleccionando la pestaña más a la derecha en la parte superior del repositorio llamada **Configuración** y luego haciendo clic en **Ramas**.
1. Haz clic en **Agregar regla de protección de rama** bajo "Reglas de protección de rama".
1. Escribe `stemdo` en **Patrón de nombre de la rama**.
1. Marca la casilla **Require a pull request before merging**.
1. Desmarca la casilla **Require approvals**.
1. Marca la casilla **Require status checks to pass before merging**.
1. Marca todas las compilaciones y pruebas que te gustaría ver en el nuevo cuadro gris que se mostrará.
1. Haz clic en **Crear**.
1. _Una vez que activas la protección de rama, las Acciones ya no pueden enviar directamente a la rama `stemdo`. Espera unos 20 segundos y luego ve a la rama `ci`. [GitHub Actions](https://docs.github.com/actions) se actualizará automáticamente al siguiente paso en la rama `ci`. Deberás seguir las instrucciones en esta rama._
