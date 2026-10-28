# Documentación de mi entorno de desarrollo · Práctica 2

**Raul Lucchini:**
**[URL de mi repositorio:](https://github.com/Lucchiniii/entorno-daw-Raul-Lucchini)**
 
> Rellena cada apartado a medida que avanzas. Donde pone «pega aquí», copia el texto
> de la terminal (no hace falta captura). Escribe con tus palabras: no se valora la longitud,
> sino que se note que entiendes lo que has hecho.

---

## 1. Instalación de entornos (CE 2.a)

### 1.1. Entorno vacío (paso 3)

Resultado de `java -version` y `node -v` **antes** de instalar nada:

```
bash: Java: command not foundbash: 
node: command not found
```

¿Por qué crees que aparece ese mensaje? (relaciónalo con la diapositiva «Problemas habituales del entorno»)

> No aparece nada por que no lo tenemos instalado todavía.

### 1.2. Después de la 1.ª reconstrucción (paso 5)

Resultado de `java -version`, `node -v` y `jupyter lab --version` **después**:

```
openjdk version "27" 2026-09-15
OpenJDK Runtime Environment Temurin-27+35 (build 27+35)
OpenJDK 64-Bit Server VM Temurin-27+35 (build 27+35, mixed mode, sharing)

v24.22.1

bash: Jupyter: command not found
```

¿Qué líneas nuevas han aparecido en `devcontainer.json`? Explica con tus palabras qué hace cada una:

> yo no he notado ningún cambio en las lineas despues del rebuild, simplemente que ahora tengo instalado java y node

### 1.3. Comparativa de los dos IDE (paso 6)

|                                         | Editor de GitHub Codespaces | JupyterLab           |
|-----------------------------------------|-----------------------------|----------------------| 
| ¿Libre o propietario?                   |propietario como servicio git|libre y code abierto. |
| Licencia / empresa o comunidad          |Microsoft/github             |BSD / Jupyter         |
| ¿Tiene coste? ¿Con qué límites?         |Gratis limitado              |Gratis                |
| ¿Se puede usar fuera de GitHub?         |No directamente              |si, independientemente|
| ¿Para qué tipo de trabajo lo elegiría?  |Desarrollo web               |analisis datos        |

---

## 2. Módulos y extensiones (CE 2.b)

| Extensión | ¿Para qué sirve? | ¿Qué cambió al instalarla? | ¿La mantengo? ¿Por qué? |
|-----------|------------------|----------------------------|-------------------------|
| Extension Pack for Java |   |   |   |
| Code Spell Checker      |   |   |   |

¿Qué diferencia hay entre instalar una extensión **solo desde el panel** y añadirla **también a `devcontainer.json`**?

> 

---

## 3. Personalización y automatización (CE 2.c)

- **Tema visual elegido** (paso 10) y por qué:
- **Ajuste del proyecto** (paso 10). ¿Qué archivo se ha creado y qué contiene?

```
pega aquí el contenido de .vscode/settings.json
```

- **Atajo de teclado** (paso 11). ¿Qué acción, qué combinación y para qué te sirve?
- **Snippet** (paso 12). ¿Qué escribes y qué aparece?
- **Automatización al crear el entorno** (paso 14). ¿Qué hace `postCreateCommand` y qué archivos/carpetas han aparecido después de reconstruir?
- **Tareas** (paso 13). ¿Cuántas tareas hay en `tasks.json` y qué hace cada una?

¿Qué parte de toda esta configuración es **personal** (solo para ti) y qué parte es **del proyecto** (la recibe cualquiera que abra el repositorio)?

> 

---

## 4. Ejecutables de diferentes lenguajes en el mismo entorno (CE 2.e)

Salida completa de la tarea **Build completo** (paso 15):

```
=== FACTURA generada con Node.js v24.22.1 ===
Dominio web anual              12.00 EUR
Alojamiento web                59.90 EUR
Logotipo corporativo          150.00 EUR
-----------------------------------------
Base imponible                221.90 EUR
IVA (21 %)                     46.60 EUR
TOTAL                         268.50 EUR
```

| Lenguaje | Archivo fuente | Herramienta que lo traduce | Archivo generado | Cómo se ejecuta |
|----------|----------------|----------------------------|------------------|-----------------|
| Java       | `src/java/Factura.java` |    javac        |    Factura.class | En la JVM con java Factura         |
| TypeScript | `src/ts/factura.ts`     |       tsc       |     factura.js   |Con Node.js (node factura.js) o en un navegador|

**Opcional:** ¿has podido ejecutar los mismos archivos desde JupyterLab (paso 19)? ¿Por qué funciona en los dos IDE sin instalar nada más?

> no funciona jupyter

---

## 5. Sistema de actualizaciones (CE 2.d)

| Elemento | ¿Quién lo actualiza? | Modo (automático / manual / ninguno) | Qué he configurado yo |
|----------|----------------------|--------------------------------------|-----------------------|
| El editor de Codespaces |   |   |   |
| Las extensiones         |   |   |   |
| Java                    |   |   |   |
| Node.js                 |   |   |   |
| Dependencias npm (lodash, typescript…) |   |   |   |

Versión de Java **antes** (paso 5) y **después** (paso 18):

```
openjdk version "27" 2026-09-15
OpenJDK Runtime Environment Temurin-27+35 (build 27+35)
OpenJDK 64-Bit Server VM Temurin-27+35 (build 27+35, mixed mode, sharing)
```

Resultado de `npm outdated` (paso 17):

```
Package         Current    Wanted   Latest  Location                    Depended by
@types/lodash  4.14.202  4.14.202  4.17.27  node_modules/@types/lodash  entorno-daw-Raul-Lucchini
@types/node    20.11.30  20.11.30   26.6.5  node_modules/@types/node    entorno-daw-Raul-Lucchini
lodash          4.17.20   4.17.20   4.18.1  node_modules/lodash         entorno-daw-Raul-Lucchini
typescript        5.4.5     5.4.5    7.0.2  node_modules/typescript     entorno-daw-Raul-Lucchini
```

Resultado de `npm audit` **antes** de actualizar lodash (solo el resumen final):

```
# npm audit report

lodash  <=4.17.23
Severity: high
Command Injection in lodash - https://github.com/advisories/GHSA-35jh-r3h4-6jhm
Regular Expression Denial of Service (ReDoS) in lodash - https://github.com/advisories/GHSA-29mw-wpgm-hmr9
lodash vulnerable to Code Injection via `_.template` imports key names - https://github.com/advisories/GHSA-r5fr-rjxr-66jc
lodash vulnerable to Prototype Pollution via array path bypass in `_.unset` and `_.omit` - https://github.com/advisories/GHSA-f23m-r3pf-42rh
Lodash has Prototype Pollution Vulnerability in `_.unset` and `_.omit` functions - https://github.com/advisories/GHSA-xxjr-mmjv-4gpg
fix available via `npm audit fix --force`
Will install lodash@4.18.1, which is outside the stated dependency range
node_modules/lodash

1 high severity vulnerability

To address all issues, run:
  npm audit fix --force
```

Resultado de `npm audit` **después**:

```
4.18.1
```

**Mi política de actualizaciones**: si este entorno lo usara un equipo de 5 personas durante todo el curso, ¿qué dejarías en automático y qué fijarías a mano? Justifícalo.

> Dejaría las actualizaciones de las dependencias fijadas en una versión concreta durante el curso para que las cinco personas trabajen con el mismo entorno. Haría las actualizaciones de forma manual y controlada, probándolas antes de aplicarlas. Así evitaría errores o incompatibilidades que pudieran afectar al proyecto.

---

## 6. Incidencias

Anota cualquier problema que hayas tenido y cómo lo resolviste (también si usaste un fragmento completo).

> He tenido que configurar el entorno de desarrollo y comprobar que las rutas de los archivos fueran correctas. Lo resolvería revisando la configuración y verificando que las herramientas necesarias estuvieran instaladas correctamente.

## 7. Reflexión final

¿Qué ventaja tiene describir el entorno «como código» frente a instalar cada programa a mano en tu ordenador? Piensa en un equipo con Mac y Windows.

> Describir el entorno como código permite que todos los miembros del equipo utilicen las mismas versiones de los programas y dependencias. Así, en Mac y Windows se puede reproducir el mismo entorno sin instalar y configurar cada herramienta manualmente. Esto facilita la colaboración, reduce errores y hace que el proyecto sea más fácil de mantener.