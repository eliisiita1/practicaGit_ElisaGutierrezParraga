# practicaGit_ElisaGutierrezParraga
**- ¿Qué comando utilizaste en el paso 11? ¿Por qué?**
  
En el paso 11 he ejecutado el siguiente comando:

```bash
 git reset --hard HEAD~1
```
Con git reset podemos mover una rama a donde queramos. En este caso, un commit atrás con la indicación "HEAD~1".\
Indicamos --hard para perder los cambios realizados en el working copy. Si no indicasemos --hard, todos los cambios del commit que saltamos, los estaríamos recuperando en el working copy.

**- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?**\
He hecho git reflog para copiar el hash del commit realizado antes del reset, donde se había modificado el fichero.\
Después, he hecho:
```bash
git reset --hard <commit hash>
```
donde <commit hash> es el hash del commit que tenía copiado.
Por último, he hecho:

```bash
cat git-nuestro.md
```
y veo que aparecen los cambios en el fichero.

**- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?**\
Como style debe absober a main, desde la rama style he ejecutado el siguiente comando:
```bash
git merge main
```
No hay conflictos porque la rama styled ya contiene todos los commits que hay main. Por esto, este merge no trae ningún cambio a la rama styled.

**- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?**\
Si, causó conflictos ya que en ambas ramas se había modificado el mismo fichero en las mismas líneas.

**- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?**\
No, no hay conflictos porque la rama styled ha modificado un archivo que estaba en main, donde no se ha vuelto a modificar el archivo tras crear la rama styled a partir esta rama.

Al no haber cambios en main tras crear la rama Styled, styled contiene los cambios de main más los suyos, sin dar lugar a conflictos.

**- ¿Qué comando o comandos utilizaste en el paso 25?**\
He usado el siguiente comando:

```bash
git log --graph --decorate --pretty=oneline
``` 

**- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?**\
Sería fast-forward porque las ramas title y main forman un grafo lineal, es decir, no hay bifurcaciones.\
Para obligar a que sea no-fastforward, he realizado el siguiente comando:
```bash
git merge --no-ff title
``` 

**- ¿Qué comando o comandos utilizaste en el paso 27?**\
Ejecuto el siguiente comando para traer los cambios que ha generado el merge a mi working copy.
```bash
git reset HEAD~1
``` 

**- ¿Qué comando o comandos utilizaste en el paso 28?**\
Con "git status" veo los ficheros que tienen modificaciones sin subir al repositorio, que, en este caso, es el fichero git-nuestro.md.\
Para descartar los cambios de este fichero ejecuto:
```bash
git restore git-nuestro.md
``` 
Después, con git status confirmo que no tengo nuevos cambios.

**- ¿Qué comando o comandos utilizaste en el paso 29?**\
El siguiente comando: 
```bash
git branch -d title
``` 
no funciona porque, como tiene cambios no mergeados, para no perderlos, Git me avisa de que si la borrase, esos commits se quedarían sin rama.

Para que Git me permita borrar la rama sabiendo que tiene cambios sin mergear, ejecuto el siguiente comando, que resulta exitoso:
```bash
git branch -D title
``` 

**- ¿Qué comando o comandos utilizaste en el paso 30?**\
Primero ejecuto el siguiente comando:
```bash
git reflog
```
y veo cual  es el hash previo al commit con esta descripción "HEAD@{0}: reset: moving to HEAD~1", ya que si en ese commit he hecho reset, en el commit anterior tendré los cambios que estoy buscando.

El commit anterior a HEAD@{0} es HEAD@{1}. Por ello, ejecuto el siguiente commando para moverme a ese commit:
```bash
git reset --hard HEAD@{1}
``` 
Para verificar el cambio, ejecuto:
```bash
cat git-nuestro.md
```
y veo que el título que añadí al fichero aparece correctamente.

**- ¿Qué comando o comandos usaste en el paso 32?**\
Primero ejecuto:
git log 
para ver el listado de commits y cojo el hash del primero de ellos, es decir, el último de la lista (fecha más antigua)\
Por último, ejecuto el siguiente comando para moverme a ese commit:
```bash
git checkout <commitHash>
```

**- ¿Qué comando o comandos usaste en el punto 33?**\
Primero ejecuto:
git log 
para ver el listado de commits y cojo el hash del último de ellos, es decir, el primero de la lista (fecha más reciente).\
Por último, ejecuto el siguiente comando para moverme a ese commit:
```bash
git checkout <commitHash>
```
