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


![static1 squarespace-1](https://user-images.githubusercontent.com/17911474/38713656-deafafb6-3e97-11e8-8151-fbfbf8759e7f.png)

Selecciona y arrastra del botón de **Start** al ViewController.swift y arrastra la etiqueta y crea el siguiente Outlet. 

![static1 squarespace-2](https://user-images.githubusercontent.com/17911474/38713563-5ad0b44c-3e97-11e8-9506-9f7e53f015e1.png)


Selecciona y arrastra del botón de **Pause** al ViewController.swift y arrastra la etiqueta y crea el siguiente Outlet. 

![static1 squarespace-3](https://user-images.githubusercontent.com/17911474/38713564-5ae7f9e0-3e97-11e8-9a39-f58c7ea56cc6.png)

Selecciona y arrastra del botón de **Start** al ViewController.swift y arrastra la etiqueta y crea la siguiente **Acción**. 

![static1 squarespace-4](https://user-images.githubusercontent.com/17911474/38713565-5afae38e-3e97-11e8-854e-1bd66411314e.png)

Selecciona y arrastra del botón de **Pause** al ViewController.swift y arrastra la etiqueta y crea la siguiente **Acción**.

![static1 squarespace-5](https://user-images.githubusercontent.com/17911474/38713566-5b0f169c-3e97-11e8-95f5-c339614e494d.png)

En ViewController.swift agrega el siguiente código para inicializar las variables: 

```
  var counterMs = 00
    var counterSec = 00
    var counterMin = 00
    var timer = Timer()
    var isPlaying = false
```

Cambia el método viewDidLoad a: 


```
override func viewDidLoad() {
    super.viewDidLoad()
        
    timeLabel.text = String(counter)
    pauseButton.isEnabled = false
}

```

Implementa los siguentes **IBActions**: 
```
@IBAction func startTimer(_ sender: AnyObject) {
    if(isPlaying) {
        return
    }
    startButton.isEnabled = false
    pauseButton.isEnabled = true
        
    timer = Timer.scheduledTimer(timeInterval: 0.1, target: self, selector: #selector(UpdateTimer), userInfo: nil, repeats: true)
    isPlaying = true
}
    
@IBAction func pauseTimer(_ sender: AnyObject) {
    startButton.isEnabled = true
    pauseButton.isEnabled = false
        
    timer.invalidate()
    isPlaying = false
}

@IBAction func resetTimer(_ sender: AnyObject) {
    startButton.isEnabled = true
    pauseButton.isEnabled = false
        
    timer.invalidate()
    isPlaying = false
    counter = 0.0
    timeLabel.text = String(counter)
}
```
La variable booleana isPlaying es usada para checar si el timer del cronómetro esta corriento. Para invalidar el método de la clase NSTimer es usada para parar el cronómetro. El método UpdateTimer se invoca cuando se inicia el cronómetro.

```
func UpdateTimer() {
    counter = counter + 0.1
    timeLabel.text = String(format: "%.1f", counter)
}

```

Compila y corre el proyecto debe de quedar algo así: 


![static1 squarespace-7](https://user-images.githubusercontent.com/17911474/38714378-84a2310c-3e9b-11e8-81e2-95b1b6aa2df3.png)

