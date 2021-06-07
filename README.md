# IS-HT03
Se trata de una aplicación en Spring Boot que implementa la dependencia:jsonwebtoken para generar un token JWT al llamar a un servicio REST.

El token debe tener un tiempo de vida dinámico.
El tiempo de vida debe ser configurable desde el archivo de configuración application.yml en segundos.
La llave secreta debe ser configurable desde el archivo de configuración application.yml
Verifique la llave secreta antes de generar el token JWT tomando en cuenta las recomendaciones de OWASP Top 10 para el riesgo Broken Authentication. En caso de que la llave secreta proporcionada no cumpla con los requisitos mínimos deberá lanzar una excepción personalizada con el mensaje "La llave secreta no cumple con los requisitos mínimos de seguridad.".
El endpoint debe ser: POST http://<server>:<port>/auth
El request debe llevar un body con el usuario y contraseña (ambos encriptados). El usuario debe poder ser desencriptado pero la contraseña no. 
Al momento de crear el token debe imprimir en la consola un mensaje incluyendo un saludo al usuario por medio de su nombre de usuario, por ejemplo: "Bienvenido Nombre!!!"
Esto no es una implementación real de un servicio de autenticación por lo que no utilizá el usuario y contraseña.
  
  Parte2
  
Aplicacion Spring Boot que implementa las  operaciones aritméticas básicas (suma, resta, multiplicación y división)
Cada controlador debe verificar la presencia del token en el Authorization header. Si el token no está presente en la cabecera entonces el usuario no podrá utilizar dicho servicio. Utilice la anotación Java @RequestHeader
Si el token JWT está presente en la cabecera entonces el controlador debe decodificarlo y veficar que aun esté vigente. Si el token ya caducó entonces deberá lanzarse una "excepción personalizada" con el mensaje "El token caducó hace n segundos." en donde "n" es el tiempo en segundos transcurrido desde que caducó el token hasta el momento en que el mensaje es generado por el servicio. Si el token es inválido debe lanzarse una "excepción personalizada" con el mensaje "El token proporcionado es inválido.".
La llave secreta debe ser configurable desde el archivo de configuración application.yml; Esta será necesaria para desencriptar el token JWT;
Para esta aplicación no se configurará tiempo de vida en el archivo de configuración application.yml ya que el token debe traer su propio tiempo de expiración.
Los endpoints deben ser:
GET http://<server>:<port>/math/add?a=1&b=2
GET http://<server>:<port>/math/sub?a=1&b=2
GET http://<server>:<port>/math/mul?a=1&b=2
GET http://<server>:<port>/math/div?a=1&b=2
