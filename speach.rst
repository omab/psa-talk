Speach
======

Diapositiva 1 (Django Social Auth)
----------------------------------

Propósito:
    Solucionar el problema del autenticado y autorización mediante el uso de
    redes sociales que soportan los protocolos OAuth1, OAuth2 y OpenId.

    Surge como resultado de horas de frustración al intentar utilizar otras
    soluciones disponibles.

Números:
    Nace el 8 de Noviembre de 2010 y muere el 5 de Octubre de 2013 con un total
    de 1605 commits, 9614 líneas de código, 165 aportes, 751 issues cerrados,
    674 forks, 1990 stars y 116 watchers.
    
Features:
    * Django ORM y Mongoengine
    * Registro de datos básicos del usuario al momento de registrarse
    * Múltiple cuentas sociales asociadas a un único usuario
    * Modelo de usuario configurable
    * Pipeline extensible utilizado al momento del autenticado o asociación
    * Variedad de sitios sociales soportados:
        - Google (OpenID, OAuth, OAuth2)
        - Yahoo
        - Twitter
        - Facebook
        - DISQUS 
        - LiveJournal 
        - Orkut 
        - Linkedin 
        - Foursquare 
        - GitHub 
        - Dropbox 
        - Flickr 
        - Vkontakte 
        - MSN Live Connect 
        - Skyrock 
        - Yahoo 
        - Evernote 
        - Mail.ru 
        - Odnoklassniki 
        - Mixcloud 
        - BitBucket 
        - Douban 
        - Fitbit 
        - Instagram 
        - Twilio
        - Trello 
        - Weibo 
        - Yandex 
        - Shopify 
        - StockTwits 
        - Stackoverflow 
        - Fedora 
        - Exacttarget HubExchange
        - Appsfuel 

Diapositiva 2 (Django Social Auth is dead)
------------------------------------------

El 29 de Agosto de 2013 se marca la librería como deprecated para favorecer el
desarrollo y aceptación de python-social-auth. El día 5 de Octubre de 2013 se
realiza el último commit en al código. Los últimos cambios implican un
refactoreo general del código para hacer DSA depender de PSA.

Por qué la nueva lib? Python-social-auth es una generalización de DSA, busca
ser una solución para un problema común independiente al framework que se
utilice. La idea había surgido hace tiempo al ya que era el siguiente paso
lógico para la aplicación, sumado con el interes de empezar a usar Flask
o Pyramid acelero el nacimiento de PSA.


Diapositiva 3 (Python Social Auth)
----------------------------------

Propósito:
    Realizar lo mismo que django-social-auth pero siendo una solución
    multi-framework.

    La idea surge como el comentario de un amigo luego de unas cervezas, y la
    implementación se vuelve realidad cuando empiezo a usar otros frameworks
    aparte de Django.

Números:
    Nace el 12 de Diciembre de 2012, 598 commits, 11953 líneas de código, 19
    aportes, 57 issues cerrados, 54 forks, 314 stars y 25 watchers.

Features:
    * Múltiple framewors (Django, Flask, Pyramid, Webpy ...)
    * Registro de datos básicos del usuario al momento de registrarse
    * Múltiple cuentas sociales asociadas a un único usuario
    * Modelo de usuario configurable
    * Pipeline extensible utilizado al momento del autenticado o asociación
    * Pipeline extensible utilizado al momento de la desconexión de una cuenta
    * Variedad de sitios sociales soportados:
        - Amazon
        - Angel
        - AOL
        - Appsfuel
        - Behance
        - BelgiumEIDOpenId
        - Bitbucket
        - Box
        - Dailymotion
        - Disqus
        - Douban
        - Dropbox
        - Evernote
        - Exacttarget
        - Facebook
        - Fedora
        - Fitbit
        - Flickr
        - Foursquare
        - Gae
        - Github
        - Google
        - Instagram
        - Jawbone
        - Linkedin
        - Livejournal
        - Live
        - Mailru
        - Mendeley
        - Mixcloud
        - Odnoklassniki
        - Orkut
        - Persona
        - Podio
        - Rdio
        - Readability
        - Reddit
        - Shopify
        - Skyrock
        - Soundcloud
        - Stackoverflow
        - Steam
        - Stocktwits
        - Stripe
        - Suse
        - Thisismyjam
        - Trello
        - Tripit
        - Tumblr
        - Twilio
        - Twitter
        - vkontakte 
        - Weibo
        - Xing
        - Yahoo
        - Yammer
        - Yandex
    * Login con username y email (sin contraseña pero esta se puede verificar
      en un pipeline)


Diapositiva 5 (Detrás de cámaras)
---------------------------------

Por detrás de lo que se ve en el video, ocurre un flujo de requests de un lado
al otro, tal como se muestra en el diagrama.

El punto de origen es el usuario clickeando en el link de login, en ese momento
la aplicación redirecciona a la url de login correspondiente al provider
seleccionado.

Una vez que el usuario autentifica (y autoriza) en el provider, este nos trae
de regreso a la URL de "complete", y por último social auth hace otra
redirección a la URL post login definida en las settings.


Diapositiva 6 (Tutorial)
------------------------

El primer paso es instalarlo.

Lo siguente es configurar nuestra aplicacion para que use PSA.
  * Agregar la aplicacion a las installed apps.
  * Agregar los backends de autenticacion a utilizar. Estos "backends" son las
    diferentes estrategias que PSA utiliza.
  * Se registra la aplicacion en facebook, para obtener acceso a las llamadas
    de la api del sitio.
  * Al crear la aplicacion, obtenemos una application key y application secret
    las cuales son requeridas en el settings.py.
  * Opcionalmente se define el storage, ya que tiene siempre un storage
    definido por defecto para cada framework. Esta es la capa de almacenamiento
    de los datos para la autenticacion.
  * Incluir las urls.
    - Login
    - Complete
    - Disconect
  * Definir los nombres de las urls que participan en el proceso.
  * Y por ultimo en nuestro template de login, agregamos el link que
    desencadena el proceso.

Los dos principales conceptos con los que nos debemos quedar son Storage y 
Backend, estas son las principales interfaces de la libreria.
