# Apuntes_Novena Semana
Apuntes control de movimiento - Segundo Corte - Novena Semana

# Control de Movimiento (Diseño de Transmisión)

**Introducción al Diseño de Transmisión**

El diseño de transmisión se encarga de transferir potencia y movimiento entre componentes mecánicos, utilizando elementos como engranajes, correas y cadenas. Su objetivo es garantizar eficiencia, durabilidad y seguridad en sistemas como vehículos, maquinaria y robótica. Un diseño adecuado optimiza el rendimiento, reduce el desgaste y mejora la eficiencia energética, combinando principios de cinemática, dinámica y resistencia de materiales.

## 1. Requerimientos de diseño

Para que el diseño en control de movimiento no tenga ningún inconveniente se requiere una excelente selección de un motor y la transmisión del sistema para que el movimiento sea llevado a cabo en la carga o una herramienta. Para este diseño se deben tener en cuenta los siguientes indicadores:

* Garantizar que el torque del motor a su máxima velocidad sea suficiente para la aplicación, considerando un margen de seguridad.

* Verificar que la relación de inercia entre el motor y la carga sea la adecuada para un desempeño óptimo.

* Asegurar que el diseño cumpla con criterios adicionales como costo, precisión y tiempos de ciclo, según los requisitos del sistema.

Existen diferentes tipos de problemas que nos enfrentamos al momento de diseñar en el cual se especifíca que es lo que se debe solucionar:

* Teniendo el Movimiento de carga deseado	se busca -> dimensionar la Transmisión y motor.

* Teniendo el Motor y transmisión existentes	se busca -> dimensionar el Movimiento de carga resultante.

* Teniendo el Motor existente, movimiento de carga deseado se busca -> dimensionar la Transmisión.

* Teniendo el Movimiento de carga deseado, transmisión se busca-> dimensionar el Motor.

## 2. Inercia y Torque Reflejado

**Inercia Reflejada**: Es la inercia equivalente que el motor "siente" debido a la carga y los elementos de transmisión. Se calcula ajustando la inercia de la carga $J_{L}$ a la referencia del motor mediante la relación de transmisión (N):

$J_{r}:J_{L}*N^{2}$

Donde N es la relación que contempla la transmisión

**Torque Reflejado:** Es el torque que el motor debe generar para mover la carga a través de la transmisión. Se obtiene transformando el torque de la carga $T_{L}$ a la referencia del motor:

$$T_{r}:\frac{T_{L}}{N}$$

## 3. Conceptos de Transmisión Engranajes

La relación de engranajes determina cómo se transmite el movimiento y el torque entre engranajes de distintos tamaños en un sistema mecánico. Se define como la razón entre el número de dientes o los diámetros de los engranajes involucrados:

$$N = \frac{Z_{conducido}}{Z_{conductor}} = \frac{D_{conducido}}{D_{conductor}}$$

Donde:

* 𝑍 es el número de dientes.

* 𝐷 es el diámetro del engranaje.

* N es la relación de transmisión.

**Efectos de la Relación de Engranajes**

*Reducción de velocidad (𝑁 > 1)*

* El engranaje conducido es más grande que el conductor.

* La velocidad angular disminuye, pero el torque aumenta.

*Aumento de velocidad (𝑁 < 1)*

* El engranaje conducido es más pequeño.

* La velocidad angular aumenta, pero el torque disminuye.

*Relación 1:1 (N=1)*

* Ambos engranajes tienen el mismo tamaño.

* No hay cambio en la velocidad ni en el torque.

### 3.1. Eficiencia

La eficiencia en el control de movimiento se refiere a la capacidad de un sistema para transformar la energía en movimiento preciso y efectivo, minimizando pérdidas y optimizando el desempeño.

**Factores Clave en la Eficiencia**

*Transmisión de Energía*

* Usar mecanismos de transmisión eficientes, como engranajes de alta precisión o correas síncronas con baja fricción.

* Minimizar pérdidas por rozamiento y holguras en acoplamientos mecánicos.

*Control del Torque y la Velocidad*

* Implementar controladores PID o algoritmos avanzados para ajustar dinámicamente el torque y la velocidad.

* Asegurar una relación de inercia adecuada entre el motor y la carga para mejorar la respuesta del sistema.

*Reducción de Pérdidas Energéticas*

* Seleccionar motores y accionamientos con alta eficiencia.

* Evitar sobrecargas y diseñar el sistema para operar dentro del rango óptimo de eficiencia del motor.

*Optimización del Perfil de Movimiento*

* Usar aceleraciones y desaceleraciones suaves para evitar picos de corriente y desgaste mecánico.

* Aplicar técnicas como interpolación y control de trayectoria para mejorar la precisión y reducir vibraciones.

*Selección de Sensores y Realimentación*

* Implementar sensores de alta resolución para mejorar la precisión y estabilidad del control.

* Utilizar sistemas de retroalimentación en tiempo real para corregir desviaciones y mejorar la eficiencia del sistema.
  
### 1.3. Motores Corriente Alterna - Síncronos
Son máquinas eléctricas cuya velocidad de rotación depende de la frecuencia de la red AC, manteniendo igual velocidad entre el rotor y el campo magnético del estator. Los imanes de campo se montan en el rotor y se excitan con corriente continua, mientras que las bobinas de armadura, divididas en tres partes, se alimentan con corriente trifásica. Estos motores contienen las siguientes caracteristicas fisicas:
* Estator:  Bobinado trifásico para producir el campo magnético giratorio.
* Rotor: Tiene unos imanes o bobinas de excitación recorridas por una corriente continua. Gira a la velocidad del campo magnético.
* Anillos Rozantes: Son anillos metálicos que sirven para alimentar de corriente continua al rotor.

Se debe tener en cuenta que para iniciar el motor síncronico se debe aplica una señal alterna trifásica al estator y una señal DC al rotor, generando un campo magnético con polaridad. El campo del estator atrae al del rotor, provocando su giro a velocidad de sincronismo.
  
En cuestiones industriales estos tipos de motores tienen varias aplicaciones, por lo que podemos resaltas las siguientes ventajas y desventajas:

| **Ventajas**                                     | **Desventajas**                                                           |
|--------------------------------------------------|---------------------------------------------------------------------------|
| • Muy poco mantenimiento                         | • Control de dificultad intermedia                                        |
| • Excelente resistencia al entorno               | • Se requiere respuesta 1:1 entre driver motor                            |
| • Compactos y ligeros                            | • Sus imanes pueden sufrir desmagnetización con el tiempo                 |
| • Alta eficiencia en todo tipo de aplicaciones   |                                                                           |

Tabla 3. Motores AC Síncronicos

### 1.4. Servomotores
**Modelo por corriente de armadura**
* Parte Eléctrica: $\upsilon a= La*Ia + Ra*Ia + Vb$
* Parte Magnética: $Tm = ( Ka*Kc*Ic )*Ia( t ) = K\tau *Ia( t )$  $Vb = Ke* \omega$  $Tm = Tc + Tp$
* Parte Mecánica: $J*\frac{\partial^2 \theta }{\partial t^2  } + b*\frac{\mathrm{d} \theta }{\mathrm{d} t} + R\theta = \tau ( t )$
$La * \frac{\mathrm{d} ( \frac{J \theta   + b\theta  + K\theta }{K\tau } )}{\mathrm{d} t} + Ra * ( \frac{J \theta   + b\theta  + K\theta }{K\tau } ) + Ke \theta  = \upsilon a$

## 2. SENSORES
Un sensores un dispositivo que detecta cambios en una magnitud física o química, como temperatura, presión o luz, y los convierte en señales eléctricas para su procesamiento. Se usa en diversos sistemas para monitoreo y automatización.

>🔑 *Encoder:* Un encoder es un sensor que convierte el movimiento (rotación o desplazamiento) en señales eléctricas para medir posición, velocidad o dirección en motores y sistemas automatizados.
>
>🔑 *Resolver:* Es un sensor electromecánico que mide la posición angular y la velocidad de un eje, utilizando señales eléctricas sin necesidad de componentes electrónicos en el rotor, lo que lo hace resistente y preciso. 

Los servomecanismos utilizan sensores para medir corriente (torque), posición y velocidad, asegurando el cumplimiento de las rutinas de movimiento necesarias para diversas aplicaciones. Sin estas mediciones, no se puede garantizar un control preciso.
Se analizarán algunos tipos de sensores que existen, especialmente los encoder u otros sensores que nos permitan hacer mediciones de pulsos de un motor.

### 2.1. Encoders
Generalmente son usados para medir tanto la posición como la velocidad del eje de cualquier tipo de motor.
* Encoders Absolutos: Tienen un Código digital de posición absoluta para una sola revolución y un contador de revoluciones.
* Encoders Incrementales: Generan un número específico de pulsos por unidad de longitud de movimiento lineal.

Comparandos ambos tipos de encoders, tenemos que:

| **Elemento**              | **Encoder Incremental**                 |  **Encoder Absoluto**                                                     |
|---------------------------|-----------------------------------------|---------------------------------------------------------------------------|
| Salida                    | Salida aumenta incrementalmente         | Hay posiciones absolutas en una revolución                                |
| Reinicialización          | Operación de retorno durante encendido  | No require ninguna operación de retorno ya que se sabe siempre su posición dentro de una revolución   |
| Precio                    | Bajo                                    |Alto                                                                        |
| Estructura                | ![](https://github.com/MariaFernandaOrtiz-111449/Apuntes---Tercera-Semana/blob/7c772e8d44d86a24e2e5148ac6cf6bbda825b5d9/Encoder%20incremental.png)  |  ![](https://github.com/MariaFernandaOrtiz-111449/Apuntes---Tercera-Semana/blob/b67c06e9965e10d66c7d25e072653e2fdb2df51d/Encoder%20Absoluto.png)            |
|Adicionales                |  Solamente se detectan pulsos           | Hay un Código perforado en el encoder. El mas usado es gray                |

Tabla 4. MEncoders

### 2.2. Resolver
Un resolver es un sensor analógico de posición angular con un rotor y un estator embobinados. Su funcionamiento es similar al de un transformador, donde la amplitud inducida en el rotor varía según la posición relativa. Existen modelos con y sin escobillas.
* **Voltajes del resolver**: entre 2V RMS y 40V RMS.  
* **Frecuencia de operación**: 50 Hz a 20 kHz.  
* **Relación de transformación**: 0.2 V/V a 1 V/V.

### 2.3. Medición de Torque
torque se infiere a partir de la corriente, debido a su relación aproximadamente lineal.   
* **Shunt**: Usa una pequeña resistencia para medir voltaje y aplicar la ley de Ohm.  
* **Efecto Hall**: Detecta cambios en el campo magnético y, por la ley de Faraday, permite obtener la corriente.

## 3. DRIVERS DE POTENCIA
Un driver es un amplificador que convierte señales de control de baja potencia en señales de alta potencia (voltaje y/o corriente) para alimentar actuadores como motores, por lo que también se le conoce como amplificador. Cada eje requiere su propio driver y controlador. En los servomotores modernos, el controlador gestiona la retroalimentación de posición y velocidad, mientras que el driver maneja la retroalimentación de corriente.
El manejo del driver se realiza mediante PWM (modulación por ancho de pulso), el estándar industrial para motores DC y AC, debido a su alta eficiencia. Algunos de los ejemplos de drivers de potencia que se pueden encontrar en el mercado, y que son bastante usados son:

* Puente H
* L293 y L298 (AN240/1288)

## 4. Ejercicios
**Validación de Modelo**

En primera medida se realiza un montaje de un motor deseado para la estimación de parámetros faltantes dentro del datasheet del mismo. Se obsera la entrada y salida del mismo mediante el osciloscopio. Todo este proceso se ralizará dentro de un espacio simulado para no desgastar los componentes físico y poder realizar las pruebas necesarias sin un alto gasto económico.

 ![](https://github.com/MariaFernandaOrtiz-111449/Apuntes---Tercera-Semana/blob/d6e6914ec354cdf12eba0cc78fcfb4d78b20ab08/Montaje.jpg)

En segunda medida, se especifican los parámtros que tendrá nuestro motor, identificando con el nombre de una variable los datos restantes a calcular.

![](https://github.com/MariaFernandaOrtiz-111449/Apuntes---Tercera-Semana/blob/19f1970097cd354a2adfe8c3de00d11f888ff097/parametros.jpg)

Además, se debe tener en cuenta un motor estándar para tomar en cuenta la respuesta de un motor a una entrada escalón. Una vez teniendo las 2 gráficas del sistema, tanto la del motor de referencia y nuetro motor seleccionado, se realiza un contraste de ambas respuestas.
![](https://github.com/MariaFernandaOrtiz-111449/Apuntes---Tercera-Semana/blob/7f7f518c4866c9cb6369a220ca7803f549a9a937/Simulacion.jpg)

Por último, se realiza la estimación de parámetros de nuestro motor y con esto completar la información faltante del funcionamiento del motor seleccionado.

![](https://github.com/MariaFernandaOrtiz-111449/Apuntes---Tercera-Semana/blob/aa328692bd5aad8d0854940948ad1e2ec0514aa9/estimaci%C3%B3n.jpg)

En la siguiente imagen podemos observar la respuesta del motoro con la estimación de parámtros faltantes; se observa un seguimiento a la referencia de la entrada con la que se alimenta al motor. 

![](https://github.com/MariaFernandaOrtiz-111449/Apuntes---Tercera-Semana/blob/6272ebc703a4665d498ee1e5b2a2bb38e9ef1e22/datos%20iniciales.jpg)

## 5. Conclusiones
Los motores eléctricos, junto con los sensores y drivers, forman la base de innumerables aplicaciones industriales y tecnológicas. Su correcto funcionamiento depende de una integración efectiva de los diferentes componentes, desde la generación del movimiento hasta su regulación mediante señales de control y retroalimentación.
El uso de tecnologías como PWM en los drivers y la incorporación de sensores de posición y corriente han permitido aumentar la eficiencia y precisión de los sistemas de automatización. Comprender estos conceptos es esencial para diseñar y optimizar motores en diversas aplicaciones, desde robótica hasta maquinaria industrial, garantizando un desempeño confiable y eficiente.

## 6. Referencias
* CHAPMAN. 2005. Maquinas eléctricas. Madrid: McGraw-Hill Interamericana
* LANGSDORF. 1968. Principios de las maquinas de corriente continua. McGrawHill
* SERRANO IRIBARNEGARAY. 1989: Fundamentos de maquinas eléctricas rotativas. Marcombo.
* https://www.swe.siemens.com/spain/web/es/industry/drive_tech/variadores /Pages/Variadores.aspx
