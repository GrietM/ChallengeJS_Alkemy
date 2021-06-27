# ChallengeJS_Alkemy --> AccountANT
Repositorio unificado que incluye como submodulos a los repositorios de FrontEnd y BackEnd desarrollados para el ChallengeJS de Alkemy

----------------------------------------------------------------------------------------------------
Se desarrolló  una aplicación para administración de presupuesto personal según lo requerido en el enunciado. 

La misma recibe el nombre de AccountANT dado que está desarrollada en inglés, sirve para el manejo de la 
contabilidad personal y está basada en componentes de ANT Design.

----------------------------------------------------------------------------------------------------

Tecnologías utilizadas:

MonogoDB --> La base de datos es de tipo NoSQL y se desarrolló con MongoDB.

Node.js + Express -->  La API se desarrolló en Node.jS + Express.

React.js +AntDesign -->  El cliente se desarrolló en React.js utilizando componentes de AntDesign.

Axios -->  Las peticiones entre el cliente y la base de datos se manejan con axios.

Postman -->  Para simular el cliente y realizar pruebas de controladores y rutas.

------------------------------------------------------------------------------------------------------

PÁGINAS

	Login: 
	
		Creación de usuarios:Para crear un usuario nuevo se deben ingresar todos los datos requeridos en el formulario. Al darle "submit", se crea automáticmanete un nombre de usuario 
		basado en los datos ingresados en los campos 'First Name' y 'Last Name'. El mismo será informado al usuario a través de un mensaje de éxito al terminar de crear el usuario y 
		tiene el formato de LASTNAME-FirstName (APELLIDOENMAYUSCULAS-nombre).
		
		Acceso: Se creó una página para el login y/o creación de nuevos usuarios. Al iniciar sesión se otroga un token al usuario de manera de poder acceder al resto de las páginas. 
		Si el usuario no está loggeado, al intentar acceder al resto de las páginas de la aplicación recibirá un mensaje de error y será automáticamente redirigido al Login.
		Una vez iniciada sesión el nombre de usuario se muestra en el navegador en lugar del botón del login. Además aparece el botón de logout.
		
	Home:
	
		Balance: En la parte superior de la página se presenta un recuadro donde se muestran los ingresos totales, egresos totales y el balance total.
		Nueva operación: Un botón permite ingresar nuevas operaciones. Al presionar el mismo se abre un formulario en que deben ingresarse los datos 
		solicitados para crear una operación ya sea de tipo ingreso o egreso.
		
		Ulitmos movimientos: Luego se presenta una tabla donde se muestran las últimas 10 operaciones ingresadas en orden desde más reciente a más antigua, 
		indistintamente de que se trate de un ingreso o un egreso. Es importante aclarar que se muestran las operaciones ordenadas en el orden que fueron cargadas 
		y no ordenadas cronológicamnete según la fecha que figura en el campo "Date"
	
	Expenses:
		
		Tabla: Se presenta una tabla con paginacion que permite consultar todas las operaciones de tipo 'Egreso' que se hayan registrado. Además permite eliminar y editar
		las mismas. (Por requerimiento del enunciado, no se permite modificar el tipo de operacion)
	
	Incomes:
	
		Tabla: Se presenta una tabla con paginacion que permite consultar todas las operaciones de tipo 'Ingreso' que se hayan registrado. Además permite eliminar y editar
		las mismas. (Por requerimiento del enunciado, no se permite modificar el tipo de operacion)
	
	LogOut:
	
		El botón de Logout aparece en la página cuando un usuario inicia sesión. Antes que eso no existe. Una vez presionado borra el Token del localhost de manera 
		de quitar los permisos de acceso al resto de las páginas, muestra un mensaje de logout exitoso y redirige automáticmante a la página de Login.

------------------------------------------------------------------------------------------------------
OTROS REQUISITOS:

Responsive --> Se modifica la visualización del menu de navegación para pantallas de ancho menor a 920px. Se cambia la barra de navegación por un botón de menú
que permite acceder a un menu lateral de tipo "Drawer"

GitHub--> Se crea un repositorio de GitHub para presentar el trabajo. Debido a que la aplicación se fue desarrollando de forma paralela en otros dos repositorios dedicados
(uno para el FrontEnd y otro para el BackEnd), se adjuntan los mimsos como 'submodulos' a este repositorio final de manera de no perder el historial de commits. 

Rutas--> El diseño de las rutas se pensó con el formato '/api/users' y '/api/operations'

Idioma --> Tanto el código como la visaulización final se desarrollaron en idioma inglés de manera de no estar mezclando idiomas en la creación de mensajes, botones y demás
textos que se muestran en la aplicación.

Otros --> 
		- Se incluyen mensajes de alerta, errores y éxito en acciones de interaccion con el cliente para que el sitio sea mas interactivo 
		y la navegación más amigable y comprensible. 
		- Se incluyen validaciones en todos los formularios tanto en el front como en el router que permite el acceso a los controladores.
		- Se creó un nombre para la aplicaci+on y se diseñó un logo para la misma.

------------------------------------------------------------------------------------------------------

BONUS:

Se empezó a desarollar el BONUS referido al login y autenticación de usuarios:
		- Se crearon modelo, rutas y controladores para el manejo de usuarios (GET,PUT, POST y DELETE ). 
		- Se agregó un formulario de registro de usuarios nuevos, un formualrio de login.
		- Se verifican los valores ingresados para el login y en caso de ser correctos se asigna un token al usuario que se almacena en el localhost y 
			en base al cual se otrogan o quitan permisos para navegar por el resto de las páginas de la aplicación.

Faltó tiempo para asociar las operaciones registradas a cada usuario (en este momento cualquier usuario que se logee accede a todas la soperaciones que 
hayan registradas en la base de datos. No se distingue quien las creo ni quien tiene permisos para verlas, editarlas o eliminarlas)

Los métodos PUT y DELETE solo se probaron y utilizaron a través de Postman. Desde el FrontEnd no se tiene acceso a los mismos.

------------------------------------------------------------------------------------------------------

Mejoras a implementar:

- Formato de la fecha para que no se muestren horas, minutos y seg en el renderizado de las tablas.
- Asociar operaciones a usuarios
- Chequear la expiracion del token --> Había implementado un método que chequeaba la validez del token cada vez que se hacía una petición de axios. Esto lo
	hacía mediante una variable llamada 'decoded' en al que almacenaba el resultado del método verify de 'jsonwebtoken' que indica si el mismo es válido. En caso 
	de que estuviera expirado hacía un RemoveItem(Token) para eliminar el token del LocalHost y un GoToMain() para dirigir automáticamente a la páfina de login. Sin 
	embargo estaba manjeando mal algo en la conexión con el backend y decidí borrarlo porque se rompía la aplicación.
- Warnings de React referidos a la asignación de 'keys' únicas para cada componente hijo...

------------------------------------------------------------------------------------------------------

Bugs:

Al Clickear en la página 'Home' sin haber hecho un Login, el cartel de error que pide iniciar sesión para acceder a esa información se muestra dos veces!

------------------------------------------------------------------------------------------------------

DEPENDENCIAS UTILIZADAS

  	-bcrypt			
		
   	-express
		
	  -joi
		
   	-express-joi-validation
		
    -jsonwebtoken
		
   	-express-jwt
		
	  -mongoose
		
	  -nodemon
		
	  -axios
		
	  -react-router-dom	
