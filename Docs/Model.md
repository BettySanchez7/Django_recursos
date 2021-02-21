## **¿QUÉ ES UN MODELO EN DJANGO?**
Un modelo en Django es un tipo especial de objeto donde se contendrá toda la información sobre los datos, es decir que en esta parte estará la base de datos. Una base de datos es una colección de datos. Es un lugar en el cual almacenarás la información sobre usuarios, artículos, etc. 
En otras palabras aquí vamos a poner todas nuestras tablas de la base de datos peero !sin lenguaje sql!. ¿Entonces cómo?

Antes que nada se necesita crear una aplicación, crear una App en un proyecto de django permite  modular, se crea una carpeta con todos los archivos necesarios dentro de esta se encontrará un archivo llamado  `models.py` 
		
		from django.db import models
		
		class  Clientes(models.Model):
			nombre = models.CharField(max_length=30)
			direccion = models.CharField(max_length=50)
			email = models.EmailField(blank=True, null=True)
			tfno = models.CharField(max_length=7)
		class  Articulos(models.Model):
			nombre = models.CharField(max_length=30)
			seccion = models.CharField(max_length=20)
			precio = models.IntegerField()
		def  __str__(self):
			return  'El nombre es %s la seccion es %s y el precio es %s' % (self.nombre, self.seccion, self.precio)
