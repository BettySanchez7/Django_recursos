## **¿QUÉ ES UN TEMPLATE EN DJANGO?**

Las templates son lo que propiamente veremos de nuestra pagina web y es en esta parte donde se hace uso de los conocimientos de css, html y js.

Las platillas son archivos con extensión .html, HTML es el código que será interpretado por la página web, es recomendable tener una carpeta junto con todas estas, que comúnmente se le conoce como `templates`.

** Imprimir variables o usar condicionales dentro de html **
``` html
{% if  temas%}
	{% for  tema  in  temas%}
		<li>{{tema}}</li>
	{% endfor %}
{%else%}

```
** HERENCIA E INRUSTACIÓN DE PLATILLAS **
Django pertmite reutilizar partes del código de html en diferentes páginas de un sitio web, esto facilita y reduce el código.

Para la herencia es parecido a la herencia en programación se crea algo llamado plantilla base que en este caso sería la plantilla padre y de la que las demás van a heredar.

Ejemplo de plantilla base.html :
``` html
<html>
<head>
	<title>
		{% block  title%}  {%endblock%}
	</title>
</head>
<body>
	<h1> EJEMPLO </h1>
	<h3>Aprendiendo Django</h3>
	{% block  content %}
	{% endblock %}
	<p>Fin de plantilla </p>
</body>
</hmtl>
```
{% block  title%}  {%endblock%}  Indican que en esta parte se puede agregar cualquier otra cosa en las plantillas hijas.

Ejemplo de plantilla hija:
``` html
{% extends  "base.html" %}
{% block  title %} 
	Plantilla hija 1
{% endblock %}
{% block  content %}
	<p>Estamos a día: {{fecha}}</p>
{% endblock %}
```
