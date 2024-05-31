## Pasos para Crear y Administrar Git Submodules

### Creación de un Submódulo

1. **Crear un Nuevo Repositorio en GitHub**  
   Crea el repositorio que se utilizará como submódulo.

2. **Clonar el Repositorio Principal en la Máquina Local**  
   Clona el repositorio donde deseas añadir el submódulo:

   ```bash
   git clone <main_repository_url>
   cd <main_repository_name>
   ```

3. **Inicializar y Actualizar Submódulos Existentes**  
   Si el repositorio principal ya tiene submódulos, inicialízalos y actualízalos:

   ```bash
   git submodule update --init --recursive
   ```

4. **Añadir un Nuevo Submódulo**  
   Añade el submódulo utilizando la URL del nuevo repositorio y especifica la carpeta donde se almacenará (esta carpeta no debe existir previamente en el proyecto):

   ```bash
   git submodule add <repository_url> <directory_name>
   ```

5. **Añadir y Subir Cambios al Repositorio Principal**  
   Añade, commitea y empuja los cambios al repositorio principal:

   ```bash
   git add .
   git commit -m "Add submodule"
   git push
   ```

### Mantenimiento de Submódulos

1. **Inicializar y Actualizar Submódulos al Clonar el Repositorio**  
   Cuando alguien clona el repositorio por primera vez, debe ejecutar el siguiente comando para inicializar y actualizar los submódulos:

   ```bash
   git submodule update --init --recursive
   ```

2. **Actualizar Referencias de los Submódulos**  
   Para actualizar los submódulos a sus últimas versiones remotas:

   ```bash
   git submodule update --remote
   ```

## Importante

Si se trabaja en un repositorio que contiene submódulos, **siempre se debe actualizar y hacer push en el submódulo primero y luego en el repositorio principal**.  
Hacerlo al revés puede causar pérdida de referencias de los submódulos en el repositorio principal, lo que llevará a conflictos que tendrán que ser resueltos.
