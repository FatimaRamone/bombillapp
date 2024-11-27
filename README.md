README - Bombilla App

Este proyecto es una aplicación Android que controla la linterna del dispositivo mediante un botón en la interfaz de usuario. El botón permite alternar entre el encendido y apagado de la linterna, y muestra un cambio visual en la interfaz (con una imagen que cambia entre "encendido" y "apagado").
Funcionalidad

    Botón de Encendido/Apagado: La aplicación permite encender y apagar la linterna del dispositivo al presionar un botón.
    Interfaz Visual: Se cambia una imagen de estado (de "encendido" a "apagado") para reflejar el estado de la linterna.
    Compatibilidad con la Linterna: Utiliza el CameraManager para acceder al hardware de la cámara del dispositivo y controlar el modo linterna (torch mode).

Características

    Encendido de Linterna: Cuando el usuario presiona el botón por primera vez, la linterna se enciende.
    Apagado de Linterna: Cuando el usuario presiona el botón nuevamente, la linterna se apaga.
    Cambio de Imagen: Una imagen cambia entre un estado de "linterna apagada" y "linterna encendida" según el estado de la linterna.

Requisitos

    Versión de Android: La aplicación requiere Android 6.0 (Marshmallow) o superior, ya que utiliza la API de linterna (Torch Mode), disponible desde Android 6.0.

Instrucciones de Uso

    Instalación:
        Clona o descarga el proyecto.
        Abre el proyecto en Android Studio.
        Asegúrate de que tu dispositivo tenga linterna (flash) disponible.

    Uso:
        Al iniciar la aplicación, verás un botón en la interfaz.
        Presiona el botón para encender o apagar la linterna del dispositivo.
        La imagen de la interfaz cambiará entre los recursos R.drawable.on y R.drawable.off para indicar el estado de la linterna.

Descripción del Código
MainActivity.java

    Inicialización de Vista:
        El Button y el ImageView se vinculan a los elementos de la interfaz de usuario mediante findViewById.
        Se utiliza CameraManager para acceder a la linterna del dispositivo.

    Encendido/Apagado de Linterna:
        Se utiliza setTorchMode de CameraManager para encender y apagar la linterna.
        Cuando el estado de la linterna cambia, se actualiza la imagen en la interfaz mediante imageView.setImageResource().

    Manejo de Excepciones:
        Se captura cualquier posible CameraAccessException en caso de errores al acceder a la cámara del dispositivo.

activity_main.xml

El archivo XML de la interfaz contiene:

    Un botón (Button) para controlar la linterna.
    Un ImageView para mostrar la imagen correspondiente al estado de la linterna.

<Button
    android:id="@+id/button"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Encender/Apagar Linterna"
    android:layout_centerInParent="true"/>

<ImageView
    android:id="@+id/imageView"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_below="@id/button"
    android:layout_centerHorizontal="true"
    android:src="@drawable/off"/>

Permisos

La aplicación utiliza el permiso de cámara para controlar la linterna. Asegúrate de que el dispositivo tiene permiso para acceder a la cámara.
Dependencias

No hay dependencias externas en este proyecto, pero requiere Android SDK con nivel mínimo de API 23 (Android 6.0).
Mejoras Futuras

    Indicadores de Estado Mejorados:
        Se pueden agregar animaciones o sonidos al encender/apagar la linterna.

    Control de Linterna con Gestos:
        Implementar control de la linterna mediante gestos o comandos de voz.

    Compatibilidad con Dispositivos sin Linterna:
        Añadir validaciones para comprobar si el dispositivo tiene linterna y manejarlo adecuadamente.

Contribución

Si deseas contribuir a este proyecto, puedes hacerlo realizando mejoras o sugerencias. Envía un pull request o abre un issue con tus propuestas.

Este proyecto es un excelente ejemplo de cómo interactuar con el hardware del dispositivo (linterna) en una aplicación Android básica.
