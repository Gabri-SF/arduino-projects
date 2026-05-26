
Hardware Setup & Temperature Sensing
====================================

.. tab-set::

   .. tab-item:: English

      The foundation of this project is measuring temperature using an NTC (Negative Temperature Coefficient) 10Kohm thermistor.

      **Voltage Divider Circuit**

      To read the resistance of the thermistor, a voltage divider circuit was used:
      - **Source:** 3.3V from the Arduino Nano ESP32.
      - **Components:** Thermistor and a 10kΩ fixed resistor.
      - **Connection:** The node between the thermistor and the resistor is connected to pin **A0**.

      Using the voltage divider formula, we can calculate the resistance of the thermistor based on the ADC reading.

      **Temperature Calculation**

      Initially, the Beta value of the thermistor was unknown. By using the **Steinhart-Hart equation** and assuming a room temperature of 25°C with a resistance of 10kΩ, a Beta value of approximately **3400** was determined.

      Later, the datasheet for the thermistor revealed the actual Beta value to be **3380**.

      .. important::
         When using the Steinhart-Hart equation, temperatures must be handled in **Kelvin**. Conversion to Celsius should only be done at the final step.

   .. tab-item:: Português

      A base deste projeto é a medição de temperatura usando um termistor NTC (Negative Temperature Coefficient) de 10Kohm.

      **Circuito Divisor de Tensão**

      Para ler a resistência do termistor, foi utilizado um circuito divisor de tensão:
      - **Fonte:** 3.3V do Arduino Nano ESP32.
      - **Componentes:** Termistor e uma resistência fixa de 10kΩ.
      - **Ligação:** O nó entre o termistor e a resistência está ligado ao pino **A0**.

      Usando a fórmula do divisor de tensão, podemos calcular a resistência do termistor com base na leitura do ADC.

      **Cálculo de Temperatura**

      Inicialmente, o valor Beta do termistor era desconhecido. Ao usar a **equação de Steinhart-Hart** e assumindo uma temperatura ambiente de 25°C com uma resistência de 10kΩ, foi determinado um valor Beta de aproximadamente **3400**.

      Mais tarde, a datasheet do termistor revelou que o valor Beta real era **3380**.

      .. important::
         Ao usar a equação de Steinhart-Hart, as temperaturas devem ser tratadas em **Kelvin**. A conversão para Celsius deve ser feita apenas no passo final.

.. code-block:: cpp

   // Snippet of the temperature calculation
   float resistance = SERIES_RESISTOR * (3.3 / voltage - 1.0);
   float steinhart = log(resistance / NOMINAL_RESISTANCE) / B_COEFFICIENT;
   steinhart += 1.0 / (NOMINAL_TEMPERATURE + 273.15);
   float temperature = (1.0 / steinhart) - 273.15;
