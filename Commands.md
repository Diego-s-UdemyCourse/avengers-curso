<input type="text" id="searchInput" placeholder="Buscar...">
<ul id="searchResults"></ul>

<script>
  // Función para manejar la búsqueda
  function performSearch() {
    // Obtén el valor del campo de búsqueda
    var searchTerm = document.getElementById('searchInput').value.toLowerCase();
    
    // Obtén los elementos en los que deseas buscar (aquí, los elementos de lista en el markdown)
    var listItems = document.querySelectorAll('li');
    
    // Limpiar resultados anteriores
    document.getElementById('searchResults').innerHTML = '';

    // Itera sobre los elementos y muestra los resultados coincidentes
    listItems.forEach(function(item) {
      var text = item.textContent.toLowerCase();
      if (text.includes(searchTerm)) {
        var resultItem = document.createElement('li');
        resultItem.textContent = text;
        document.getElementById('searchResults').appendChild(resultItem);
      }
    });
  }

  // Asocia la función de búsqueda al evento de cambio en el campo de búsqueda
  document.getElementById('searchInput').addEventListener('input', performSearch);
</script>

# Comandos de git
```
*git init*
```
> inicializa el proyecto con git

```
git checkout -- . 
```
> Retorna el repositorio a la ultima version cargada con commit  
Solamente para los archivos que esten en el commit, los demas quedan igual

```
git status
```
> Muestra el status de git
```
git add .     
```
> Agrega todos los cambios al stash para posteriormente  
hacer commit
```
git add FILENAME   
```
> Agrega un solo archivo al stage
```
git branch    
```
> muestra las ramas existentes
```
git branch -m master main  
```
> Cambia el nombre de la rama master a main
```
git reset NOMBREDEARCHIVO 
```
> Saca el archivo del stash
```
.gitkeep   
```
> Al crear este archivo dentro de una carpeta, el sistema de git la carga al  
repositorio, aun si esta no contiene archivos
```
git add RUTA/*.js  
```
> Esto agrega al Stash todos los archivos con extensión .js dentro del  
directorio ruta/
```
git add css/
```
> Esto agrega al stash todo el contenido de la carpeta css
```
git diff   
```
> Muestra todos los archivos dentro del repositorio que se encuentran en estado modificado
```
git reflog 
```
> Historico de las referencias, movimiendos de HEAD y cambios en las ramas
```
git mv NOMBRE.TS NUEVONOMBRE.TS  
```
> Renombra un archivo dentro del repositorio

## Trabajo con ramas
```
git branch rama-diego     
```
> Se crea una rama nueva con el nombre de RAMA-DIEGO
```
git branch   
```
> Muestra las ramas que tiene el repositorio
```
git checkout rama-diego   
```
> Hace el cambio a la rama de diego
```
git branch -d rama-diego-villanos  
```
> Elimina la rama
```
git branch -d rama-diego-villanos  -f 
```
> Elimina la rama de manera forzada
```
git merge RAMAPARATRAERCAMBIOS   
```
> Se llaman los cambios que tiene la rama RAMAPARATRAERCAMBIOS
```
git tag super-release 
```
> Agrega un tag llamado super-release
```
git show NOMBREDELTAG  
```
> Muestra toda la información relacionada al tag
```
git stash 
```
> guarda los cambios que estoy realizando en una bobeda para despues retomarlos
```
git stash list   
```
> lista de los stash
```
git stash pop  
```
> Retoma los cambios guardados en el stash combinando con lo actual
```
git stash clear 
```
> limpia los stash
```
git stash drop stash@{0}
```
> elimina el stash con el ID0
```
git stash apply stash@{2} 
```
> Restaura el Stash numero 2
```
git stash show stash@{0}   
```
> Muestra los cambios de stash

## *Rebase sirve para ordenar commits, corregir mensajes de commits, unir commits y separar commits*
```
git rebase RAMADESTINO  
```
> Mueve los commit a la punta de la rama especificada
```
git rebase -i HEAD~4     
```
> Modo interactivo para editar los commit (En el modo interactivo cambiar  
pick por la letra que deseamos).
```
git rebase --continue     
```
> Una vez solucionados los problemas, salir del rebase
```
git checkout -- Readme.md   
```
> Regresa el archivo readme a la version almacenada en el commit, revierte cambios
```
git remote add origin https://NAME   
```
> add es crear un nuevo remoto y origin es el nombre del remoto, el estandar es origin
```
git remote -v    
```
> muestra los nombres remotos
```
git push -u origin master     
```
> origin nombre del repo, master es la rama
```
git push 
```
> Envia los cambios locales a un repositorio en la nube
```
git push --tags   
```
> Sube al repositorio los tags que tengamos en nuestro proyecto de git
```
git pull/git pull origin main   
```
> Trae lo ultimos cambios de la rama principal
```
git commit 
```
> Una vez corregidos los problemas hacer el commit y luego salir del rebase
```
git config --global -e  
```
> Muestra la configuración global por defecto
```
git fetch 
```
> Es una version anterior del git pull que consiste en que trae la  
información del servidor remoto pero no la combina con la rama local  
en la que nos encontramos trabajando. Si quieremos combinar esos cambios identificados en el fectch, es necesario ejecutar otra serie de comandos que combinen los cambios traidos con el fetch con la rama que se este trabajando localmente.


```

```


