# Introducción

¡Gracias por elegir el Mini libro de Asp.NET Core! Escribí este pequeño libro para ayudar a desarrolladores y gente interesada en programación web a aprender Asp.NET Core 2.0, un nuevo framework para construir aplicaciones web y APIs.

Thanks for picking up the Little ASP.NET Core Book! I wrote this short book to help developers and people interested in web programming learn about ASP.NET Core 2.0, a new framework for building web applications and APIs.

Mini libro de Asp.NET Core está estructurado como un tutorial. Construirás un gestor de tareas de principio a fin, y aprenderás:

* Conceptos básicos del patrón MVC \(Modelo-Vista-Controlador\)
* Cómo el código de front-end \(HTML, CSS, JavaScript\) trabaja junto al código backend
* Qué es inyección de dependencias y por qué es útil
* Cómo leer y escribir datos en una base de datos
* Cómo añadir login, registro y seguridad
* Cómo desplegar la aplicación en la nube

No te preocupes, no necesitas saber nada de Asp.Net Core \(o algo de lo citado anteriormente\) para empezar.

## Antes de empezar

The code for the finished version of the application you'll build is available on GitHub \([https://www.github.com/nbarbettini/little-aspnetcore-todo](https://www.github.com/nbarbettini/little-aspnetcore-todo)\). Feel free to download it if you want to compare as you write your own code.

The book itself is updated frequently with bug fixes and new content. If you're reading a PDF, e-book, or print version, check the official website \([littleasp.net/book](http://www.littleasp.net/book)\) to see if there's an updated version available. Check the very last page of the book for version information and a changelog.

El código para la versión final de la aplicación que construirás está disponible en GitHub \([https://www.github.com/nbarbettini/little-aspnetcore-todo\](https://www.github.com/nbarbettini/little-aspnetcore-todo%29\). Puedes descargarlo ahora si deseas compararlo mientras escribes tu propio código.

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

There are a lot of great web frameworks to choose from already: Node/Express, Spring, Ruby on Rails, Django, Laravel, and many more. What advantages does ASP.NET Core have?

* **Speed.** ASP.NET Core is fast. Because .NET code is compiled, it executes much faster than code in interpreted languages like JavaScript or Ruby. ASP.NET Core is also optimized for multithreading and asynchronous tasks. It's common to see a 5-10x speed improvement over code written in Node.js.

* **Ecosystem.** ASP.NET Core may be new, but .NET has been around for a long time. There are thousands of packages available on NuGet \(the .NET package manager; think npm, Ruby gems, or Maven\). There are already packages available for JSON deserialization, database connectors, PDF generation, or almost anything else you can think of.

* **Security.** The team at Microsoft takes security seriously, and ASP.NET Core is built to be secure from the ground up. It handles things like sanitizing input data and preventing cross-site request forgery \(XSRF\) automatically, so you don't have to. You also get the benefit of static typing with the .NET compiler, which is like having a very paranoid linter turned on at all times. This makes it harder to do something you didn't intend with a variable or chunk of data.

Hay un montón frameworks web geniales que podrías elegir ya mismo: Node / Express, Spring, Ruby on Rails, Django, Laravel, y muchos más. ¿Qué ventajas tiene ASP.NET Core?

* **Velocidad**. ASP.NET Core es rápido. Debido a que el código .NET se compila, se ejecuta mucho más rápido que el código en lenguajes interpretados como JavaScript o Ruby. ASP.NET Core también está optimizado para multi-hilo \(multi-threading\) y tareas asíncronas que permiten aprovechar de manera eficiente el rendimiento de la máquina. Digamos que es común ver una mejora de velocidad de 5 a 10 veces superior al código escrito con Node.js.

* **Ecosistema**. ASP.NET Core puede ser nuevo, pero .NET ha existido desde hace mucho tiempo. Hay miles de paquetes disponibles en NuGet \(el gestor de paquetes .NET, similar a npm, Ruby gems o Maven\). Hay paquetes disponibles para deserialización JSON, conectores de bases de datos, generación de PDF, o casi cualquier otra cosa que te puedas imaginar.

* **Seguridad**. El equipo de Microsoft se toma la seguridad muy en serio y ASP.NET Core está diseñado para ser seguro desde sus cimientos. Maneja y filtra los datos de entrada y previene la falsificación de solicitudes cruzadas \(XSRF\) de forma automática, por lo que no es necesario hacerlo tú mismo. También obtienes el beneficio de escritura estática de código mediante el compilador .NET, que es como tener un chivato muy paranoico activado en todo momento que te avisa de cualquier error sin necesidad de compilar. Esto previene hacer mal las cosas en una variable o una porción de código.

## .NET Core and .NET Standard

Throughout this book, you'll be learning about ASP.NET Core \(the web framework\). I'll occasionally mention the .NET runtime \(the supporting library that runs .NET code\).

You may also hear about .NET Core and .NET Standard. The naming gets confusing, so here's a simple explanation:

**.NET Standard** is a platform-agnostic interface that defines what features and APIs are available in .NET. .NET Standard doesn't represent any actual code or functionality, just the API definition. There are different "versions" or levels of .NET Standard that reflect how many APIs are available \(or how wide the API surface area is\). For example, .NET Standard 2.0 has more APIs available than .NET Standard 1.5, which has more APIs than .NET Standard 1.0.

**.NET Core** is the .NET runtime that can be installed on Windows, Mac, or Linux. It implements the APIs defined in the .NET Standard interface with the appropriate platform-specific code on each operating system. This is what you'll install on your own machine to build and run ASP.NET Core applications.

And just for good measure, **.NET Framework** is a different implementation of .NET Standard that is Windows-only. This was the only .NET runtime until .NET Core came along and opened .NET up to Mac and Linux. ASP.NET Core can also run on Windows-only .NET Framework, but I won't touch on this too much.

If you're confused by all this naming, no worries! We'll get to some real code in a bit.

## A note to ASP.NET 4 developers

If you haven't used a previous version of ASP.NET, skip ahead to the next chapter!

ASP.NET Core is a complete ground-up rewrite of ASP.NET, with a focus on modernizing the framework and finally decoupling it from System.Web, IIS, and Windows. If you remember all the OWIN/Katana stuff from ASP.NET 4, you're already halfway there: the Katana project became ASP.NET 5 which was ultimately renamed to ASP.NET Core.

Because of the Katana legacy, the `Startup` class is front and center, and there's no more `Application_Start` or `Global.asax`. The entire pipeline is driven by middleware, and there's no longer a split between MVC and Web API: controllers can simply return views, status codes, or data. Dependency injection comes baked in, so you don't need to install and configure a container like StructureMap or Ninject if you don't want to. And the entire framework has been optimized for speed and runtime efficiency.

Alright, enough introduction. Let's dive in to ASP.NET Core!

