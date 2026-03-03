  "Version 1.0.0 lista" >> README.md
Proyecto Git Flow – Julieth Rojas
Descripción

Este proyecto es una práctica de Git Flow y Conventional Commits, usando un flujo completo de desarrollo en un proyecto Python.
Se aplicaron las siguientes etapas:

Feature: creación de nuevas funcionalidades

Release: preparación de la versión final

Hotfix: corrección de errores

Todos los commits siguen el estándar Conventional Commits.
Archivos del proyecto

main.py → contiene funciones de ejemplo (saludo, despedida)

README.md → documentación del flujo

 # Inicializar Git y Git Flow
git init
git flow init

Se crearon las ramas main y develop.
 https://github.com/juliethrojas755-beep/Github_actividad/blob/3f7311af4c484cfc9cc37d9951c357ca8e1e245f/Git.png


# Crear una feature
git flow feature start miFeature

Rama creada: feature/miFeature

Comandos para commits usando Conventional Commits:

git add main.py
git commit -m "feat: crear función saludo"
git add main.py
git commit -m "feat: agregar función de despedida"

Finalizar feature:

git flow feature finish miFeature

https://github.com/juliethrojas755-beep/Github_actividad/blob/14e8fb7fb7769dd2dde4284b739a7e859fc46391/Feature.png

 # Crear y finalizar la release
git flow release start v1.0.0
# Actualizar README
echo "Versión 1.0.0 lista" >> README.md
git add README.md
git commit -m "docs: actualizar README con versión 1.0.0"
git flow release finish v1.0.0
# Si falla el tag automático:
git tag -a v1.0.0 -m "Release v1.0.0"
git push origin v1.0.0

Se fusionó en main y develop.

Se creó el tag v1.0.0.
https://github.com/juliethrojas755-beep/Github_actividad/blob/bffb128e5f37aa073a6b5c7e8c7289bcd21ab963/Release.png


# Crear y finalizar un hotfix
git flow hotfix start fix-saludo

https://github.com/juliethrojas755-beep/Github_actividad/blob/a8fd2c4c963bd3763102ccf66758e2f0d0064b7c/Hotfix.png

# Corrección en main.py
echo 'print("¡Hola, este es mi primer proyecto con Git Flow!")' > main.py
git add main.py
git commit -m "fix: corregir mensaje de saludo en main.py"
git flow hotfix finish fix-saludo

https://github.com/juliethrojas755-beep/Github_actividad/blob/0965bb9cc4e5b79cb46599b5d226b61dd83f5b70/Correccion%20saludo.png

# Crear tag manual si falla
git tag -a v1.0.1 -m "Hotfix: corregir mensaje de saludo"
git push origin v1.0.1

https://github.com/juliethrojas755-beep/Github_actividad/blob/955cd68b2600dade4a2102144e547425d9d9691f/tags.png

Subir todo a GitHub
git remote add origin https://github.com/juliethrojas755-beep/Github_actividad.git
git push -u origin main
git push origin develop
git push origin --tags
