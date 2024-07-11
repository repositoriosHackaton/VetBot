# Proyecto VetBot  

Se debe agregar toda la documentación que ustedes consideren pertinente para la compresión de los modelos usados, la ejecución del código y los resultados obtenidos. 
Puden, si desean, agregar imágenes o resultados obtenidos. 

Recuerden que este readme es su puerta de entrada para su proyecto. 

# Nombre del Proyecto: VetBot

* Breve descripción del proyecto -> Alguna imagen o gif que muestre el proyecto
  
Nuestra propuesta es desarrollar un chatbot para una consulta en el veterinario. Esta nos dará información básica sobre servicios veterinario, oportunidad para agendar citas para consultas, responder preguntas frecuentes sobre el cuidado de la mascota, dar primeros auxilios, recordar sobre citas y vacunas pendientes. 

![image](https://github.com/repositoriosHackaton/VetBot/assets/164280396/d5036bda-ce31-4471-897f-c951a1014800)

* Arquitectura del proyecto + imagen

La arquitectura del proyecto incluye los siguientes componentes:
Librerías de Python:
* tkinter: Utilizada para crear la interfaz gráfica de usuario (GUI).
*	tensorflow: Utilizada para construir y entrenar modelos de aprendizaje automático.
*	keras: Utilizada como una API de alto nivel para construir y entrenar modelos de aprendizaje profundo.
* numpy: Utilizada para operaciones matemáticas y de matrices.
*	random: realizamos operaciones aleatorias de números.
*	json: Permite trabajar con datos en formato JSON.
*	pickle: Nos permite serializar y deserealizar objetos.
*	nltk: Nos permite trabajar con datos del lenguaje natural.

Frameworks de Aprendizaje Automático:
*	TensorFlow: Un framework de código abierto para el aprendizaje automático, ampliamente utilizado para tareas de aprendizaje profundo.
*	Keras: Una biblioteca de redes neuronales de alto nivel que se ejecuta sobre TensorFlow.

![image](https://github.com/repositoriosHackaton/VetBot/assets/164280396/6eb8765b-504a-46da-9834-122df2613795)

 
Interfaz Gráfica de Usuario (GUI):
*	Uso de tkinter para la creación de una ventana de chat donde los usuarios pueden interactuar con el chatbot.
*	Un área de texto para mostrar la conversación (ChatLog).
*	Un área de entrada de texto para que el usuario ingrese sus preguntas (EntryBox).
*	Un botón de enviar (SendButton).

Entrenamiento del Modelo:

Utilizamos TensorFlow para entrenar un modelo de aprendizaje automático con datos de entrenamiento específicos de “intents_veterinaria_sin_tildes ”.
El entrenamiento del modelo en múltiples épocas (se muestra hasta la época 23) con seguimiento de la precisión (accuracy) y la pérdida (loss).
Función del Chatbot:
*	Tenemos una función (respuesta) para generar respuestas basadas en el mensaje del usuario.
*	Tenemos una inserción de mensajes del usuario y del chatbot en el ChatLog.
Vinculación de Eventos:
*	Vinculamos el evento de la tecla Enter para enviar mensajes.

Bucle Principal:
*	Un bucle principal para ejecutar la interfaz gráfica (base.mainloop()).

* Proceso de desarrollo:

-Fuente del dataset

Esta ubicada en el archivo intents_veterinaria_sin_tildes.json en donde contenemos todos los parámetros con el cual se entrenará el modelo. 

![image](https://github.com/repositoriosHackaton/VetBot/assets/164280396/e4b4b47f-413a-4908-8877-343597dee1b3)


-Limpieza de datos (img que lo valide)

Primero: Importamos la biblioteca en Python para trabajar con datos de lenguaje natural u luego hacemos el proceso de convertir una palabra a su forma base o lema.

![image](https://github.com/repositoriosHackaton/VetBot/assets/164280396/ffbf5cf5-4be4-45f0-8be7-e9ef84d6fec9)

Segundo: Cargamos el json con el que trabajaremos
![image](https://github.com/repositoriosHackaton/VetBot/assets/164280396/68a3a4b9-6021-492f-8471-c3e2575eb5a6)

Tercero: Descargamos los paquetes de nltk el cual nos permite trabajar con datos del lenguaje natural.

![image](https://github.com/repositoriosHackaton/VetBot/assets/164280396/35cfc010-4fe1-4a5d-af09-a8c82201f5d0)

Cuarto: Tenemos el preprocesamiento de Textos

![image](https://github.com/repositoriosHackaton/VetBot/assets/164280396/5205fad2-a3be-42d0-b6bb-dc355681cad1)

Quinto: Pasamos la información a unos y a ceros

![image](https://github.com/repositoriosHackaton/VetBot/assets/164280396/685a7e91-e437-4df2-8ef5-d2f06e456167)

Sexto: Mostramos los patrones de entrenamiento

![image](https://github.com/repositoriosHackaton/VetBot/assets/164280396/cf310ef2-0e1a-4632-86e5-e5eb5bd71673)

Séptimo: Tenemos la función para limpiar y lematizar oraciones, y también la conversión de oraciones a una representación numérica.

![image](https://github.com/repositoriosHackaton/VetBot/assets/164280396/76615402-ace4-427f-8799-8683a5a5eab4)


-Manejo excepciones/control errores

Para mejorar el manejo de excepciones y control de errores en el proyecto "VetBot", se pueden agregar bloques try-except en varias partes del código donde puedan ocurrir errores.
En caso de que el usuario escriba mal una palabra él puede reconocer cual es y responder en base a lo que el usuario necesita. 

-¿Qué modelo de Machine Learning están usando?

En el proyecto "VetBot", nosotros estamos utilizando un modelo de aprendizaje automático Machine Learning para clasificar las consultas de los usuarios y generar respuestas. El modelo específico utilizado es una red neuronal secuencial creada con Keras, una API de alto nivel que se ejecuta sobre TensorFlow. Creamos una red neuronal secuencial con múltiples capas densas y de dropout, entrenada con el optimizador SGD y compilada con una función de pérdida de entropía cruzada categórica. Este modelo se utiliza para clasificar las consultas de los usuarios y generar respuestas apropiadas basadas en las categorías predichas.

-Estadísticos (Valores, gráficos, …)

Estos valores se observan en el historial de entrenamiento monitoreando de la precisión (accuracy) y la pérdida (loss) a lo largo de las épocas de entrenamiento.

![image](https://github.com/repositoriosHackaton/VetBot/assets/164280396/90eed04a-dbc6-49e6-b531-530c61a47374)


-Métrica(s) de evaluación del modelo

En modelo que creamos tiene buen nivel de acontecimiento ya que cada vez que lo vamos entrenando el modelo va siendo más asertivo es decir en un epochs de 100 con un batch_size de 8 el modelo es muy malo y no predice exactamente como lo previste uno. Mientras que con epochs de 100 con un batch_size variándolo entre 13 y 16 el modelo es muy efectivo marcándonos una probabilidad en cada entrenamiento de 89 a 98.

* Funcionalidades extra:

VetBot tiene la capacidad de responder ante una mala ortografía que tenga el usuario, esta capacidad puede hacer que VetBot sea más accesible y fácil de usar, mejorando la calidad general de la interacción con los usuarios.

![Imagen de WhatsApp 2024-07-03 a las 09 58 48_ebe3f953](https://github.com/repositoriosHackaton/VetBot/assets/164280396/28eaad58-c699-4d55-bbe1-11e026f22b2b)



