# GLAB-S12 · ajax-react-lab

Procedimiento del Laboratorio 12 de Desarrollo de Aplicaciones Empresariales (Tecsup, 2026-02): **Ajax y servicios web
con React**. Proyecto creado con `create-react-app`, `axios` y `react-bootstrap`, consumiendo
[swapi.dev](https://swapi.dev/api/people/).

Alumno: Alvarez Sayaverde Alejandro Aaron · Grupo C · Docente: Jean Marco Miranda Llanos.

La TAREA (buscador en tiempo real con filtros) está en otro repositorio:
[GLAB-S12-buscador-star-wars](https://github.com/ALEDEROSEE/GLAB-S12-buscador-star-wars).

## Cómo correrlo

```bash
npm install
npm start
```

Abre <http://localhost:3000>. Probado con Node 24.15.0 y npm 11.12.1.

## Qué hay en `src/`

| Archivo | Paso de la guía |
| --- | --- |
| `CharacterList.js` | Paso 3: componente de clase, pide los personajes en `componentDidMount` |
| `DataLoader.js` | Paso 6: carga simulada con `setTimeout` (2 s) |
| `CharacterLoader.js` | Paso 9: `axios.get` al pulsar el botón, con hooks |
| `App.js` | Paso 10: usa `CharacterLoader` (para ver los otros dos, cambiar el import y la etiqueta) |
| `index.js` | Igual que CRA, más `import 'bootstrap/dist/css/bootstrap.min.css'` (la guía no lo incluye) |

El código de los tres componentes es el de la guía, sin cambios.

## Lo que encontré al ejecutarlo

- Sin el import del CSS de Bootstrap, las tarjetas salen en una sola columna y sin bordes.
- El título "Personajes de Star Wars" aparece dos veces (el `h1` de `App.js` y el `h2` de `CharacterList`).
- swapi.dev devuelve `count: 82`, pero entrega 10 personajes por página.
- En desarrollo, `CharacterList` hace dos peticiones idénticas al abrir la página (`React.StrictMode`).
- `DataLoader` no hace ninguna petición: son 2001 ms de `setTimeout`.
- Si falla la red, el `.catch` de la guía solo escribe en la consola y la pantalla no muestra nada.
