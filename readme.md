### ¿Qué comando utilizaste en el paso 11? ¿Por qué?

**Deshacer el último commit (perdiendo los cambios realizados en el working copy)**

`git log`

Veo el historial para poder ver __ID hash__ al que quiero retroceder.

Aunque es opcional utilizando el posicionamiento relativo `HEAD~n` dónde n es el número de posiciones a retroceder desde la posición actual.

`git reset --hard HEAD~1`

Utilizo `--hard` para forzar perder cambios en el working copy si los hubiera.

### ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

**Rehacer el último commit (el que acabamos de deshacer)**

`git reflog`

Veo el ID del antiguo commit

`5f3a6e9 HEAD@{1}: commit: Doy estilo a git-nuestro.md`

Y me muevo a él:

`git reset --hard 5f3a6e9`


### El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?

**Hacer un merge con ‘master’ (styled absorbe a master)**

La rama _master_ no ha hecho ningún commit desde que se ramifico _styled_ por lo que esta todo al día.

### El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?

**Hacer un merge de “htmlify” en “styled” (styled absorbe a htmlify)**

Si porque se esta haciendo merge de un commit de una rama el cual contiene un archivo con contenido distinto a la de la rama actual.

### El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?

**Desde “master”, hacer un merge con “styled”**

No porque como en _master_ no se ha añadido ningún commit desde que ramifico _styled_ simplemente avanza _master_ hasta el último commit de _styled_

### ¿Qué comando o comandos utilizaste en el paso 25?

**Dibujar el diagrama**

`git log --graph --decorate --pretty=oneline`

### El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

**Hacer un merge “no fast-forward” de “title” en “master” (master absorbe a title)**

Si porque desde que se ramifico _title_ no se hizo ningún commit en _master_ 

### ¿Qué comando o comandos utilizaste en el paso 27?

**Deshacer el merge (sin perder los cambios del working copy)**

`git log --graph --decorate --pretty=oneline`

Para ver el commit antes de que _master_ mergueara _title_

Aunque también se podría hacer directamente:

`git reset HEAD~1``

Sin `--hard` para mantener los cambios del working copy


### ¿Qué comando o comandos utilizaste en el paso 28?

**Descartar los cambios**

`git checkout git-nuestro.md`

### ¿Qué comando o comandos utilizaste en el paso 29?

**Eliminar la rama “title”**

`git branch -D title`

### ¿Qué comando o comandos utilizaste en el paso 30?

**Rehacer el merge que hemos deshecho**

`git reflog`

284cb4c HEAD@{1}: merge title: Merge made by the 'recursive' strategy.

`git reset --hard 284cb4c`


### ¿Qué comando o comandos usaste en el paso 32?

**Volver al commit inicial cuando se creó el poema**

`git log --graph --decorate --pretty=oneline`

`git checkout e5e0502a533e339029f00ebfbfbc3fab36c679ce`


### ¿Qué comando o comandos usaste en el punto 33?

**Volver al estado final, cuando pusimos título al poema**

`git log --graph --decorate --pretty=oneline`

`git checkout dcdc7e9b7e1f01541e958e53ac6c2b01552968a5`