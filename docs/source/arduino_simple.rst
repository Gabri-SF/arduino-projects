Simple Arduino Thermal Monitor
==============================

.. tab-set::

   .. tab-item:: English

      This initial version of the project uses the ESP32 in **Access Point (AP)** mode to host a simple web dashboard.

      **Features**

      - **Local Web Server:** Hosted directly on the ESP32.
      - **Visual Feedback:** RGB LEDs change color based on the current temperature.
      - **Real-time Plotting:** Sends data to the Arduino Serial Plotter.

      **PWM Control**

      In this project, PWM (Pulse Width Modulation) is used to vary the intensity of the RGB LEDs.

      .. note::
         On the ESP32, you can use the ``ledcSetup(channel, freq, resolution)`` function to set up a PWM channel, use ``ledcAttachPin(pin, channel)`` to attach the pin to the channel, and then use ``ledcWrite(channel, value)`` to write a value. 

      This allows for high-precision control of LED brightness and color blending.

   .. tab-item:: Português

      Esta versão inicial do projeto usa o ESP32 em modo **Access Point (AP)** para alojar um painel web simples.

      **Funcionalidades**

      - **Servidor Web Local:** Alojado diretamente no ESP32.
      - **Feedback Visual:** LEDs RGB mudam de cor com base na temperatura atual.
      - **Gráficos em Tempo Real:** Envia dados para o Serial Plotter do Arduino.

      **Controlo PWM**

      Neste projeto, o PWM (Pulse Width Modulation) é usado para variar a intensidade dos LEDs RGB.

      .. note::
         No ESP32, podes usar a função ``ledcSetup(channel, freq, resolution)`` para configurar um canal PWM, usar ``ledcAttachPin(pin, channel)`` para ligar o pino ao canal, e depois usar ``ledcWrite(channel, value)`` para escrever um valor.

      Isto permite um controlo de alta precisão do brilho dos LEDs e da mistura de cores.

Arduino Code
------------

Below is the complete code for the standalone thermal monitor:

.. literalinclude:: ../../temperature.txt
   :language: cpp
   :linenos:
