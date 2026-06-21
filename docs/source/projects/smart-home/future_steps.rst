Future Steps and Alternatives
=============================

.. tab-set::

   .. tab-item:: English

      The project continues to evolve with new integrations and discoveries in the IoT ecosystem.

      **Next Steps: Supabase**

      The next phase of the project involves integrating **Supabase** for long-term data persistence. This will allow for:
      - Storing historical temperature data.
      - User management and extended security.
      - Analytics on device usage.

      **Home Assistant and ESPHome**

      During the development process, **Home Assistant** was discovered as a powerful alternative for home automation. 
      Using **ESPHome** with YAML configuration simplifies the process of integrating ESP32 devices into a local network without writing extensive custom C++ code.

      **Lessons Learned**

      - **Hardware Choice:** While the Arduino Nano ESP32 is a great board, standard ESP32 modules can be more cost-effective for large-scale deployments.
      - **Protocol Efficiency:** MQTT is highly efficient for low-bandwidth IoT communication.
      - **Security:** Implementing authentication (even in a learning project) is crucial when exposing devices to the internet.

   .. tab-item:: Português

      O projeto continua a evoluir com novas integrações e descobertas no ecossistema IoT.

      **Próximos Passos: Supabase**

      A próxima fase do projeto envolve a integração com o **Supabase** para persistência de dados a longo prazo. Isto permitirá:
      - Armazenar histórico de dados de temperatura.
      - Gestão de utilizadores e segurança alargada.
      - Análise de utilização dos dispositivos.

      **Home Assistant e ESPHome**

      Durante o processo de desenvolvimento, o **Home Assistant** foi descoberto como uma alternativa poderosa para a domótica.
      O uso do **ESPHome** com configuração YAML simplifica o processo de integração de dispositivos ESP32 numa rede local sem a necessidade de escrever código C++ customizado extenso.

      **Lições Aprendidas**

      - **Escolha de Hardware:** Embora o Arduino Nano ESP32 seja uma excelente placa, módulos ESP32 padrão podem ser mais económicos para implementações em larga escala.
      - **Eficiência do Protocolo:** O MQTT é altamente eficiente para comunicação IoT de baixa largura de banda.
      - **Segurança:** Implementar autenticação (mesmo num projeto de aprendizagem) é crucial ao expor dispositivos à internet.
