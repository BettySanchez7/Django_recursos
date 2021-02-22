## **ENVIO DE EMAILS CON DJANGO**

NECESITAMOS UNA LIBRERIA CORE.MAIL
* Editar el archivo de settings y agregar los siguientes parámetros: (revisar documentación)
```python

EMAIL_BACKEND = "django.core.mail.backends.smtp.EmailBackend"
EMAIL_HOST= "smtp.gmail.com"
EMAIL_USE_TLS = True
EMAIL_PORT = 587
EMAIL_HOST_USER = "correo desde donde se enviaran los correos al cliente"
EMAIL_HOST_PASSWORD = "tu_contraseña"

```
* Comprobar desde consola el funcionamiento correcto:
```python
>>> from django.core.mail import send_mail
>>> send_mail("Prueba asunto","Hola esto es el mensaje","remitente@gmail.com",["destinatario@gmail.com"], fail_silently=False)
1
>>> 

```

* Crear un formulario sencillo para envío de correos:
1. Template (contacto.html) :
```python
<html>
<head>
	<title>Formulario de Contacto</title>
</head>
<body>
	<h1>Contactanos</h1>
	<form  action="/contacto/"  method="POST">  {% csrf_token %}
		<p>Asunto: <input  type="text"  name="asunto"></p>
		<p>Email: <input  type="text"  name="email"</p>
		<p>Mensaje: <textarea  name="mensaje"  rows="15"  cols="45"></textarea></p>
	<input  type="submit"  value="Enviar">
	</form>
</body>
</html>
```
2. View
```python
def  contacto(request):
	if request.method =="POST":
		subject = request.POST["asunto"]
		message = request.POST["mensaje"] + " " + request.POST["email"]
		email_from = settings.EMAIL_HOST_USER
		recipient_list = ["ejemplo@gmail.com"] #a donde quiero que lleguen los correos
		send_mail(subject, message, email_from, recipient_list)
		return render(request, "gracias.html")
	return render(request, "contacto.html")
```
3. URLS
```python
from django.contrib import admin
from django.urls import path
from gestionPedidos import views
urlpatterns = [
path('admin/', admin.site.urls),
path('busqueda_productos/', views.busqueda_productos),
path('buscar/', views.buscar),
path('contacto/', views.contacto)  <----------------------
]
```

Para más detalles: 
[Tutorial código facilito](https://codigofacilito.com/articulos/envio-correos-django)

[Documentación oficial- emails](https://docs.djangoproject.com/en/3.1/topics/email/)
