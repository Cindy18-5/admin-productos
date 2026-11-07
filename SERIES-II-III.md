# Series II y III - Cindy18-5

Destino previsto: https://github.com/Cindy18-5/admin-productos

Esta copia contiene las tres pruebas de la Serie II y el workflow de Cypress del curso. La publicacion y la evidencia de la Serie III estan pendientes de acceso autorizado al fork de Cindy18-5. Las ejecuciones y el PR de otra cuenta no son evidencia de este repositorio.

## Serie II

Desde la carpeta de este proyecto, instalar las dependencias una vez:

```powershell
npm.cmd install
npm.cmd start
```

Si otro proyecto usa el puerto 3000, detener ese servidor antes o usar un puerto distinto y ajustar baseUrl en Cypress.

En otra terminal:

```powershell
npx.cmd cypress open
```

Seleccionar E2E Testing y `serie-ii.cy.js`. Las tres pruebas verifican el panel despues del login, un producto nuevo en la tabla y el rechazo del precio cero. Antes de cada prueba se limpia localStorage y se esperan los cinco productos iniciales.

## Serie III: ejecutar en el fork propio

1. Crear el fork del repositorio del curso en Cindy18-5 y habilitar Actions. Configurar la identidad real de quien realiza los commits; no atribuir commits a otra persona.
2. Esta copia ya tiene la rama `examen/cindy18-5-series-ii-iii`, creada desde main del curso. Confirmar el destino con `git remote -v`.
3. Guardar las pruebas correctas:

```powershell
git add cypress/e2e/serie-ii.cy.js SERIES-II-III.md
git commit -m "test: agregar pruebas de la Serie II"
```

4. En la prueba de agregar producto, cambiar la expectativa de 6 filas a 7. Confirmar y subir:

```powershell
git add cypress/e2e/serie-ii.cy.js
git commit -m "test: introducir falla intencional en cantidad de productos"
git push -u origin examen/cindy18-5-series-ii-iii
```

5. Abrir un Pull Request en Cindy18-5/admin-productos con base main y la rama de trabajo. Esperar CI rojo y descargar los artefactos cypress-video y cypress-capturas de ESA ejecucion.
6. Corregir 7 por 6 y subir:

```powershell
git add cypress/e2e/serie-ii.cy.js
git commit -m "fix: esperar seis productos despues del alta"
git push
```

7. Esperar CI verde, mostrarlo al docente y hacer merge. Actualizar main:

```powershell
git switch main
git pull --ff-only origin main
git log --oneline --graph --decorate -10
```

Entregar el enlace del fork y el PR creado en ese fork. Explicar que commit guarda cambios localmente, push los envia a GitHub y Actions ejecuta las pruebas en cada push o pull_request.
