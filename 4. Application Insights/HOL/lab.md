#Application Insights
## �Qu� es Application Insights?
Es un servicio de an�lisis extensible que supervisa su aplicaci�n activa. Le ayuda a detectar y a diagnosticar problemas de rendimiento y a comprender qu� hacen los usuarios realmente con su aplicaci�n. Est� dise�ado para desarrolladores, para ayudarle a mejorar continuamente el rendimiento y la facilidad de uso de la aplicaci�n y que permite:
- Supervisar el uso y rendimiento de las aplicaciones activas.
- Supervisar aplicaciones web de ASP.NET o J2EE hospedadas en cualquier lugar: en Azure, en otros servicios en la nube o en sus propios servidores locales.
- Supervisar aplicaciones de Android, iOS, OSX, Windows, etc.
- Obtener alertas inmediatas en caso de problemas de rendimiento o disponibilidad.
- Obtener telemetr�a para aplicaciones web existentes sin tener que volver a implementarlas.
- Se puede usar con una amplia variedad de tipos de aplicaciones en ejecuci�n en dispositivos, servidores o equipos de escritorio.
- Buscar registros de seguimiento y excepci�n para diagnosticar los errores.
- Realizar un seguimiento de eventos, m�tricas, vistas de p�gina, usuarios, bloqueos, dependencias, contadores de rendimiento y tiempos de respuesta.
- Funciona tanto con aplicaciones web como independientes en una amplia variedad de plataformas: .NET o J2EE, hospedadas localmente o en la nube; aplicaciones de dispositivos en Windows, iOS, Android, OSX y otras plataformas.

###Lo que haremos en este laboratorio:
Revisaremos la forma en que podemos integrar nuestras aplicaciones al servicio de Insights para poder realizar un seguimiento a las mismas
Requisitos:
- Una suscripci�n activa a Azure
- Visual Studio 2015
- Visual Studio Code (Opcional)

##Tareas
- [Tarea 1 - Revisar como adicionar Application Insights a su proyecto de Visual Studio.](#tarea-1)
- [Tarea 2 - Crear una aplicaci�n web ASP.Net MVC con Application Insights.](#tarea-2)
- [Tarea 3 - Implementar y publicar Contoso University.](#tarea-3)
- [Tarea 4 - Crear una instancia de telemetr�a para asociarlo con la aplicaci�n.](#tarea-4)
- [Tarea 5 - Agregar informaci�n de excepciones a Application Insights.] (#tarea-5)
- [Tarea 6 - Conteo de eventos.] (#tarea-6)
- [Tarea 7 - Test de disponibilidad y capacidad de respuesta del web site.] (#tarea-7)
- [Tarea 8 - A manera de repaso.] (#tarea-8)

###Tarea 1
####Revisar como adicionar Application Insights a su proyecto de Visual Studio
Se puede adicionar Insights cuando se est� creando un proyecto nuevo, abriendo Visual Studio agregando un nuevo proyecto web y se le habilita la opci�n de Application Insights.

![Nuevo Proyecto](Images/T1_1.png)

O Si se va a realizar desde un proyecto existente, desde el explorador de la soluci�n (Solution Explorer) se hace clic derecho sobre el proyecto y seleccionamos la opci�n agregar Application Insights.

![Proyecto existente](Images/T1_2.png)

###Tarea 2
####Crear una aplicaci�n web ASP.Net MVC con Application Insights 
Abrimos Visual Studio en donde agregaremos una nueva aplicaci�n web seleccionar la opci�n de Application Insights.

![Proyecto](Images/T2_1.png)

Al hacer clic en Ok seleccionamos la plantilla MVC con la autenticaci�n para cuentas de usuario individuales y hacemos clic en ok para que se implementen los elementos b�sicos de nuestra plantilla.

![Iniciando](Images/T2_2.png)

Lo que hicimos al Agregar Application Insights fue (que podr�a hacer manualmente en su lugar si lo prefiere):
- Crear un recurso de Application Insights en el portal de Azure. Es donde ver� los datos. Recupera la clave de instrumentaci�n, que identifica el recurso.
- Agregar el paquete NuGet del SDK web de Application Insights al proyecto. Para verlo en Visual Studio, haga clic con el bot�n secundario en el proyecto y elija Administrar paquetes de NuGet.
- Colocar la clave de instrumentaci�n en ApplicationInsights.config.

![Iniciando](Images/T2_3.png)

Ejecuci�n del proyecto

Ejecute la aplicaci�n con F5 y pru�bela. Abra varias p�ginas para generar telemetr�a.

![Iniciando](Images/T2_4.png)

En Visual Studio, aparecer� un recuento de los eventos que se han enviado.

Al abrir el explorador de soluciones, haremos clic derecho sobre el proyecto para ver las opciones que se encuentran asociadas con Application Insights

![Iniciando](Images/T2_5.png)

Abra el recurso de Application Insights, esto abrir� el portal de Azure.

![Iniciando](Images/T2_6.png)

Haga clic sobre cualquiera de las gr�ficas para ver los detalles de la misma.

![Iniciando](Images/T2_7.png)

Abra B�squeda para investigar solicitudes individuales y sus eventos asociados.

![Iniciando](Images/T2_8.png)

###�No hay datos?
- Aseg�rese de que est� viendo lo correcto. Inicie sesi�n en el portal de Azure, haga clic en "Examinar" >, "Application Insights" y, a continuaci�n, seleccione la aplicaci�n.
- Use la aplicaci�n y abra varias p�ginas para generar telemetr�a.
- Abra la hoja Buscar para ver los eventos individuales. A veces, los eventos tardan un poco en llegar a trav�s de la canalizaci�n de m�tricas.
- Espere unos segundos y haga clic en Actualizar.

###Tarea 3
####Implementar y publicar Contoso University

Puede descargar el proyecto desde https://github.com/qjuanp/nc-azure-ai/tree/example-nc

Abra la aplicaci�n con Visual Studio 2015.

![Application Insights](Images/T3_1.png)

Compile la aplicaci�n y verifique que la compilaci�n este correcta antes de realizar el paso de publicaci�n.

![Application Insights](Images/T3_2.png)

Publicar la aplicaci�n en Azure
Realice la publicaci�n de la aplicaci�n ContosoUniversity a su cuenta en Azure desde Visual Studio 2015

![Application Insights](Images/T3_5.png)

Cree un nuevo perfil de publicaci�n para Web Apps

![Application Insights](Images/T3_6.png)

Recuerde que debe iniciar sesi�n con la cuenta que tenga asociada para acceder a su subscripci�n de Windows Azure

![Application Insights](Images/T3_7.png)

Defina para la publicaci�n de su Web App
- El **Service Plan** al que va a pertenecer la Web App (Plan Free por defecto)
- El **Resource Group** que va a contener la Web App
- La **Regi�n de Azure** en donde se van a publicar la Web App
- Crear una **nueva Base de Datos** para los datos de la aplicaci�n ContosoUniversity

![Application Insights](Images/T3_8.png)

![Application Insights](Images/T3_9.png)
 
Active la migraci�n para que se puedan desplegar los datos de la base de datos de ContosoUniversity

![Application Insights](Images/T3_10.png)

Y Publique la Web App

![Application Insights](Images/T3_11.png)

Verifique las diferentes secciones de la aplicaci�n e ingrese datos adicionales en cada una de ellas
- Instructores
- Departamentos
- Clases
- Estudiantes
- Acerca de

![Application Insights](Images/T3_12.png)
 
###Tarea 4
####Crear una instancia de telemetr�a para asociarlo con la aplicaci�n.

La aplicaci�n tiene algunos problemas de performance y errores dif�cilmente visibles, para lo cual haremos el seguimiento correspondiente utilizando Application Insights.
En el portal Preview de Azure vamos a revisar Application Insights nos debe mostrar la aplicaci�n de Contoso University que agregamos.

![Application Insights](Images/T4_01.png)
 
Ahora crearemos un nuevo recurso de **Application Insight**, el que asociaremos a nuestra aplicaci�n.
 	
![Application Insights](Images/T4_02.png)

Desde Visual Studio 2015 vamos a integrar nuestra aplicaci�n con Application Insights Desde el explorador de la soluci�n hacemos clic derecho sobre el proyecto y Add Application Insights Telemetry (Agregar Telemetr�a).

![Application Insights](Images/T4_03.png)

Si lo solicita, es necesario reingresar las credenciales de acceso a su cuenta de azure.

![Application Insights](Images/T4_04.png)

Se abrir� la ventana desde donde seleccionaremos la opci�n que creamos. Y hacemos clic en agregar (Add)

![Application Insights](Images/T4_05.png)
 
Ya que se agregaron las librer�as asociadas con Insights, debemos publicar nuevamente la aplicaci�n para guardar los cambios realizados.

![Application Insights](Images/T4_06.png)

Lo que permitir� revisar la aplicaci�n delde Azure Application Insights en donde podemos revisar la informaci�n que arroja la telemetr�a a nivel general, por ejemplo revisemos cuales son las p�ginas que mostraron error al ingresar a ellas.

![Application Insights](Images/T4_07.png)


###Tarea 5
####Agregar informaci�n de excepciones a Application Insights

Crearemos un filtro para integrarnos r�pida y f�cilmente con nuestro proyecto hecho en MVC5 para lo cual crearemos la clase ContosoHandleErrorAttribute que heredar� de la clase HandleErrorAttribute del framework de Insight.

```C#
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
```

Luego seleccionamos nuestro archivo Global.asax y registramos el filtro de manera global en el FilterConfig de nuestro c�digo al final de la clase.

```C#
// ...
public static void RegisterGlobalFilters(GlobalFilterCollection filters)
{
    filters.Add(new ContosoHandleErrorAttribute());
}
// ...
```

De nuevo publicamos la aplicaci�n para que queden en el servidor los cambios.

![Application Insights](Images/T5_01.png)
 
Observemos cuales son las excepciones que presenta en el momento de navegar por el sitio.

![Application Insights](Images/T5_02.png)

Es un esquema inicial para detectar el filtrado de informaci�n asociado con nuestro seguimiento de la aplicaci�n.

###Tarea 6
####Conteo de eventos

Podemos utilizar Application Insigths para medir eventos espec�ficos dentro de nuestra aplicaci�n. Algo como los nuevos estudiantes e instructores que se registran pueden verse con una m�trica en el tablero de Application Insigths
Contar cuantos estudiantes se registran en la aplicaci�n En la clase Controllers\StudentController.cs agergar al m�todo Crear (POST):

```C#
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
```

Contar cuantos instructores se registran en la aplicaci�n En la clase Controllers\InstructorController.cs agregar al m�todo Crear (POST):

```C#
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
```

- �Qu� informaci�n nos arroja Application Insight sobre ContosoUniversity?
- �Cuantos usuarios hemos podido crear en nuestra aplicaci�n?

###Tarea 7
####Test de disponibilidad y capacidad de respuesta del web site

Despu�s de haber implementado la aplicaci�n web, configuraremos pruebas web para supervisar su disponibilidad y capacidad de respuesta. Application Insights enviar� solicitudes web a intervalos regulares desde puntos de todo el mundo y puede alertarle si la aplicaci�n responde lentamente o no responde en absoluto.
Puede configurar pruebas web para cualquier punto de conexi�n HTTP o HTTPS que sea accesible desde la red p�blica de Internet.

Existen dos tipos de prueba web:
- Prueba de ping de la direcci�n URL: una prueba sencilla que se puede crear en el portal de Azure.
- Prueba web de varios pasos: que se crea en Visual Studio Ultimate o Visual Studio Enterprise y se carga en el portal.

Ahora vamos a seleccionar el recurso con el que hemos trabajado para las tareas anteriores:

![Application Insights](Images/T7_01.png)

Si no aparece el icono que nos permite manejar la disponibilidad es necesario agregarlo.

![Application Insights](Images/T7_02.png)

Hacemos clic sobre la opci�n Add tiles

![Application Insights](Images/T7_03.png) 

Lo que nos despliega un men� al lado derecho Tile Gallery.

>![Application Insights](Images/T7_04.png)
 
Seleccionamos la opci�n Availability arrastr�ndola al men� de nuestro recurso y hacemos clic en la opci�n Done sobre �ste men�.

![Application Insights](Images/T7_05.png)

####Configuraci�n de la prueba Ping
Hacemos clic sobre el icono que acabamos de implementar (Availability) y hacemos clic en la opci�n Add web test (Crear una prueba web)

![Application Insights](Images/T7_06.png)

Llenamos la informaci�n para crear nuestra prueba: Nombre, tipo de test, la url (cargada por defecto), frecuencia, locaciones de carga, criterio, alertas.
Aunque lo vamos a dejar como est� cargado por defecto, es bueno revisar las opciones que nos presenta cada uno de los elementos.
Hacemos clic en crear para que quede listo nuestro test.

![Application Insights](Images/T7_07.png)
 
#####Para tener en cuenta:
- **La direcci�n URL** debe ser visible desde la red p�blica de Internet. Puede incluir una cadena de consulta, as� por ejemplo se puede ejercitar un poco la base de datos. Si la direcci�n URL se resuelve en una redirecci�n, la seguiremos, con un m�ximo de 10 redirecciones.
- **Analizar solicitudes dependientes**: im�genes, scripts, archivos de estilo y otros recursos de la p�gina se solicitan como parte de la prueba. La prueba da error si todos estos recursos no se pueden descargar correctamente dentro del tiempo de espera de la prueba entera.
- **Habilitar reintentos**: cuando la prueba da error, se reintenta tras un corto intervalo. Se notifica un error �nicamente si los tres intentos sucesivos producen un error. Las sucesivas pruebas se realizan seg�n la frecuencia habitual de la prueba. El reintento se suspende temporalmente hasta que uno se complete correctamente. Esta regla se aplica independientemente en cada ubicaci�n de la prueba. (Se recomienda esta configuraci�n. Como media, cerca del 80 % de los errores desaparecen al reintentar).
- **Frecuencia de prueba**: establece la frecuencia con que se ejecuta la prueba desde cada ubicaci�n de prueba. Con una frecuencia de cinco minutos y cinco ubicaciones de prueba, el sitio se prueba cada minuto por t�rmino medio.
- **Las ubicaciones de prueba** son los lugares desde donde nuestros servidores env�an solicitudes web a la direcci�n URL. Elija m�s de una de tal forma que pueda distinguir los problemas del sitio web a partir de los problemas de red. Puede seleccionar hasta 16 ubicaciones.

#####Criterios de �xito:
- Tiempo de espera de prueba: reduzca este valor para recibir una alerta sobre las respuestas lentas. La prueba se considera un error si no se han recibido respuestas de su sitio dentro de este per�odo. Si seleccion� Analizar solicitudes dependientes, todas las im�genes, archivos de estilo, scripts y otros recursos dependientes se deben haber recibido durante este per�odo.
- Respuesta HTTP: el c�digo de estado devuelto que se considera correcto. 200 es el c�digo que indica que se ha devuelto una p�gina web normal.
- Coincidencia de contenido: una cadena, como "Bienvenido". Realizaremos una prueba que tenga lugar en todas las respuestas. Debe ser una cadena sin formato, sin caracteres comod�n. No se olvide que si el contenido cambia, es posible que tenga que actualizarla.
- De forma predeterminada, las alertas se le env�an cuando hay errores en tres ubicaciones durante cinco minutos. Es probable que un error en una ubicaci�n sea un problema de red y no un problema con su sitio. No obstante, puede cambiar el umbral a m�s o menos sensible, y tambi�n puede cambiar las personas a quienes se deben enviar los correos electr�nicos.

Al seleccionar el test que acabamos de crear podemos ver el avance del mismo.

![Application Insights](Images/T7_08.png)
 
Agregue m�s pruebas. Por ejemplo, adem�s de probar la p�gina principal, puede asegurarse de que la base de datos se est� ejecutando probando la URL con una b�squeda.

Despu�s de uno o dos minutos, haga clic en Actualizar en la hoja de pruebas de disponibilidad o web. (No se actualiza autom�ticamente).

![Application Insights](Images/T7_09.png)
 
Al ubicarse sobre cualquiera de los puntos podr� ver la informaci�n relacionada.
 
![Application Insights](Images/T7_10.png)

###Tarea 8
####A manera de repaso.

Abramos nuestro ambiente de Azure Insights y seleccionemos el elemento que hemos venido trabajando asociado con Contoso University, luego hagamos clic en Settings para que se desplieguen las diferentes opciones.

![Application Insights](Images/T8_01.png)

All� podemos ver las diferentes opciones agrupadas por las caracter�sticas generales.

![Application Insights](Images/T8_011.png)

- Quick Start: Nos ofrece una ser�e de gu�as para un inicio rapido, a manera de referencia y autoaprendizaje.
- Investigate (Investigar): Podemos ver el movimiento y los datos relacionados con la navegaci�n, Las fallas, las escepciones, el uso y los eventos asociados con la aplicaci�n a la que le estamos haciendo el seguimiento.
- Properties (Propiedades): Se pueden revisar las propiedades, la disponibilidad, los test y las dem�s caracter�sticas de nuestro servicio Application Insight.
- Resourse Management (Manejo de recursos): Nos permite manejar los usuarios, los roles y las etiquetas asociados a nuestro elemento Application Insight seleccionado.

#####Agregando un Chart

Aprovechemos que estamos ah� y hagamos clic sobre el Setting Browser (Navegaci�n o p�ginas) y en la ventana que se despliega hagamos clic sobre **Add Chart**.

![Application Insights](Images/T8_02.png)

Modifiquemos algunas de las caracter�sticas del chart que estamos creando y veamos como se refleja esto dentro de nuestro sistema de charts.

![Application Insights](Images/T8_03.png)


###V�nculos

Azure Application Insights es una gran herramienta para poder hacer seguimiento en tiempo real a nuestras aplicaciones, para mayor profundidad de este tema recomendamos la siguiente documentaci�n:

- �Qu� es Application Insights?: https://azure.microsoft.com/es-es/documentation/articles/app-insights-overview/
- Detecci�n, evaluaci�n de errores y diagn�stico con Application Insights: https://azure.microsoft.com/es-es/documentation/articles/app-insights-detect-triage-diagnose/
- An�lisis de uso con Application Insights: https://azure.microsoft.com/es-es/documentation/articles/app-insights-overview-usage/
- Vistas de datos de Application Insights en Power BI: https://azure.microsoft.com/es-es/documentation/articles/app-insights-export-power-bi/
- exportaci�n a SQL desde Application Insights mediante An�lisis de transmisiones: https://azure.microsoft.com/es-es/documentation/articles/app-insights-code-sample-export-sql-stream-analytics/

Entre otros varios al respecto.









