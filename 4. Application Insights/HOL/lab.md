#Application Insights
## �Qu� es Application Insights?
Es un servicio de an�lisis extensible que supervisa su aplicaci�n activa. Le ayuda a detectar y a diagnosticar problemas de rendimiento y a comprender qu� hacen los usuarios realmente con su aplicaci�n. Est� dise�ado para desarrolladores, para ayudarle a mejorar continuamente el rendimiento y la facilidad de uso de la aplicaci�n y que permite:
�	Supervisar el uso y rendimiento de las aplicaciones activas.
�	Supervisar aplicaciones web de ASP.NET o J2EE hospedadas en cualquier lugar: en Azure, en otros servicios en la nube o en sus propios servidores locales.
�	Supervisar aplicaciones de Android, iOS, OSX, Windows, etc.
�	Obtener alertas inmediatas en caso de problemas de rendimiento o disponibilidad.
�	Obtener telemetr�a para aplicaciones web existentes sin tener que volver a implementarlas.
�	Se puede usar con una amplia variedad de tipos de aplicaciones en ejecuci�n en dispositivos, servidores o equipos de escritorio.
�	Buscar registros de seguimiento y excepci�n para diagnosticar los errores.
�	Realizar un seguimiento de eventos, m�tricas, vistas de p�gina, usuarios, bloqueos, dependencias, contadores de rendimiento y tiempos de respuesta.
�	Funciona tanto con aplicaciones web como independientes en una amplia variedad de plataformas: .NET o J2EE, hospedadas localmente o en la nube; aplicaciones de dispositivos en Windows, iOS, Android, OSX y otras plataformas.

###Lo que haremos en este laboratorio:
Revisaremos la forma en que podemos integrar nuestras aplicaciones al servicio de Insights para poder realizar un seguimiento a las mismas
Requisitos:
�	Una suscripci�n activa a Azure
�	Visual Studio 2015
�	Visual Studio Code (Opcional)

##Tareas
- [Tarea 1: Revisar como adicionar Application Insights a su proyecto de Visual Studio.
- [Tarea 2: Crear una aplicaci�n web ASP.Net MVC con Application Insights.
- [Tarea 3: Implementar y publicar Contoso University.
- [Tarea 4: Crear una instancia de telemetr�a para asociarlo con la aplicaci�n.
- [Tarea 5:
- [Tarea 6:
- [Tarea 7:

###Tarea 1
Revisar como adicionar Application Insights a su proyecto de Visual Studio
Se puede adicionar Insights cuando se est� creando un proyecto nuevo, abriendo Visual Studio agregando un nuevo proyecto web y se le habilita la opci�n de Application Insights.
![Iniciando](Images/T1_1.png)
O Si se va a realizar desde un proyecto existente, desde el explorador de la soluci�n (Solution Explorer) se hace clic derecho sobre el proyecto y seleccionamos la opci�n agregar Application Insights.
 

Tarea 2
Crear una aplicaci�n web ASP.Net MVC con Application Insights 
Abrimos Visual Studio en donde agregaremos una nueva aplicaci�n web seleccionar la opci�n de Application Insights.
 
Al hacer clic en Ok seleccionamos la plantilla MVC con la autenticaci�n para cuentas de usuario individuales y hacemos clic en ok para que se implementen los elementos b�sicos de nuestra plantilla.
 
Lo que hicimos al Agregar Application Insights fue (que podr�a hacer manualmente en su lugar si lo prefiere):
�	Crear un recurso de Application Insights en el portal de Azure. Es donde ver� los datos. Recupera la clave de instrumentaci�n, que identifica el recurso.
�	Agregar el paquete NuGet del SDK web de Application Insights al proyecto. Para verlo en Visual Studio, haga clic con el bot�n secundario en el proyecto y elija Administrar paquetes de NuGet.
�	Colocar la clave de instrumentaci�n en ApplicationInsights.config.
 
Ejecuci�n del proyecto
Ejecute la aplicaci�n con F5 y pru�bela. Abra varias p�ginas para generar telemetr�a.
 
En Visual Studio, aparecer� un recuento de los eventos que se han enviado.

Al abrir el explorador de soluciones, haremos clic derecho sobre el proyecto para ver las opciones que se encuentran asociadas con Application Insights
 
Abra el recurso de Application Insights, esto abrir� el portal de Azure.
 

Haga clic sobre cualquiera de las gr�ficas para ver los detalles de la misma.
 
Abra B�squeda para investigar solicitudes individuales y sus eventos asociados.
 
�No hay datos?
�	Aseg�rese de que est� viendo lo correcto. Inicie sesi�n en el portal de Azure, haga clic en "Examinar" >, "Application Insights" y, a continuaci�n, seleccione la aplicaci�n.
�	Use la aplicaci�n y abra varias p�ginas para generar telemetr�a.
�	Abra la hoja Buscar para ver los eventos individuales. A veces, los eventos tardan un poco en llegar a trav�s de la canalizaci�n de m�tricas.
�	Espere unos segundos y haga clic en Actualizar.



Tarea 3
Implementar y publicar Contoso University
Dir�jase al directorio "aplicaciones" de este repositorio y copie la aplicaci�n ContosoUniversity en su directorio de trabajo.
Tambi�n lo pueden descargar desde https://github.com/qjuanp/nc-azure-ai/tree/example-nc
Abra la aplicaci�n desde Visual Studio 2015.
 
Compile la aplicaci�n y verifique que la compilaci�n este correcta antes de realizar el paso de publicaci�n.
   ***
    ***
Publicar la aplicaci�n en Azure
Realice la publicaci�n de la aplicaci�n ContosoUniversity a su cuenta en Azure desde Visual Studio 2015
 
Cree un nuevo perfil de publicaci�n para Web Apps
 
Recuerde que debe iniciar sesi�n con la cuenta que tenga asociada para acceder a su subscripci�n de Windows Azure
 
Defina para la publicaci�n de su Web App
�	El Service Plan al que va a pertenecer la Web App (Plan Free por defecto)
�	El Resource Group que va a contener la Web App
�	La Regi�n de Azure en donde se van a publicar la Web App
�	Crear una nueva Base de Datos para los datos de la aplicaci�n ContosoUniversity
 

 
Active la migraci�n para que se puedan desplegar los datos de la base de datos de ContosoUniversity
 
Y Publique la Web App
 
Verifique las diferentes secciones de la aplicaci�n e ingrese datos adicionales en cada una de ellas
�	Instructores
�	Departamentos
�	Clases
�	Estudiantes
�	Acerca de
�	etc...
 
Tarea 4
Crear una instancia de telemetr�a para asociarlo con la aplicaci�n.
La aplicaci�n tiene algunos problemas de performance y errores dif�cilmente visibles, para lo cual haremos el seguimiento correspondiente utilizando Application Insights.
En el portal Preview de Azure vamos a revisar Application Insights nos debe mostrar la aplicaci�n de Contoso University que agregamos.
 
Ahora crearemos un nuevo Application Insight, el que asociaremos a nuestra aplicaci�n.
 	


Ahora desde Visual Studio 2015 vamos a integrar nuestra aplicaci�n con Application Insights Desde el explorador de la soluci�n hacemos clic derecho sobre el proyecto y Add Application Insights Telemetry (Agregar Telemetr�a).
 
Si lo solicita, es necesario reingresar las credenciales de acceso a su cuenta de azure.
 
Se abrir� la ventana desde donde seleccionaremos la opci�n que creamos. Y hacemos clic en agregar (Add)
  
Ya que se agregaron las librer�as asociadas con Insights, debemos publicar nuevamente la aplicaci�n para guardar los cambios realizados.
 

Lo que permitir� revisar la aplicaci�n
 
Ac� podemos revisar la informaci�n que arroja la telemetr�a a nivel general, por ejemplo revisemos cuales son las p�ginas que mostraron error al ingresar a ellas.
Tarea 5
Agregar informaci�n de excepciones a Application Insights
Crearemos un filtro para integrarnos r�pida y f�cilmente con nuestro proyecto hecho en MVC5 para lo cual crearemos la clase ContosoHandleErrorAttribute que heredar� de la clase HandleErrorAttribute del framework de Insight.
using System;
using System.Web.Mvc;
using Microsoft.ApplicationInsights;

namespace ContosoUniversity.Common
{
    [AttributeUsage(AttributeTargets.Class | AttributeTargets.Method, Inherited = true, AllowMultiple = true)]
    public class ContosoHandleErrorAttribute : HandleErrorAttribute
    {
        public override void OnException(ExceptionContext filterContext)
        {
            if (filterContext != null && filterContext.HttpContext != null && filterContext.Exception != null)
            {
                //If customError is Off, then AI HTTPModule will report the exception
                if (filterContext.HttpContext.IsCustomErrorEnabled)
                {
                    // Note: A single instance of telemetry client is sufficient to track multiple telemetry items.
                    var telemetry = new TelemetryClient();
                    telemetry.TrackException(filterContext.Exception);
                }
            }
            base.OnException(filterContext);
        }
    }
}
Luego seleccionamos nuestro archivo Global.asax y registramos el filtro de manera global en el FilterConfig de nuestro c�digo al final de la clase.
// ...
public static void RegisterGlobalFilters(GlobalFilterCollection filters)
{
    filters.Add(new ContosoHandleErrorAttribute());
}
// ...
De nuevo publicamos la aplicaci�n para que queden en el servidor los cambios.
 
Observemos cuales son las excepciones que presenta en el momento de navegar por el sitio.
 
Tarea 6
Conteo de eventos
Podemos utilizar Application Insigths para medir eventos espec�ficos dentro de nuestra aplicaci�n. Algo como los nuevos estudiantes e instructores que se registran pueden verse con una m�trica en el tablero de Application Insigths
Contar cuantos estudiantes se registran en la aplicaci�n En la clase Controllers\StudentController.cs agergar al m�todo Crear (POST):
public ActionResult Create([Bind(Include = "LastName, FirstMidName, EnrollmentDate")]Student student)
{
    // .. 
        if (ModelState.IsValid)
        {
            db.Students.Add(student);
            db.SaveChanges();

            //----------------------------------------------
            TelemetryClient telemetry = new TelemetryClient();
            telemetry.TrackEvent("NewStudent");
            //----------------------------------------------

            return RedirectToAction("Index");
        }
    //..
}
Contar cuantos instructores se registran en la aplicaci�n En la clase Controllers\InstructorController.cs agregar al m�todo Crear (POST):
public ActionResult Create([Bind(Include = "LastName,FirstMidName,HireDate,OfficeAssignment")]Instructor instructor, string[] selectedCourses)
{
    //..
    if (ModelState.IsValid)
    {
        db.Instructors.Add(instructor);
        db.SaveChanges();

        //----------------------------------------------
        TelemetryClient telemetry = new TelemetryClient();
        telemetry.TrackEvent("NewInstructor");
        //----------------------------------------------

        return RedirectToAction("Index");
    }
    //..
}
�Qu� informaci�n nos arroja Application Insight sobre ContosoUniversity?
�Cuantos usuarios hemos podido crear en nuestra aplicaci�n?
Tarea 7
Test de disponibilidad y capacidad de respuesta del web site
Despu�s de haber implementado la aplicaci�n web, configuraremos pruebas web para supervisar su disponibilidad y capacidad de respuesta. Application Insights enviar� solicitudes web a intervalos regulares desde puntos de todo el mundo y puede alertarle si la aplicaci�n responde lentamente o no responde en absoluto.
Puede configurar pruebas web para cualquier punto de conexi�n HTTP o HTTPS que sea accesible desde la red p�blica de Internet.
Existen dos tipos de prueba web:
�	Prueba de ping de la direcci�n URL: una prueba sencilla que se puede crear en el portal de Azure.
�	Prueba web de varios pasos: que se crea en Visual Studio Ultimate o Visual Studio Enterprise y se carga en el portal.
Ahora vamos a seleccionar el recurso con el que hemos trabajado para las tareas anteriores:
 
Si no aparece el icono que nos permite manejar la disponibilidad es necesario agregarlo.
 

Hacemos clic sobre la opci�n Add tiles
 

Lo que nos despliega un men� al lado derecho Tile Gallery.
 
Seleccionamos la opci�n Availability arrastr�ndola al men� de nuestro recurso y hacemos clic en la opci�n Done sobre �ste men�.
 

Configuraci�n de la prueba Ping
Hacemos clic sobre el icono que acabamos de implementar (Availability) y hacemos clic en la opci�n Add web test (Crear una prueba web)
 

Llenamos la informaci�n para crear nuestra prueba: Nombre, tipo de test, la url (cargada por defecto), frecuencia, locaciones de carga, criterio, alertas.
Aunque lo vamos a dejar como est� cargado por defecto, es bueno revisar las opciones que nos presenta cada uno de los elementos.
Hacemos clic en crear para que quede listo nuestro test.
 
Para tener en cuenta:
�	La direcci�n URL debe ser visible desde la red p�blica de Internet. Puede incluir una cadena de consulta, as� por ejemplo se puede ejercitar un poco la base de datos. Si la direcci�n URL se resuelve en una redirecci�n, la seguiremos, con un m�ximo de 10 redirecciones.
�	Analizar solicitudes dependientes: im�genes, scripts, archivos de estilo y otros recursos de la p�gina se solicitan como parte de la prueba. La prueba da error si todos estos recursos no se pueden descargar correctamente dentro del tiempo de espera de la prueba entera.
�	Habilitar reintentos: cuando la prueba da error, se reintenta tras un corto intervalo. Se notifica un error �nicamente si los tres intentos sucesivos producen un error. Las sucesivas pruebas se realizan seg�n la frecuencia habitual de la prueba. El reintento se suspende temporalmente hasta que uno se complete correctamente. Esta regla se aplica independientemente en cada ubicaci�n de la prueba. (Se recomienda esta configuraci�n. Como media, cerca del 80 % de los errores desaparecen al reintentar).
�	Frecuencia de prueba: establece la frecuencia con que se ejecuta la prueba desde cada ubicaci�n de prueba. Con una frecuencia de cinco minutos y cinco ubicaciones de prueba, el sitio se prueba cada minuto por t�rmino medio.
�	Las ubicaciones de prueba son los lugares desde donde nuestros servidores env�an solicitudes web a la direcci�n URL. Elija m�s de una de tal forma que pueda distinguir los problemas del sitio web a partir de los problemas de red. Puede seleccionar hasta 16 ubicaciones.
Criterios de �xito:
�	Tiempo de espera de prueba: reduzca este valor para recibir una alerta sobre las respuestas lentas. La prueba se considera un error si no se han recibido respuestas de su sitio dentro de este per�odo. Si seleccion� Analizar solicitudes dependientes, todas las im�genes, archivos de estilo, scripts y otros recursos dependientes se deben haber recibido durante este per�odo.
�	Respuesta HTTP: el c�digo de estado devuelto que se considera correcto. 200 es el c�digo que indica que se ha devuelto una p�gina web normal.
�	Coincidencia de contenido: una cadena, como "Bienvenido". Realizaremos una prueba que tenga lugar en todas las respuestas. Debe ser una cadena sin formato, sin caracteres comod�n. No se olvide que si el contenido cambia, es posible que tenga que actualizarla.
�	De forma predeterminada, las alertas se le env�an cuando hay errores en tres ubicaciones durante cinco minutos. Es probable que un error en una ubicaci�n sea un problema de red y no un problema con su sitio. No obstante, puede cambiar el umbral a m�s o menos sensible, y tambi�n puede cambiar las personas a quienes se deben enviar los correos electr�nicos.
Al seleccionar el test que acabamos de crear podemos ver el avance del mismo.
 
Agregue m�s pruebas. Por ejemplo, adem�s de probar la p�gina principal, puede asegurarse de que la base de datos se est� ejecutando probando la URL con una b�squeda.

Despu�s de uno o dos minutos, haga clic en Actualizar en la hoja de pruebas de disponibilidad o web. (No se actualiza autom�ticamente).
 
Al ubicarse sobre cualquiera de los puntos podr� ver la informaci�n relacionada.
 

