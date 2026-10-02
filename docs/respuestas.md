¿Qué ventaja tiene registrar las dependencias del proyecto en
requirements.txt en lugar de compartir la carpeta .venv?

R: Es mejor evitar compartir un archivo tan grande y que solo cumple con funciones específicas como el entorno virtual, ya que requiere demasiado espacio y que no pueden ser utilizados por otros desarrolladores, para ello, el archivo requirements.txt se utiliza para registrar las dependencias del proyecto mostrándole a los colaboradores que dependencias requiere el proyecto.

¿Por que el repositorio que tienes ahora en tu computadora no es el mismo concepto que el del git?

R: El repositorio es un repositorio de código, mientras que el git es un sistema de control de versiones. El repositorio es una colección de archivos, mientras que el git es una herramienta de control de versiones que permite rastrear los cambios en los archivos y compartir esos cambios con otros desarrolladores.

¿Cómo identificaste el comando necesario cuando la práctica no lo proporcionó?

Básicamente usé la vieja confiable: la documentación oficial de Git o el comando git --help. Si la cosa se ponía fea, buscaba en Google / Stack Overflow o le preguntaba a ChatGPT para ver qué comando solucionaba exactamente la acción que necesitaba hacer.

80. ¿Qué diferencia existe entre preparar un archivo para un commit y crear el commit?

Preparar un archivo (git add) es solo meter los cambios a la "zona de preparación" (Staging Area), o sea, elegir qué fotos vas a guardar en el álbum. Crear el commit (git commit) es tomar la foto definitiva e historia guardada en la base de datos de Git con su mensaje y autor.

81. ¿Cómo puedes comprobar en qué rama estás trabajando?

Escribiendo git branch en la terminal (la que tiene el asterisco * y color diferente es en la que estás) o ejecutando git status, que te dice justo en la primera línea en qué rama andas parado.

82. ¿Cómo puedes determinar qué archivos fueron modificados antes de registrarlos?

Con git status. Te muestra la lista de archivos en rojo (modificados pero no agregados) o en verde (ya en la Staging Area listos para el commit).

83. ¿Cómo puedes observar exactamente qué cambió dentro de un archivo?

Usando git diff. Te enseña línea por línea qué le borraste (en rojo con -) y qué le agregaste (en verde con +). Si ya subiste el archivo al staging, usas git diff --staged.

84. ¿Por qué debe reconstruirse .venv después de obtener un repositorio?

Porque el entorno virtual (.venv) contiene binarios y rutas absolutas que dependen del sistema operativo de cada máquina, por lo que nunca se sube a Git (va en el .gitignore). Al clonar o bajar el repo, tienes que volver a crearlo localmente e instalar las dependencias de cero.

85. ¿Qué relación existe entre requirements.txt y .gitignore?

El requirements.txt es la lista de compras con los nombres y versiones de los paquetes que necesita el proyecto. Por eso, agregas la carpeta del entorno virtual (.venv/) dentro del .gitignore para no subir gigas de librerías basura, dejando únicamente el requirements.txt para que otros sepan qué instalar.

86. ¿Por qué la colaboración se realiza desde una rama y no directamente desde main?

Para no romper el código que ya funciona en producción. En una rama trabajas tu parte seguro y sin molestar a los demás; si te equivocas no pasa nada. Ya que todo sirva y esté probado, se junta a main.

87. ¿Por qué una solicitud de cambios no requiere crear un Pull Request nuevo?

Porque el Pull Request (PR) está vinculado a la rama, no a un commit en específico. Si te piden correcciones, solo haces los cambios en tu computadora, haces commit y los subes (git push) a la misma rama; el PR abierto se actualiza en automático.

88. Después de realizar el merge en GitHub, ¿por qué todavía es necesario actualizar el repositorio local?

Porque el merge ocurrió en los servidores de GitHub (en la nube), no en tu computadora. Tu Git local no se entera mágicamente de lo que pasó allá arriba hasta que haces un git pull para traer los cambios integrados a tu máquina.