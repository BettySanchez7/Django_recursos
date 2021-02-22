## **¿QUÉ ES UN MODELO EN DJANGO?**
Un modelo en Django es un tipo especial de objeto donde se contendrá toda la información sobre los datos, es decir que en esta parte estará la base de datos. Una base de datos es una colección de datos. Es un lugar en el cual almacenarás la información sobre usuarios, artículos, etc. 
En otras palabras aquí vamos a poner todas nuestras tablas de la base de datos peero !sin lenguaje sql!. ¿Entonces cómo?

**Creación de una aplicación con Django**

Antes que nada se necesita crear una aplicación, crear una App en un proyecto de Django permite  modular y tener un mejor control, para crear una aplicación:

    $python manage.py startapp nombre_app

**Registrar aplicación**

Dentro del archivo `settings.py` se debe registrar registra la aplicación para hacer uso de ella:
```python
# Application definition
INSTALLED_APPS = [
'django.contrib.admin',
'django.contrib.auth',
'django.contrib.contenttypes',
'django.contrib.sessions',
'django.contrib.messages',
'django.contrib.staticfiles',
'nombre_app',  <---------------------------------------
]
```
Se creara una lista de archivos donde se encontrará `models.py`
que nos servirá para gestionar la base de datos.

Es como si nuestras clases fueran las tablas de nuestra base de datos hablando de una base de datos relacional, en el siguiente ejemplo tendremos dos tablas: Clientes y Artículos, cada una con sus respectivas propiedades:
```python

from django.db import models
		
class  Clientes(models.Model):
	nombre = models.CharField(max_length=30)
	direccion = models.CharField(max_length=50)
	email = models.EmailField(blank=True, null=True)
	telefono = models.CharField(max_length=7)
class  Articulos(models.Model):
	nombre = models.CharField(max_length=30)
	seccion = models.CharField(max_length=20)
	precio = models.IntegerField()
	def  __str__(self):
		return  'El nombre es %s la seccion es %s y el precio es %s' % (self.nombre, self.seccion, self.precio)

```
Ahora que tengo mis modelos necesito llenar mi base de datos con ellos:
* `python manage.py makemigrations`
* `python manage.py sqlmigrate nombre_app num_migration` con esta instruccion creo el codigo sql que se le insertara a mi base de datos
* `python manage.py migrate` insertando tablas en la base de datos

![img](https://github.com/BettySanchez7/Django_recursos/blob/main/Images/app.png)
¡LISTO!
