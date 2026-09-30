# Portal Andina

Repositorio de práctica del curso **Desarrollo de software asistido por IA** de Edutin Academy.
Distribuidora Andina y Nodo Software son empresas ficticias; todos los datos son inventados.

## Requisitos
- Node.js 22.13 o superior (usa el módulo `node:sqlite` incluido en Node).
- Git.

## Primeros pasos
1. En GitHub, en la página de este repositorio, haz clic en **Use this template** → **Create a new repository**.
2. Elige tu cuenta como dueña, ponle un nombre y **marca la casilla «Include all branches»**. Sin esa casilla, tu copia no trae los puntos de control.
3. Clona tu copia y ejecuta:
```bash
npm install
npx playwright install chromium   # solo la primera vez, para las pruebas de extremo a extremo
npm run dev
```
Abre http://localhost:5173 e ingresa con el código de vendedor `V-101`, `V-102` o `V-103`.

## Comandos
| Comando | Qué hace |
|---|---|
| `npm run dev` | Levanta la API (3001) y la web (5173) |
| `npm test` | Pruebas unitarias y de integración |
| `npm run test:e2e` | Pruebas de extremo a extremo con Playwright |
| `npm run lint` | Verificación de tipos |
| `npm run db:reset` | Vuelve a cargar la base local desde `test-data/` |

## Puntos de control
El repositorio tiene una rama por cada punto de control del curso (`punto-01-inicio`, `punto-02-plan-aprobado`…), con el estado esperado al terminar cada etapa.
Si te pierdes, puedes comparar tu trabajo con un punto de control o partir de él.

Para ver y comparar:
```bash
git branch -r                                   # lista los puntos de control
git diff origin/punto-02-plan-aprobado          # compara tu trabajo con un punto de control
```

**Los puntos de control no son para abrir un pull request.** En una copia creada con «Include all branches», GitHub guarda cada rama como un commit inicial propio, así que los puntos de control y `main` no comparten historia. Si creas tu rama directamente desde un punto de control, GitHub no podrá compararla con `main` y no te dejará abrir el pull request.

Para partir de un punto de control, crea tu rama desde `main` y trae los archivos del punto:
```bash
git switch main
git switch -c mi-rama                           # tu rama de trabajo, creada desde main
git checkout origin/punto-04-endpoint-revisado -- .   # cambia el número por el punto que necesitas
git add -A
git commit -m "Parto del punto 04"
```
Después sigue trabajando en `mi-rama` y abre el pull request desde ella hacia `main`.

## Estructura
```
apps/api      API (Express + SQLite)
apps/web      Portal web (React + Vite)
test-data     Datos sintéticos y su script generador
e2e           Pruebas de extremo a extremo
docs          Historias de usuario y planes
```
