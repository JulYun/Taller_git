Git Exercises

Este documento contiene una serie de ejercicios prácticos para aprender y practicar comandos de Git.

 01: Creación de estructura de directorios

Crear la estructura de directorios mostrada a continuación:
mkdir -p taller_git/001_local

Verificar la estructura:
tree
git cd taller_git/001_local

 02: Seguimiento y gestión de archivos

Ejecute los siguientes comandos respetando el orden:

git status
touch test_001.txt
git status
git add test_001.txt
git status
git commit -m "[jvo2967] Adding the first file"
git status
ls -lt

Crear archivos adicionales y gestionar el índice:
git status
touch test_002.txt test_003.txt
git status
git add test_002.txt test_003.txt
git status
git restore --staged test_003.txt
git status
ls -lt

 03: Uso de Stash

Mover el archivo test_002.txt al área de stash y luego restaurarlo:

git status
ls -lt
git stash
git status
ls -lt
git stash apply
git status
ls -lt

 04: Versionado de archivos

touch test_001.txt test_002.txt
git add test_001.txt test_002.txt
git commit -m "[jvo2967] Versioning files"

Ejercicio 05: Sincronización con GitLab

Crear el archivo test_003.txt en GitLab, comparar repositorios y actualizar:

git pull
ls -lat
git status

 06: Restauración de cambios
Modificar, versionar y restaurar un archivo:

git status
echo "This is the first comment" > test_001.txt
cat test_001.txt
git add test_001.txt
git commit -m "[jvo2967] Adding the first comment"
echo "This is a bad idea" > test_001.txt
cat test_001.txt
git restore test_001.txt
cat test_001.txt
git status
git push


Ejercicio 07: Agregar y subir archivos


git status
touch test_001.txt test_002.txt
git status
git add test_001.txt test_002.txt
git status
git commit -m "[jvo2967] Adding 2 files to main branch"
git status
git push
git status


 08: Control de versiones

echo "This is the second comment" >> test_001.txt
cat test_001.txt
git add test_001.txt
git commit -m "[jvo2967] Adding the second comment, #2"
echo "This is the third comment" >> test_001.txt
cat test_001.txt
git add test_001.txt
git commit -m "[jvo2967] Adding the third comment, #3"
echo "This is a bad idea" > test_001.txt
cat test_001.txt
git log --oneline test_001.txt
git checkout 6a47c00 -- test_001.txt
cat test_001.txt

Ejercicio 09: Subir cambios al repositorio remoto

git status
git commit -m "[jvo2967] Restoring to the second comment"
git status
git push


10: Ramas en GitLab

git status
git branch
git fetch
git branch
git checkout feature/001
git branch
cat .git/HEAD
git checkout main
git branch
cat .git/HEAD

11: Creación de ramas y versionado


git status
git checkout -b feature/002
touch test_005.txt
git status
git add test_005.txt
git status
git commit -m "[jvo2967] Adding file for feature 002"
git status
git push origin -u feature/002
git status

12: Gestión de ramas 
git checkout -b feature/003
git status
git branch -vv
git push origin -u feature/003
git branch -vv
git checkout main
git branch -d feature/003
git branch -a
git push origin -d feature/003