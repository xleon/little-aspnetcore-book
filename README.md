# Introducción

¡Gracias por elegir el Mini libro de Asp.NET Core! Escribí este pequeño libro para ayudar a desarrolladores y gente interesada en programación web a aprender Asp.NET Core 2.0, un nuevo framework para construir aplicaciones web y APIs.

Mini libro de Asp.NET Core está estructurado como un tutorial. Construirás un gestor de tareas de principio a fin, y aprenderás:

* Conceptos básicos del patrón MVC \(Modelo-Vista-Controlador\)
* Cómo el código de front-end \(HTML, CSS, JavaScript\) trabaja junto al código backend
* Qué es inyección de dependencias y por qué es útil
* Cómo leer y escribir datos en una base de datos
* Cómo añadir login, registro y seguridad
* Cómo desplegar la aplicación en la nube

No te preocupes, no necesitas saber nada de Asp.Net Core \(o algo de lo citado anteriormente\) para empezar.

## Antes de empezar

El código para la versión final de la aplicación que construirás está disponible en [GitHub](https://www.github.com/nbarbettini/little-aspnetcore-todo\). Puedes descargarlo ahora si deseas compararlo mientras escribes tu propio código.

El libro en sí se actualiza con frecuencia con correcciones de errores y nuevos contenidos. Si estás leyendo un PDF, un libro electrónico o una versión impresa, consulta el sitio web oficial \(littleasp.net/book\) para ver si hay una versión actualizada disponible. Comprueba la última página del libro para obtener información sobre la versión y un registro de cambios.

## Para quién es este libro

Si es nuevo en la programación, este libro te introducirá los patrones y conceptos utilizados para crear aplicaciones web modernas. ¡Aprenderás cómo construir una aplicación web \(y cómo encajan todas las piezas\) construyendo algo desde cero! Mientras que este mini libro no será capaz de cubrir absolutamente todo lo que necesitas saber acerca de la programación, te dará un punto de partida para que puedas aprender más temas avanzados.

Si ya codificas en un lenguaje backend como Node, Python, Ruby, Go o Java, notarás muchas ideas conocidas como MVC, plantillas para vistas e inyección de dependencias. El código estará en C\#, pero no se verá muy diferente de lo que ya sabes.

¡Si eres un desarrollador de ASP.NET MVC, te sentirás como en casa! ASP.NET Core añade nuevas herramientas y reutiliza \(y simplifica\) las cosas que ya sabes. Voy a señalar algunas de las diferencias a continuación.

No importa tu experiencia previa con la programación web, este libro le enseñará todo lo que necesitas para crear una aplicación web sencilla y útil en ASP.NET Core. Aprenderás cómo crear funcionalidad utilizando código backend y frontend, cómo interactuar con una base de datos y cómo probar e implementar la aplicación en el mundo real.

## ¿Qué es ASP.NET Core?

ASP.NET Core es un framework web creado por Microsoft para el desarrollo de aplicaciones web, APIs y microservicios. Utiliza patrones comunes como MVC \(Modelo-Vista-Controlador\), inyección de dependencias y una canalización de solicitudes mediante middleware. Es de código abierto bajo la licencia Apache 2.0, lo que significa que el código fuente está disponible libremente, y se anima a la comunidad a que aporte correcciones de errores y nuevas características.

ASP.NET Core funciona sobre el motor de ejecución .NET de Microsoft \(.NET runtime\), similar a la máquina virtual de Java \(Java Virtual Machine o JVM\) o el intérprete Ruby. Puedes escribir aplicaciones ASP.NET Core en varios idiomas \(C\#, Visual Basic y F\#\). C\# es la opción más popular, y es lo que voy a utilizar en este libro. Como es multi-plataforma, puedes crear y ejecutar aplicaciones ASP.NET Core en Windows, Mac y Linux.

## ¿Por qué necesitamos un nuevo framework web?

Hay un montón frameworks web geniales que podrías elegir ya mismo: Node / Express, Spring, Ruby on Rails, Django, Laravel, y muchos más. ¿Qué ventajas tiene ASP.NET Core?

* **Velocidad**. ASP.NET Core es rápido. Debido a que el código .NET se compila, se ejecuta mucho más rápido que el código en lenguajes interpretados como JavaScript o Ruby. ASP.NET Core también está optimizado para multi-hilo \(multi-threading\) y tareas asíncronas que permiten aprovechar de manera eficiente el rendimiento de la máquina. Digamos que es común ver una mejora de velocidad de 5 a 10 veces superior al código escrito con Node.js.

* **Ecosistema**. ASP.NET Core puede ser nuevo, pero .NET ha existido desde hace mucho tiempo. Hay miles de paquetes disponibles en NuGet \(el gestor de paquetes .NET, similar a npm, Ruby gems o Maven\). Hay paquetes disponibles para deserialización JSON, conectores de bases de datos, generación de PDF, o casi cualquier otra cosa que te puedas imaginar.

* **Seguridad**. El equipo de Microsoft se toma la seguridad muy en serio y ASP.NET Core está diseñado para ser seguro desde sus cimientos. Es capaz de manejar y filtrar los datos de entrada automáticamente y previene la falsificación de solicitudes cruzadas \(XSRF\) de forma automática, por lo que no es necesario hacerlo tú mismo. También obtienes el beneficio de escritura estática de código mediante el compilador .NET, que es como tener un chivato muy paranoico activado en todo momento que te avisa de cualquier error sin necesidad de compilar. Esto ayuda muchísimo a evitar errores en tu código.

## .NET Core y .NET Standard

A través de este libro, aprenderás sobre ASP.NET Core \(el framework web\). De vez en cuando mencionaré el motor de ejecución de .NET \(la librería de soporte que ejecuta código .NET\).

También verás menciones sobre .NET Core y .NET Standard. Ambos se pueden confundir, así que va una explicación sencilla:

**.NET Standard** es una interfaz independiente de la plataforma que define qué características y APIs están disponibles en .NET. No representa ningún código o funcionalidad real, sino la definición de la API. Existen diferentes "versiones" o niveles de .NET Standard que reflejan cuántas APIs están disponibles \(o cuán amplia es la superficie de la API\). Por ejemplo, .NET Standard 2.0 tiene más APIs disponibles que .NET Standard 1.5, que a su vez tiene más APIs que .NET Standard 1.0.

**.NET Core** es el motor de ejecución multi-plataforma de .NET que se puede instalar en Windows, Mac o Linux. Implementa las APIs definidas en la interfaz .NET Standard con el código específico de plataforma apropiado en cada sistema operativo. Esto es lo que instalará en tu propia máquina para crear y ejecutar aplicaciones ASP.NET Core.

Y sólo por tenerlo en cuenta, **.NET Framework** es una implementación diferente de .NET Standard que solo vale para Windows \(no es multi-plataforma\). Éste fue el único motor de ejecución .NET existente hasta que .NET Core apareció. Fue entones cuando .NET abrió sus puertas a Mac y Linux. ASP.NET Core también puede ejecutarse en Windows .NET Framework, pero no voy a tocar ese tema demasiado.

Si te confunden todos estos nombres, ¡no te preocupes! Vamos a ver ejemplos de código real en breve.

## Aclaración para desarrolladores de ASP.NET 4

> Si no has utilizado versiones anteriores de ASP.NET, puedes pasar directamente al siguiente capítulo.

ASP.NET Core es una re-escritura completa de ASP.NET, enfocándose en la modernización del framework y desvinculándolo de System.Web, IIS \(Internet Information Server\) y Windows. Si recuerdas todas las cosas de OWIN / Katana de ASP.NET 4, ya estás a mitad de camino: el proyecto Katana se convirtió en ASP.NET 5, que finalmente se renombró a ASP.NET Core.

Debido al legado de Katana, la clase `Startup` sigue siendo el punto de entrada, y ya no se usa `Application_Start` o `Global.asax`. La totalidad del flujo de entrada y salida es conducido por middleware, y ya no hay una división entre MVC y API Web: los controladores pueden simplemente devolver vistas, códigos de estado o datos, indistintamente. La inyección de dependencias ahora viene de fábrica, así que no te hace falta instalar y configurar un contenedor de terceros como StructureMap, Unity o Ninject. Y todo el framework ha sido optimizado para velocidad y eficiencia en tiempo de ejecución.

Muy bien, hasta aquí llegó la introducción. ¡Vamos a bucear en ASP.NET Core!

