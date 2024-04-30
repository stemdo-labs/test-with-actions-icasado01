<header>

<!--
  <<< Notas del autor: Encabezado del curso >>>
  Incluye una imagen de 1280×640, el título del curso en minúsculas con descripción concisa en énfasis.
  En la configuración de tu repositorio: habilita el repositorio de plantillas, agrega tu imagen social de 1280×640, elimina automáticamente las ramas principales.
  Agrega tu licencia de código abierto, GitHub utiliza la licencia MIT.
-->

# Prueba con Actions

_Crea flujos de trabajo que te permitan utilizar Integración Continua (CI) para tus proyectos._

</header>

<!--
  Elige 3-5 pasos para tu curso.
  ¡El primer paso siempre es el más difícil, así que elige algo fácil!
  Enlaza a docs.github.com para explicaciones adicionales.
  ¡Anima a los usuarios a abrir nuevas pestañas para los pasos!
-->

## paso 1: Agregar un workflow de prueba

_Bienvenido a "GitHub Actions: Integración Continua"! :wave:_

**¿Qué es la _integración continua_?**: [La integración continua](https://es.wikipedia.org/wiki/Integración_continua) puede ayudarte a mantener los estándares de calidad de tu equipo ejecutando pruebas e informando los resultados en GitHub. Las herramientas de CI ejecutan compilaciones y pruebas, desencadenadas por commits. Los resultados de calidad se envían de vuelta a GitHub en la pull request. El objetivo es tener menos problemas en `stemdo` y obtener una retroalimentación más rápida mientras trabajas.

![Una ilustración con una mitad izquierda y una mitad derecha. En la izquierda: ilustración de cómo están encapsulados los términos de GitHub Actions. En el nivel más alto: flujos de trabajo y disparadores de eventos. Dentro de los flujos de trabajo: trabajos y definición del entorno de compilación. Dentro de los trabajos: pasos. Dentro de los pasos: una llamada a una action. En la derecha: la secuencia evaluada: workflow, trabajo, paso, action.](https://user-images.githubusercontent.com/6351798/88589835-f5ce0900-d016-11ea-8c8a-0e7d7907c713.png)


- **workflow**: Un workflow es una unidad de automatización desde su inicio hasta su finalización, incluyendo la definición de lo que desencadena la automatización, qué entorno u otros aspectos deben tenerse en cuenta durante la automatización y qué debe suceder como resultado del desencadenante.
- **Job**: Un Job es una sección del workflow y está compuesto por uno o más pasos. En esta sección de nuestro workflow, la plantilla define los pasos que componen el trabajo de `build`.
- **Step**: Un paso representa un _efecto_ de la automatización. Un paso podría definirse como una Action de GitHub u otra unidad, como imprimir algo en la consola.
- **Action**: Una action es una pieza de automatización escrita de manera compatible con los flujos de trabajo. Las acciones pueden ser escritas por GitHub, por la comunidad de código abierto, ¡o tú mismo puedes escribirlas!


Para obtener más información, consulta [Sintaxis de flujo de trabajo para GitHub Actions](https://docs.github.com/actions/using-workflows/workflow-syntax-for-github-actions) en los documentos de GitHub.

Primero, agreguemos un flujo de trabajo para _lint_ (limpiar, como un rodillo de pelusa) nuestros archivos Markdown en este repositorio.


### :keyboard: Actividad: Agregar un flujo de trabajo de prueba

1. Abre una nueva pestaña del navegador y trabaja a través de los siguientes pasos en esa pestaña mientras lees las instrucciones en esta pestaña.
1. Ve a la **pestaña Actions**.
1. Haz clic en **Nuevo workflow**.
1. Busca "Simple workflow" y haz clic en **Configurar**.
1. Nombre de tu flujo de trabajo `ci.yml`.
1. Actualiza el flujo de trabajo eliminando los dos últimos pasos.
1. Agrega el siguiente paso al final de tu flujo de trabajo:


   ```yml
   - name: Run markdown lint
     run: |
       npm install remark-cli remark-preset-lint-consistent
       npx remark . --use remark-preset-lint-consistent --frail
   ```

    > Incluso después de que el código esté indentado correctamente en `ci.yml`, verás un error de compilación en GitHub Actions. Lo solucionaremos en el siguiente paso.


1. Haz clic en **Commit changes...**, y elige crear una nueva rama llamada `ci`.
1. Haz clic en **Propose changes**.
1. Haz clic en **Crear pull request**.
1. Espera unos 20 segundos y luego actualiza esta página (la que estás siguiendo instrucciones). [GitHub Actions](https://docs.github.com/actions) se actualizará automáticamente al siguiente paso.

<footer>

<!--
  <<< Notas del autor: Pie de página >>>
  Agrega un enlace para obtener soporte, página de estado de GitHub, código de conducta, enlace de licencia.
-->

---

Obtén ayuda: [Publica en nuestro foro de discusión](https://github.com/orgs/skills/discussions/categories/test-with-actions) &bull; [Revisa la página de estado de GitHub](https://www.githubstatus.com/)

&copy; 2023 GitHub &bull; [Código de Conducta](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [Licencia MIT](https://gh.io/mit)

</footer>
