# Clase 04

## Buenas prácticas para ponerle un buen mensaje a los commits

<https://medium.com/@jmz12/buenas-pr%C3%A1cticas-para-commits-5eb4c86b9a47>

## GIT REBASE
Muy parecido al MERGE. Me permite unir ramas con una particularidad.

    git rebase <rama-que-me-quiero-traer>

Ej: Si quiero traerme los cambios de <dev> a la rama <master> tengo que estar posicionado sobre la rama <master>

    git rebase master

## GITHUB PAGES
Hosting gratutito para subir código html, css, js (React, Angular, VUE, Svelte)

Creo un repo. Repo mágico

<nombre-cuenta-gihub>.github.io
mlapeducacionit.github.io

## Trabajar en proyectos Open Source (Pull Request)

1. Hacer un fork del proyecto. Del proyecto del cual quiero contribuir (Me voy copiar en mi cuenta el repo del proyecto original)
2. Me clono el fork desde mi cuenta github
3. Trabajo normalmente. Subo los cambios (A repo propio)
4. Me voy al proyecto original en el apartado Pull Request. Creo un nuevo Pull Request. Algunas veces aparece en mi repo la posibilidad Pull Request.
---
5. Si el repo original sufrió más modificaciones. (Commits). Voy a tener que actualizar mi fork.
6. Voy a la cuenta del proyecto original y me copio la url del repositorio
7. Y agrego en mi repositorio local, la url (el remoto) del proyecto original.

    git remote upstream <URL-repositorio-original>

8. Me traigo los cambios del repositorio original a mi repo local

    git pull upstream <rama-que-quiero-actualizar>

9. Subo a mi repositorio remoto (Fork) las actualizaciones del repo local

    git push origin <rama-a-actualizar>

## Apuntadores

### Apuntadores Dinamicos

* HEAD

### Apuntadores estaticos

* RAMAS (locales y remotas)
* TAG
* STASH

## TAGS
Me permiten marcas commits en particular.

> Listar tags

    git tag

> Crear un tag

    git tag <nombre-tag>
    git tag tengo-un-problema

> Borrar tags

    git tag -d <nombre-tag>
    git tag -d problema

> Crear un tag con versiona semantico

    git tag -a v1.0.0 <hash> -m "Versión 1.0.0"
    git tag -a v1.0.0 0801cf6 -m "Versión 1.0.0"

* a: anotado
* m: mensaje
#### VERSIONADO SEMANTICO
<https://semver.org/lang/es/>

> Ver detalle de los tags, quien creo y en que commit están creados

    git show <tag>
    git show v1.0.0

> Para subir tag especifico (Recomendada)

    git push origin <nombre-tag>
    git push origin v1.0.0

> Para subir todos tags (NO RECOMENDA)

    git push --tags

## GIT ADD (Continuación)
GIT ADD PATCH
git add --patch
* y: Para confirmar el hunk (Pedacito de código)
* n: Para descartar el hunk (Pedacito de código)
## GIT REBASE INTERACTIVO (AVANZADO)
* Ordenar commits
* Corregir mensajes de los commits
* Unir commits
* Separar commits
git rebase -i <hash> #inmedito inferior a lo que quiero seleccionar

Una vez selecccionamos los commits tengo que seguir los pasos que me sugiriendo.

r, reword: Cambiar el mensaje del commits. s, squash: Nos permite fusionar commits.

En el caso de surgir algún problema.

git rebase --abort

## Git eBooks
https://git-scm.com/book/en/v2