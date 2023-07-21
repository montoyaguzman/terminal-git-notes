#### Git

Git es un sistema de control de versiones.

Para obtener mas info del tema ir al repo de apuntes de git

#### Configuraciones iniciales

```
# establecer un usuario global
git config --global user.name "juanito perez"


# establecer un correo global
git config --global user.email juanito.perez@example.com

# inicializar una carpeta como repositorio
git init
```

#### Información del repo

```
# ver estado del working directory y/o staging area
git status

# ver historial de commits
git log --oneline
```

#### Hacer un commit

```
# agregar al staging area
git add .

# quitar del staging area
git restore --staged namefile.txt

# hacer un commit al repo local
git commit -m "conventionalCommitScope: mi mensaje"

```

#### Administración de ramas

```
# ver rama en la que se encuentra el head
git branch 

# crea una rama nueva
git branch newBranchName 

# cambiarse a una rama con el nombre nombreRama
git checkout branchName

# crear y cambiarse a una nueva rama
git checkout -b newBranchName

# crear y cambiarse a una nueva rama
git switch -c newBranchName 

# eliminar una rama
git branch -D branchName

```

#### Otros comandos útiles

```
# Descarta los cambios del stagin y working directory
git reset --hard

# actualiza la cache de git para que tome ciertos cambios (.gitignore)
git rm --cached . r

# actualiza el mensaje del ultimo commit realizado (no debe estar pusheado)
git commit --amend -m "an updated commit message"

# stash: el codigo de working directory y staging area es eliminado temporalmente
git stash

# stash: el codigo de working directory y staging area que fue eliminado se recuperar
git stash pop

```

[Más info](https://www.conventionalcommits.org/en/v1.0.0/)

#### Buenas practicas para mensajes de commits

##### Commits Atómicos

Consiste en realizar un commit por un solo objetivo. Es decir, no mezclar muchas soluciones en el mismo commit.

##### Conventional Commits

Es una especificación sobre como escribir mensajes de confirmación (commits).

**Estructura una línea**

```
[optional scope]: [optional body][optional footer(s)]
```

**Esctructura multilínea**

```
feat: add hat wobble
^--^  ^------------^
|     |
|     +-> Resumen en tiempo presente (no deberia ser un listado).
|
+-------> Tipo: chore(tarea), docs(documentos), feat(logro), fix(corrección), refactor(refactorización), style(estilo), or test(prueba).

[optional footer(s)]
```

**Tipos principales**

* **feat:** Nuevas funcionalidades.
* **chore:** Cosas que no aportan un requerimiento funcional, generalmente son requerimientos no funcionales.
* **fix:** Corrección de errores.
* **docs:** Documentación o comentarios.
* **style:** Cambios de legibilidad o formateo de código que no afecta a funcionalidad.
* **refactor:** Modificaciones de código o arquitectura que no corrige errores ni añade funcionalidad, pero mejora la escritura y optimiza la funcionalidad.
* **test:** Para añadir o arreglar tests.

**Referencias**

- [Semantic commit messages](https://gist.github.com/joshbuchea/6f47e86d2510bce28f8e7f42ae84c716).
- [Conventional commits](https://www.conventionalcommits.org/).
- [Karma](http://karma-runner.github.io/1.0/dev/git-commit-msg.html).


#### Github

Ir al repo de terminal y git.

Github es el repositorio remoto a donde podemos respaldar el codigo. Los siguientes comandos funcioan para conectarse a cualquier repositorio remoto, nos sólo a github, por ejemplo gitlab o bitbucket.

#### Generar llave ssh

```
# generar ssh key
ssh-keygen

# ver llave pública
cat ~/.ssh/id_rsa.pub
```

#### Conexión al repo remoto

```
# ver los repos remotos a los que esta conectado el repo local
git remote -v

# agregar una direccion remoto (origin)
git remote add origin myUrl

# modificar una direccion remoto (origin)
git remote set-url origin myUrl
```

### Subir y bajar cambios

```
# bajar cambios
git pull origin branchNamesubir cambios

# git push origin branchName

# subir cambios de una rama nueva para el remoto
git push -u origin branchName

# obtener los cambios de una rama remota y cambiarse a esa rama

git fetch && git checkout develop
```
