# TutorialSwiftWit


Para este tutorial vamos a hacer un cronómetro. Este tutorial es una versión traducida del StopWatch Tutorial (https://www.ioscreator.com/tutorials/stopwatch-tutorial) por @ArthurKnopper con el código de @katiearriaga 

## Crear el proyecto 

Abre Xcode crea un nuevo proyecto y selecciona Single-View Application

![static1 squarespace](https://user-images.githubusercontent.com/17911474/38650581-56383926-3dc2-11e8-865c-83e91301f85e.png)

Dale 'Next' o 'Siguiente' e ingresa los siguientes datos! Recuerda ponerle en lenguaje **Swift** y dispositivos **iPhone**


![static1 squarespace-1](https://user-images.githubusercontent.com/17911474/38650724-0ed91de2-3dc3-11e8-92ff-b4b6cada3915.png)


## Crear los botones 
<img width="253" alt="screen shot 2018-04-11 at 20 04 35" src="https://user-images.githubusercontent.com/17911474/38651082-dc56598c-3dc4-11e8-8036-3898d0a9b63c.png">




Selecciona el archivo 'Main Story Board' 


Crea 1 etiqueta con '00:00' y 3 botones con **Start Stop y Reset**

<img width="300" alt="screen shot 2018-04-11 at 20 15 47" src="https://user-images.githubusercontent.com/17911474/38651167-58dd6e8c-3dc5-11e8-8228-5f97b5903c30.png">


El resultado debe de quedar así 



![static1 squarespace-2](https://user-images.githubusercontent.com/17911474/38651315-30878354-3dc6-11e8-9f17-19ef20cb2511.png)

Selecciona Assitant Editor y asegúrate que ViewController.swift este visible. Ctrl y arrastra  la etiqueta a la clase de ViewControllery crea el siguiente Outlet. 
