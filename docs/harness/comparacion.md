# Comparación con y sin harness

Mismo encargo (login), mismo modelo, mismo texto. Harness: `CLAUDE.md` + hook PostToolUse con lint.

| | Con harness | Sin harness |
|---|---|---|
| Archivos tocados | 5 (2 mod., 3 nuevos), +227/-262 | 4 (2 mod., 2 nuevos), +291/-276 |
| Convenciones respetadas | No tocó `backend/`. Lint y build antes de terminar. Sin dependencias nuevas. Probó contra el backend real y corrigió el formato `{data:{...}}`. Llamada a la API separada en `lib/api.ts`. | No tocó `backend/` ni dependencias (el ticket no lo ejercía). Lint y build pasan. No había ninguna convención escrita. Guarda el token en `localStorage` y añade logout y persistencia sin que se pidieran. URL del backend escrita dentro del componente. |
| Intervenciones mías | 1 (Tailwind o CSS plano) | 0 |
| Qué arreglaría a mano | `App.css`: borró la plantilla de Vite sin mencionarlo en su resumen. No se verificó visualmente en navegador. | No probé el login con credenciales correctas, así que no sé si funciona. Por el código lee `data.user` y `data.token`, y la otra copia vio que el backend envuelve la respuesta en `data`, por lo que podría fallar. Sin verificar. Además, el mensaje de error es un texto fijo y no el del backend. |

Común a ambas: las dos vaciaron `App.css`. Lo de no tocar `backend/` no discrimina, porque el ticket no invitaba a hacerlo.

Sin terminar: no probé en navegador el login de la copia sin harness.

## Parte B

1. **Piezas:** `CLAUDE.md` y un hook `PostToolUse` que corre `npm run lint` en `frontend/`. La que más me costó: ninguna de las dos piezas en sí; el rato se me fue en dejar el entorno listo (WSL, herramientas, Jira) y en decidir qué poner en el CLAUDE.md. Del hook de lint no comprobé que se disparase, solo que el lint pasa.
2. **Primera diferencia:** la copia con harness me preguntó Tailwind o CSS plano y la pelada no preguntó nada. Lo vi en la terminal, mientras corría la sesión.
3. **Escrito en el harness y no cumplido:** mi `CLAUDE.md` decía que los componentes de shadcn/ui se copian a `frontend/src/components/ui`, pero el proyecto no tiene shadcn ni Tailwind. El agente no siguió la regla: detectó que no encajaba y me preguntó. La regla estaba mal escrita por mi parte.
