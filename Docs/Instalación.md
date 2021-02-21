**

## INSTALACIÓN DJANGO

**

Requisitos:
1. Instalación de Python (no olvidar agregar al path para usarlo en cualquier lugar)
[Instalación python](https://github.com/BettySanchez7/Django_recursos/blob/main/Images/Screenshot_2.png)
3. Instalar Django  
	`pip install django`
	Se puede hacer de manera global en tu computadora o en un entorno virtual. Si se hace de manera global instalarlo directamente.
	De manera virtual crea el entorno virtual e instálalo ahí:
	**¿Qué es un entorno virtual?**: En ocasiones, necesitamos tener varios entornos de trabajo distintos, con distintas versiones del intérprete, distintas librerías, etc. Una de las soluciones más comunes es usar varios ordenadores o varias máquinas virtuales, cada una con una instalación diferente. Pero Python nos provee de una herramienta simple y útil para facilitarnos ese trabajo, sin necesidad de recurrir a soluciones más complicadas. Esta herramienta es «virtualenv».
Virtualenv es un programa que permite crear entornos virtuales de Python. Un entorno virtual consta de un intérprete (podemos elegir la versión concreta) acompañado de todos los módulos que necesitemos instalar. Se pueden tener varios entornos distintos, instalando en cada uno los módulos que necesitemos, sin que unos entornos afecten a los otros.
* Instalar virtualenv `pip install virtualenv`
* Crea la carpeta donde se encontrará el proyecto `mkdir nombre_directorio`
* Entra a la carpeta creada y crea el entorno virtual con el siguiente comando: `virtualenv nombre_entorno`
* Entra a la carpeta scripts que se creo para activar el entorno: `cd nombre_entorno/Scripts`
	Ejecuta el script activa : `./activate`
* Dentro de esa carpeta(nombre_directorio) instalar los requerimientos necesarios comenzando con django `pip install django`

