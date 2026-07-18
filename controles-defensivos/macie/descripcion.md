# Control defensivo: Amazon Macie

Crear trabajo en Analizar depósitos públicos

![Evidencia img_097.png](screenshots/img_097.png)

Creamos un amazon macie que detecta información confidencial en los buckets de S3 mediante un trabajo de detección de datos.

Seleccionar buckets

![Evidencia img_098.png](screenshots/img_098.png)

seleccionamos manualmente los buckets dev-blog-awsgoat-bucket-[ACCOUNT_ID_REDACTED] y production-blog-awsgoat-bucket-[ACCOUNT_ID_REDACTED] para su análisis, excluyendo el bucket do-not-delete-awsgoat-state-files

Seleccion de identificadores

![Evidencia img_099.png](screenshots/img_099.png)

Seleccionamos todas las informaciones confidenciales con categoria credencial con el fin de que el trabajo detecte específicamente credenciales y claves privadas expuestas en los buckets seleccionados.

Ver que objetos son vulnerables

![Evidencia img_100.png](screenshots/img_100.png)

En hallazgos podemos ver que hay 8 activos, donde si seleccionamos uno cualquiera, nos va a arrojar toda su informacion

Correcion de permisos mal configurados

![Evidencia img_101.png](screenshots/img_101.png)

los objetos vulnerables se encuentran en el bucket dev. Por lo tanto, sustituyamos production por dev y añadamos la carga útil después de la URL. Veamos si podemos acceder al archivo .pem.

el archivo bob.pem se ha descargado. Esto significa que cualquier persona en internet puede acceder a él y obtener acceso a la instancia EC2.

Eliminar acceso de lectura publico

![Evidencia img_102.png](screenshots/img_102.png)

Para intentar remediar la descarga automatica, eliminamos le lectura que estaba publica

Declaracion de politica

![Evidencia img_103.png](screenshots/img_103.png)

Editamos la politica en la parte del sid, porque tenia un asterisco, lo que queria decir que cualquiera podia entrar y hacer la descarga

Entrar nuevamente a la URL para descargar el bob.pem

![Evidencia img_104.png](screenshots/img_104.png)

Ya no nos deja descargar el pem, lo que quiere decir, que nuestra remediacion surtio efecto
