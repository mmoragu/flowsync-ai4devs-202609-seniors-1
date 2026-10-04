# Prompts

Prompts lanzados, en orden, con modelo y herramienta. Mismo texto en las dos copias.

## Prompt 1 — copia CON harness

**Modelo:** PON-AQUI-EL-MODELO-REAL
**Herramienta:** Claude Code

```
Pantalla de inicio de sesión

Como usuario registrado de FlowSync, quiero poder iniciar sesión con mi email y contraseña desde la pantalla principal, para acceder a mi cuenta.

Criterios de aceptación:
- El formulario pide email y contraseña.
- Si las credenciales son correctas, el usuario accede (se le indica de alguna forma que ha entrado).
- Si son incorrectas, se le muestra un mensaje de error claro.
- El botón de enviar se deshabilita mientras se procesa la petición.
```

**Qué salió:** me preguntó Tailwind o CSS plano. Terminó en 10m43s con lint y build en verde.

## Prompt 2 — copia CON harness (respuesta a su pregunta)

**Modelo:** PON-AQUI-EL-MODELO-REAL
**Herramienta:** Claude Code

```
css plano
```

**Qué salió:** continuó con CSS plano y sin dependencias nuevas.

## Prompt 3 — copia SIN harness

**Modelo:** PON-AQUI-EL-MODELO-REAL
**Herramienta:** Claude Code

```
Pantalla de inicio de sesión

Como usuario registrado de FlowSync, quiero poder iniciar sesión con mi email y contraseña desde la pantalla principal, para acceder a mi cuenta.

Criterios de aceptación:
- El formulario pide email y contraseña.
- Si las credenciales son correctas, el usuario accede (se le indica de alguna forma que ha entrado).
- Si son incorrectas, se le muestra un mensaje de error claro.
- El botón de enviar se deshabilita mientras se procesa la petición.
```

**Qué salió:** no preguntó nada. Terminó en 1m46s con lint y build en verde.
