**

## PRIMER PROYECTO CON DJANGO

**


Si lo haces de manera global primero entra a la carpeta donde crearas el proyecto, de preferencia crear una carpeta donde se tendrán todos los proyectos de Django.


Si lo haces en un entorno virtual primero activarlo `cd nombre_entorno/Scripts`
Ejecutar script para activar:
    ./activate


Dentro de la carpeta donde se almacenara el proyecto iniciar el proyecto:

    $django-admin startproject <NombreProyecto>

¡LISTO! Se crearan los archivos necesarios para comenzar a trabajar con una estructura como la siguiente:

 	Proyecto1
	    ├───manage.py
	    └───Proyecto1
			settings.py	
		        urls.py
		        wsgi.py
		        asgi.py
		        views.py
		        __init__.py
		     
        
 Es necesario hacer varias configuraciones y saber que significa cada archivo pero por ahora para probar que todo este correto, Dentro de la carpeta Proyecto1:
 Iniciar base de datos:
	
	$python manage.py migrate
	
Iniciar servidor:

	$python manage.py runserver
![IMAGEN 1](https://github.com/BettySanchez7/Django_recursos/blob/main/Images/runserver.png)
![IMAGEN2](https://github.com/BettySanchez7/Django_recursos/blob/main/Images/runserver2.png)

