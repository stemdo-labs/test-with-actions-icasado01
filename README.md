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
  <<< Notas del autor: Paso 3 >>>
  Comienza este paso reconociendo el paso anterior.
  Define los términos y enlaza a docs.github.com.
-->

## Paso 3: Subir informes de prueba

_¡El workflow ha terminado de ejecutarse! :sparkles:_

Entonces, ¿qué hacemos cuando necesitamos el producto del trabajo de un trabajo en otro? Podemos usar el almacenamiento de [artefactos integrado](https://docs.github.com/actions/advanced-guides/storing-workflow-data-as-artifacts) para guardar artefactos creados de un trabajo para ser utilizados en otro trabajo dentro del mismo workflow.

Para cargar artefactos en el almacenamiento de artefactos, podemos usar una acción construida por GitHub: [`actions/upload-artifacts`](https://github.com/actions/upload-artifact).

### :keyboard: Actividad: Subir informes de prueba

1. Edita tu archivo de workflow.
1. Actualiza el paso `Run markdown lint` en tu trabajo de `build` para usar `vfile-reporter-json` y generar los resultados en `remark-lint-report.json`.
1. Agrega un paso a tu trabajo de `build` que utilice la acción `upload-artifact`. Este paso debería subir el archivo `remark-lint-report.json` generado por el paso `Run markdown lint` actualizado.
1. Tu nuevo trabajo de `build` debería lucir así:

   ```yml
   build:
     runs-on: ubuntu-latest
     steps:
       - uses: actions/checkout@v4

       - name: Run markdown lint
         run: |
           npm install remark-cli remark-preset-lint-consistent vfile-reporter-json
           npx remark . --use remark-preset-lint-consistent --report vfile-reporter-json 2> remark-lint-report.json

       - uses: actions/upload-artifact@v3
         with:
           name: remark-lint-report
           path: remark-lint-report.json
   ```

1. Confirma tu cambio en esta rama.
1. Espera unos 20 segundos y luego actualiza esta página (la que estás siguiendo instrucciones). [GitHub Actions](https://docs.github.com/actions) se actualizará automáticamente al siguiente paso.

Al igual que la acción de carga para enviar artefactos al almacenamiento, puedes usar la acción de descarga para descargar estos artefactos previamente subidos desde el trabajo de `build`: [`actions/download-artifact`](https://github.com/actions/download-artifact). Por brevedad, omitiremos ese paso para este curso.

<footer>

<!--
  <<< Notas del autor: Pie de página >>>
  Agrega un enlace para obtener soporte, página de estado de GitHub, código de conducta, enlace de licencia.
-->

---

Obtén ayuda: [Publica en nuestro foro de discusión](https://github.com/orgs/skills/discussions/categories/test-with-actions) &bull; [Revisa la página de estado de GitHub](https://www.githubstatus.com/)

&copy; 2023 GitHub &bull; [Código de Conducta](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [Licencia MIT](https://gh.io/mit)

</footer>
