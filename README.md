# LAB 3: CÁLCULO AMBULATORIO DEL ÍNDICE PLETISMOGRÁFICO QUIRÚRGICO (SPI)

## I. INTRODUCCIÓN

Con el objetivo de evaluar en tiempo real el equilibrio entre la nocicepción, es decir, la espuesta del sistema nervioso a estímulos potencialmente dañinos, y la analgesia, que es el efecto de los fármacos que bloquean dicha respuesta; se buscó índices cuantitativos y objetivos que buscan evaluar entre ambas variables, uno de dichos índices es el  índice pletismográfico quirúrgico, SPI por sus siglas en inglés, que se obtiene a través de la técnica fotopletismográfica (PPG). El PPG permite detectar los cambios en el volumen sanguíneo periférico asociados a cada latido cardíaco, y el SPI se encarga de relacionar la amplitud y frecuencia de los pulsos cardiacos; el resultado es un valor numérico entre 0 y 100, donde valores más altos indican una mayor respuesta nociceptiva (estrés quirúrgico).

La presente práctica busca el desarrollo de un sistema de medición continua del SPI utilizando un sensor óptico de reflectancia y herramientas de procesamiento digital de señales para la detección de picos por medio de MATLAB, para la adquisisión y cálculo del SPI. Todo lo anterior se realiza con el motivo de cumplir los siguientes objetivos [1]:

### Objetivo general:

Desarrollar un sistema de medición continua del índice pletismográfico quirúrgico (SPI) en condiciones ambulatorias.

### Objetivos específicos:

• Reconocer las características fundamentales de la onda de pulso a partir de las cuales se obtiene el SPI.

• Construir un sistema que calcule el SPI en tiempo real y bajo condiciones  ambulatorias.

• Validar el funcionamiento del sistema desarrollado mediante un método que induzca una respuesta fisiológica similar a la que produce el dolor agudo

## II. MARCO TEÓRICO

### a) PPG para la medición del volumen sanguíneo periférico

La fotopletismografía es una técnica no invasiva que permite detectar cambios en el volumen sanguíneo en los tejidos periféricos, como los dedos, a través de la absorción de luz por parte de la hemoglobina. Un sensor de PPG consta de una fuente de luz como un LED y un fotodetector, la luz emitida atraviesa el tejido, una parte de esa luz es absorbida por la sangre, mientras que el resto llega al fotodetector, la cantidad de luz absorbida varía respecto al volumen sanguíneo arterial generando una señal pulsátil, dicha señal permite tener un entendimiento de la actividad cardiovascular y el sistema nervioso autónomo.

El PPG indica la vasoconstricción simpática, es decir, ante una activación del sistema nervioso simpático como lo es el dolor o un estado de alerta, los vasos sanguíneos periféricos se contraen, disminuyendo la amplitud de la onda de pulso, sin contar de que también se altera la frecuencia cardiaca. Por lo anterior, esta señal es usada para estimar el equilibrio nocicepción-analgesia y, adicionalmente, el SPI. [2]

### b) Índice pletismográfico quirúrgico (SPI)

El SPI es un parámetro cuantitativo que evalúa el equilibrio entre nocicepción y analgesia, es especialmente usada durante la anestesia general. Esta es una componente la cual calcula a partir de la señal de fotopletismografía de modo que el SPI combina dos componentes de la onda de pulso:

1. Amplitud normalizada de la onda de pulso (NP): representa la relación entre la amplitud de la onda pulsátil y la componente continua de la señal PPG; esta relación isminuye cuando ocurre vasoconstricción simpática, es decir, cuando el cuerpo es sometido a un estado de dolor o alerta.

2. Intervalo entre latidos normalizado (IBI): indica los cambios en la frecuencia cardíaca, durante la activación simpática el intervalo entre latidos tiende a disminuir, lo cual indica un aumento de la frecuencia cardíaca.

La fórmula matemática para el cálculo del SPI según lo investigado corresponde a:

<img width="477" height="53" alt="image" src="https://github.com/user-attachments/assets/0cb7fd15-37e1-4cf6-89ed-56d9a24bcd56" />

_(Ecuación 1. Fórmula cálculo SPI)_

Cabe aclarar que los rangos de valores de NP (amplitud) están entre 0 a 100, al igual que los de IBI (intervalo latidos); en cuanto a la constante de 0.7 y 0.3, son coeficientes establecidos empíricamente. El rsultado del valor de SPI es un valor también entre 0 y 100, donde valores más altos reflejan una mayor respuesta nociceptiva, durante la anestesia general los rangos esperados de este indice rondan los valores de entre 20 y 50, un rango mayor puede provocar cierto grado de conciencia, por el contrario, un rango menor puede simbolizar un alto riesgo para el paciente. [3]

### c) Cold Pressor Test (CPT)

Es una prueba que consiste en la inmersión de la mano en agua fría de entre 0°C y 4°C durante 1 a 3 minutos por lo general, esto se hace con el fin de inducir una respuesta de estrés agudo y dolor controlado para estimular la activación simpática intensa, manifestadando un aumento de la frecuencia cardíaca, la elevación de la presión arterial y la vasoconstricción periférica, todos estos valores influyendo en respuesta nocioceptiva.

EL CPT es usado para crear un estímulo que simule una respuesta fisiológica similar a la que ocurre durante un estímulo quirúrgico doloroso; el medir el PPG y su correspondiente SPI durante esta práctica es posible evaluar incrementos en el SPI acordes con la activación simpáticaes, observando incrementos en el SPI acordes con la activación simpática. [4]

## III. METODOLOGÍA EXPERIMENTAL

### a) Sensor y circuito de adquisición

En un principio se usó el sensor TCST110, el cual se modificó tal como lo indicado en la guía, junto con su correspondiente circuito, inclusive se verificó el funcionamiento del mismo al observar la activación del LED  a trevés de una cámara, que indicaba una correcta polarización; sin embargo, al momento de adquisición, se observaba que no se distinguía la señal PPG pues la señal estaba sometido a una cantidad enorme de ruido, por lo que se optó por usar un sensor MAX30102.

Se cree que la razón principal del error en la toma con el sensor TCST110 fue la alta sensibilidad del mismo, y la delicadesa que implica la amplificación y filtrado de la señal por medio del circuito análogo, como por ejemplo el control de factores como potenciómetros y fuentes que garantizan la ganancia del mismo. Por lo anterior el sensor MAX30102 fue una opción más directa y fácil de aplicar, pues es fabricado especialmente para la medición de PPG al contener etapas de amplificación, filtros análogos y digitales que eliminan ruidos provenientes de la fuente o de la iluminación directa.

### b) Código de adquisición y registro SPI



### c) Método ejecución CPT



## IV. ANÁLISIS DE RESULTADOS

### a) Comparación del SPI en reposo y aplicando maniobra CPT



### b) Comparación valores SPI obtenidos con los observados durante una cirugía

Los valores del SPI en condiciones de reposo se encuentran en quilibrio, en donde predomina la actividad parasimpática, por tanto, la vasoconstricción periférica es baja y la frecuencia cardíaca se mantiene en valores basales; por lo anterior, el SPI calculado a partir de la PPG suele situarse en valores bajos por debajo de 20, tal como se evidencia.

Ahora bien, comparando los valores adquiridos con los que se pueden presentar en un estado de anestasia general, el rango SPI es completamente distinto. En un contexto quirúrgico donde el paciente es sometido a anestesia general, la respuesta autonómica a los estímulos quirúrgicos no se elimina por completo, el objetivo es mantener un balance nocicepción-analgesia que evite respuestas simpáticas excesivas. Los estudios han establecido lo siguiente: [3]

• SPI < 20: analgesia excesiva, sobresedación.

• SPI entre 20 y 50: rango óptimo analgesia aplicada.

• SPI > 50: analgesia insuficiente, puede haber activación simpática.

Ahora bien, la frecuencia de la señal PPG de un paciente bajo analgesia es ligeramente inferior, entre 50-80 lpm, pues se aumenta el tono parasimpático; por otro lado la amplitud de esta señal es por lo general mayor en la analgesia, pues se produce vasodilatación periférica, que incrementa el volumen sanguíneo pulsátil en los tejidos periféricos, aumentando la amplitud de la señal PPG.

### c) Alcance y limitaciones para cuantificar el dolor con el sistema diseñado

Frente al alcance del sistema, este es capaz de detectar respuestas autonómicas ante estímulos nociceptivos, evidenciando mediante la prueba de CPT, evidenciando que puede capturar cambios fisiológicos por la activación simpática a causa del dolor. Adicionalemente, permite una monitorización continua y ambulatoria al ser un sensor de bajo costo y tamaño reducido capás de medir el SPI en casi cualquier momento, sin contar que al medir variables fisiológicas y a partir de ellas calcular el SPI, otorga una cuantificación objetiva del dolor; lo anterior se puede demostrar y validar por medio de la práctica del CPT, que cuantifica el "nivel" de dolor que esta padeciendo el paciente en ele momento.

En cuanto a sus limitaciones, la calidad de la señal depende del sensor y la fijación del mismo, así como la presión ejercida sobre el y la ausencia de movimiento, en caso de afectar alguno de estos factores se pueden generar falsos picos o pérdida de señal. De mismo modo, el sistema de MATLAB de detección de picos puede fallar en señales ruidosas, afectando el cálculo del SPI. Por último, aunque la nociocepción refleja el procesamiento a estímulos dañinos, no es un indicador completo del dolor, pues este último es una experiencia subjetiva que involucra componentes sensoriales, emocionales y cognitivos, por ejemplo, un paciente puede sufrir dolor sin cambios significativos de su SPI. [5]

### d) ¿Cómo se relacionan las variaciones del volumen sanguíneo periférico con el balance autonómico?

El volumen sanguíneo periférico, medido a través de la señal PPG, refleja en tiempo real la actividad del sistema nervioso autónomo sobre la circulación en tejidos pequeños. Su relación se fundamenta en la inervación simpática vascular, que en los vasos sanguíneos de la piel, especialmente en extremidades como dedos, están densamente inervados por fibras simpáticas que al activarse producen vasoconstricción, reduciendo el volumen sanguíneo pulsatil afectando directamente el PPG. Por el lado opuesto, el sistema parasimpático modula el volumen sanguíneo al influir sobre la frecuencia cardíaca y el gasto cardíaco, que a su vez puede aumentar la amplitud de la señal adquirida por PPG.

Por lo anterior, el balance autonómico, que hace referencia a la actividad simpática y parasimpática, tienen efectos que reflejan en la PPG, cambiando su amplitud e inclusive el intervalo entre latidos que a su vez se traducen como cambios en el volumen sanguíneo de los dedos o cualquier tejido donde se realice la medición de PPG. [3]

### e) Comparación del SPI con otros índices empleados en cirugía

Como otros indicadores de nociocepción, aparte de SPI existen otros índices derivados de señales fisiológicas, a continuación se realizará un breve análisis y comparación de las dos mas relevantes respecto al SPI:

1. Índice nocicepción-analgesia (ANI): se obtiene por medio de la señal ECG, específicamente la variabilidad de la frecuencia cardíaca (HRV) en respuesta a la respiración. se calcula analizando el cambio parasimpática de la frecuencia cardíaca durante el ciclo respiratorio, al igual que el SPI se mide entre 0 a 100 y los valores inferiores a 50 sugieren nociocepción (dolor). Como ventaja refleja directamente el tono parasimpático si depender de la vasoconntricción, sin embargo al depender del ECG de buena calidad no es valido para pacientes con arritmias, marcapasos o ventilación con alta frecuencia.
   
2. Índice de perfusión (PI): al igual que SPI proviene de la señal PPG, específicamente la relación entre la componente alterna y continua (AC/DC), sus valores de entre 0.1-20 refleja la perfusión periférica, en donde su valor disminuye con la vasoconstricción simpática. Más que una señal independiente se suele usar en conjunto con la SPI para monitorear la nociocepción, por esto mismo está sujeto a cambios de perfusión por factores no dolorosos, como temperatura o prblemas de tensión arterial.

Por lo anterior se entiende que mientras el SPI refleja principalmente el componente simpático (vasoconstricción), el ANI refleja el componente parasimpático (modulación vagal), y el PI es un parámetro más simple pero menos específico; ninguno de ellos es perfecto pero permiten tener una mejor comprensión del proceso de la nociocepción. [6]

## V. CONCLUSIONES

Dando por concluido el presente laboratorio, se comprendió la complejidad y sensibilidad de los elementos análogos tal como sensores al momento de la captura de la señal de PPG, por lo cual se requiere de un estudio a profundidad de las alternativas para asegurar una captura de la señal lo menor dependiente posible a factores externos. Agregando se comprendió la importancia de los modelos empleados para la medición del SPI, pues dependiendo del modelo usado, puede desencadenar en errores de la medición del mismo alterando el estudio de los resultados.

Por último se comprendió la relación entre la medición del SPI con la actividad nocioceptiva, ya sea tratándose de un paciente en estado de reposo, cuando es sujeto a una activación simpática como el CPT, o inclusive bajo un estado de analgesia. Complementando a lo anterior, con el objetivo de tener una lectura de la nociocepción con mayor presición, se pueden integrar más variables en futuros sensores, como bien puede ser las señales ANI y PI, capaces de cubrir la falencias del SPI y complementandose entre si, reduciendo la incertidumbre causada por factores fisiológicos de los pacientes.

## VI. BIBLIOGRAFÍA

[1] A. Rosero, ECálculo ambulatorio del índice pletismográfico quirúrgico (SPI), Colombia, UMNG facultad de ingeniería biomédica, sep. 2025.

[2] J. L. Apfelbaum, C. Chen, S. S. Mehta, y T. J. Gan, “Postoperative pain experience: results from a national survey suggest postoperative pain continues to be undermanaged,” Anesthesia & Analgesia, 2003.

[3] V. Bonhomme, K. Uutela, G. Hans, I. Maquoi, J. D. Born, y J. F. Brichant, “Comparison of the Surgical Pleth Index with haemodynamic variables to assess nociception-anti-nociception balance during general anaesthesia,” British Journal of Anaesthesia, 2011.

[4] J. Carrillo, S. Vázquez, N. Rojo, “EL COLD PRESSOR TEST EN LA INVESTIGACIÓN DEL
DOLOR EXPERIMENTAL Y CLÍNICO”, Universidad Alfonso X el Sabio, 2005.

[5] J. L. Apfelbaum, C. Chen, S. S. Mehta, y T. J. Gan, “Postoperative pain experience: results from a national survey suggest postoperative pain continues to be undermanaged,” Anesthesia & Analgesia, 2003.

[6] G. Gruenewald y P. Ilies, “Monitoring the nociception-anti-nociception balance,” Best Practice & Research Clinical Anaesthesiology, vol. 27, no. 2, pp. 235–247, 2013.









