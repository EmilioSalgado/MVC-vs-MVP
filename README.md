#MVC vs MVP

###Model View Controller (MVC)
Model: Recibe la entrada del controlador y decide qué datos se necesitan para cumplir con la solicitud planteada por el controlador. El modelo es también capaz de hacer transacciones con bases de datos u otro almacenamiento persistente, según sea necesario. Una vez que se recopila la información requerida, se informa a la vista (a través del controlador) acerca de los nuevos datos de eventos de recaudación apropiadas.

View: Alberga todos los controles de interfaz de usuario que necesita el usuario final para interactuar con la aplicación. Su función es controlar los gestos de los usuarios finales y pasarlo al controlador para su manipulación posterior.

Controller: Extensión o un asistente personal para la vista, todos los eventos que se originaron a partir de la vista son manejados por el controlador. El controlador también informará al Modelo si algún acontecimiento sucedió en la vista y pueden ser necesarios algunos datos nuevos.

```javascript
public Controller(IViewBase view)
    {
        _view = view;
        _model.ModelChanged += new EventHandler(_model_ModelChanged);    
    }
```
![alt text](https://github.com/EmilioSalgado/MVC-vs-MVP/blob/master/MVC.gif "MVC")

###Model View Presenter (MVP)
Model: Puede ser pensado como la interfaz a los datos. Cualquier parte del programa que necesita algunos datos para trabajar debe ir a través de la interfaz o funciones definidas por el desarrollador que está manteniendo la parte del modelo. Por lo general, el modelo contiene todas las rutinas de validación de los datos presentados por el usuario final.

View: vista, como su nombre lo indica, es la parte en la que interactúa el usuario final. El desarrollo de esta parte puede ser delegada a un diseñador especializado.

Presenter: Actúa como intermediario para hacer posible el desacoplamiento. Toda la lógica de negocio requerido para responder a un evento de usuario está escrito dentro de la capa Presentador. Normalmente la vista sólo tiene el controlador de eventos y la lógica para llamar a las funciones de presentador apropiadas, para ayudar a la persona que trabaja en el fin de concentrarse en el diseño de la interfaz de usuario sin tener que preocuparse por el código detrás de archivo. Presentador también es responsable de recuperar los datos solicitados a partir del modelo.

![alt text](https://github.com/EmilioSalgado/MVC-vs-MVP/blob/master/MVP.png "MVP")

Diferencias

![alt text](https://github.com/EmilioSalgado/MVC-vs-MVP/blob/master/difftable.png)
