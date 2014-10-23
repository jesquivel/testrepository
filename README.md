GIT Pasos de instalacion y terminal, cada linea de excel es un solo comando	IR PASO A PASO EN LA GUIA PARA MEJOR ENTENDIMIENTO				
					
1. Descargar y instalar ultima version de GIT     ----------------------------->	http://git-scm.com/				
2. Ir a la terminal y hacer estos comandos:					
which git	[deberá mostrar donde está instalado GIT]				
git —version	[muestra la version de GIT que tenemos]				
git config --global user.mail “mymail@mail.com”					
git config --global user.name “Your Name”					
git config —list	[muestra los cambios agregados de nombre y mail]				
git config --global color.ui true					
cat .gitconfig	[muestra todos los cambios hechos hasta ahora]				
curl -OL https://github.com/git/git/raw/master/contrib/completion/git-completion.bash	[descargar el autocomplete de ayuda]				
ls -la	[deberá mostrar en la lista el archivo git-completion.bash]				
mv ~/git-completion.bash ~/.git-completion.bash	[ocupamos que el archivo se convierta en .git-completion.bash renombrandolo]				
ls -la	[para verificar que el archivo se movio como .git-completion.bash				
					
3. Editar el archivo oculto localizado en users/home/.bash_profile	Pueden editar este archivo desde terminal con nano pero es mejor con				
pueden usar la app Funter para ver archivos ocultos	editor de texto porque ya el archivo contiene una configuracion de variables				
	del ambiente de BV				
Agregar este bloque de codigo en el archivo .bash_profile					
					
if [ -f ~/.git-completion.bash ]; then	busca el archivo .git-completion y si lo encuentra lo carga con todo lo que tenga dentro				
source ~/.git-completion.bash					
fi					
					
Guardamos cambios					
Cerramos la terminal y la volvemos abrir, para comprobar que el autocomplete funciona.					
En la terminal:					
git h [presionamos la tecla tab y debera auto completar a git help]					
git help log	[muestra el manual de git con ayuda, barra espaciadora para pasar d pagina,				
	tecla f ó b para devolverse, tecla q para salir]				
					
4. Iniciar un repositorio					
Ya con Git instalado hay que crear el proyecto:					
					
Crear una carpeta en Documents llamada    first_git_project	Esta seccion es solo de prueba/test				
					
cd Documents/first_git_project/	Accesamos al folder				
git init	Inicializamos el repositorio de GIT vacio				
ls -la .git	Para ver los archivos y carpetas ocultas dentro de la carpeta del repositorio				
git add .	Agrega todos los archivos con el punto, ya podemos hacer commit	Git add lo agrega a stg y git commit al repositorio			
git commit -m "Initial commit"	Primer commit, lo que esta dentro de las comillas es el texto personalizado	Cada commit tiene un numero de version			
git log	estos cambios estan en el branch master	cada version se denomina como Snapshot.			
					
					
4.1 Parte opcional solo para ver los snapshots de master					
~/Documents/first_git_project$ ls -la					
cd .git	Accesamos a .git				
~/Documents/first_git_project/.git$ ls -la					
cat HEAD	Accesamos a head, ahi podremos ver el master				
~/Documents/first_git_project/.git$ cd refs	Accesamos a refs				
ls -la					
~/Documents/first_git_project/.git/refs$ cd heads	Accesamos a heads				
ls -la	Podemos ver el master				
~/Documents/first_git_project/.git/refs/heads$ cat master	Podemos ver el primer snapshot con el numero del commit del master				
git log					
git log head					
					
git status					
Agregamos 3 archivos html de prueba ejemplo first_file.html second_file.html etc					
git status	Deberan aperecer en otro color en la terminal los archivos agregados				
git add first_file.html					
git status					
git commit -m "Add first file to the project"					
git status	Todos estos cambios son para agregar archivos uno por uno para ir probando				
git add second_file.html	Si quisieran agregar todos de una sola ves:   git add .				
git commit -m "Add second file"					
git status					
git log					
					
git diff	Para ver los cambios de un archivo ha recibido, similar al tdiffer de SVN				
git diff [nombre del archivo]	Para ver los cambios de solo el archivo elegido				
git diff --staged	Para ver solo los cambios hechos en staging				
git rm [nombre del archivo]	Para borrar un archivo				
					
5. Agregar un proyecto a GitHub					
Crear el repositorio en GitHub https://github.com/new					
					
Luego del commit hacer estos comandos					
git remote add origin https://github.com/mpol90/repositorio2.git					
git push -u origin master					
					
6. Utilizar GitHub Pages					
1- Crear el branch aparte de master llamado gh-pages   http://i.imgur.com/vn73kVo.png					
1.1 - Utilizar la siguiente nomenclatura para ver la pagina subida en github como un sitio web					
http://mpol90.github.io/testrepository/second_file.html					
http://[nombreUsuario].github.io/[nombreRepositorio]/[nombreArchivoHTML.html]					
