# practicaGit_ElisaGutierrezParraga
- ¿Qué comando utilizaste en el paso 11? ¿Por qué?
En el paso 11 he ejecutado el comando "git reset --hard HEAD~1".

Con git reset podemos mover una rama a donde queramos. En este caso, un commit atrás con la indicación "HEAD~1".
Indicamos --hard para perder los cambios realizados en el working copy. Si no indicasemos --hard, todos los cambios del commit que saltamos, los estaríamos recuperando en el working copy.


- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?
He hecho git reflog para copiar el chash del commit realizado antes del reset primero, donde se había modificado el fichero.
Después, he hecho git reset --hard <commit hash> con el hash del commit antes de hacer el reset primero.
Por último, he hecho "nano git-nuestro.md" y veo que aparecen los cambios en el fichero.

- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
Como style debe absober a main, he hecho "git merge main" desde la rama style.
No hay conflicto porque la rama styled ya contiene todos los commits que hay main. Por esto, este merge no trae ningún cambio a la rama styled.

- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
Si, hay conflictos. Ambas ramas han modificado el mismo fichero en las mismas líneas.

- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
No, no hay conflictos porque la rama styled ha modificado un archivo que estaba en main y no ha sido modificado tras crear la rama styled desde main. 
Al no haber cambios en main tras crear la rama Styled, styled contiene los cambios de main más los suyos, sin dar lugar a conflictos.

- ¿Qué comando o comandos utilizaste en el paso 25?
He usado el comando "git log --graph --decorate --pretty=oneline"

- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?
sería fast-forward porque las ramas title y main forman un grafo linea, es decir, no hay bifurcaciones.
Pâra obligar a que sea no-fastforward, he realizado el siguiente comando:
"git merge --no-ff title"

- ¿Qué comando o comandos utilizaste en el paso 27?
"git reset HEAD~1". Con este comando traigo los cambios que ha generado el merge a mi working copy.

- ¿Qué comando o comandos utilizaste en el paso 28?
Con "git status" veo los ficheros que tienen modificaciones sin subir al repositorio, que, en este caso, es el fichero git-nuestro.md.
Para descartar los cambios de este fichero hago "git restore git-nuestro.md". 
Después, con git status veo que mi working copy no tiene cambios.

- ¿Qué comando o comandos utilizaste en el paso 29?
 "git branch -d title" no funciona porque, como tiene cambios no mergeados, para no perderlos, Git me avisa. 
 Para que Git me permita borrar la rama sabiendo que tiene cambios sin mergear, hago "git branch -D title", y ya sí que me ha dejado.

- ¿Qué comando o comandos utilizaste en el paso 30?
Hago "gir reflog" y veo cual  es el hash previo al commit con esta descripción "HEAD@{0}: reset: moving to HEAD~1",
ya que si en ese commit he hecho reset, en el commit anterior, tengo los cambios.
Después, hago "git reset --hard HEAD@{1}". 
Para verificar el cambio, hago "cat git-nuestro.md" y veo que el título que añadí al fichero aparece correctamente.

- ¿Qué comando o comandos usaste en el paso 32?
hago git log para ver el listado de commits y cojo el hash del primero de ellos, es decir, el último de la lista (fecha más antigua).
Hago git checkout <commitHash>

- ¿Qué comando o comandos usaste en el punto 33?
hago git log para ver el listado de commits y cojo el hash del último de ellos, es decir, el primero de la lista (fecha más reciente).
Hago git checkout <commitHash>
