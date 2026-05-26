Smart Home Control (MQTT)
=========================

.. tab-set::

   .. tab-item:: English

      The project evolved from a simple local monitor to a centralized web interface for monitoring and controlling multiple IoT nodes using the **MQTT** protocol.

      **Project Overview**

      The goal is to provide a premium industrial-themed dashboard for real-time control.

      **Tech Stack**

      - **Framework:** Next.js 16 (App Router)
      - **Language:** TypeScript
      - **Styling:** Tailwind CSS v4 (with Geist Mono)
      - **Authentication:** NextAuth.js (Google Provider)
      - **Communication:** MQTT (lightweight IoT protocol)
      - **Deploy:** Vercel

      **Implemented Features**

      1. **Security & Access**
         - Robust authentication via Google (NextAuth.js).
         - Middleware protection for routes and APIs.
         - Restricted access via email whitelist.

      2. **Real-time Control**
         - Bi-directional communication using the `useMqtt` hook.
         - Centralized device logic in `src/lib/devices.ts`.

      3. **Dashboard UI**
         - "Industrial Dark" aesthetics with glassmorphism.
         - Custom components: `DeviceSwitch`, `DeviceSlider`, `TempSensor`, and `TempChart`.

      **MQTT Topics Structure**

      All topics follow the standard: `home/[room]/[device]`.

   .. tab-item:: Português

      O projeto evoluiu de uma simples monitorização local para uma interface web centralizada para monitorizar e controlar múltiplos nodos IoT usando o protocolo **MQTT**.

      **Visão Geral do Projeto**

      O objetivo é fornecer um dashboard com estética industrial premium para controlo em tempo real.

      **Stack Tecnológica**

      - **Framework:** Next.js 16 (App Router)
      - **Linguagem:** TypeScript
      - **Estilização:** Tailwind CSS v4 (com Geist Mono)
      - **Autenticação:** NextAuth.js (Google Provider)
      - **Comunicação:** MQTT (protocolo leve para IoT)
      - **Deploy:** Vercel

      **Funcionalidades Implementadas**

      1. **Segurança & Acesso**
         - Autenticação robusta via Google (NextAuth.js).
         - Proteção por middleware para rotas e APIs.
         - Acesso restrito via whitelist de email.

      2. **Controlo em Tempo Real**
         - Comunicação bi-direcional usando o hook `useMqtt`.
         - Lógica de dispositivos centralizada em `src/lib/devices.ts`.

      3. **Interface do Dashboard**
         - Estética "Industrial Dark" com glassmorphism.
         - Componentes customizados: `DeviceSwitch`, `DeviceSlider`, `TempSensor`, e `TempChart`.

      **Estrutura de Tópicos MQTT**

      Todos os tópicos seguem o padrão: `home/[room]/[device]`.

Arduino Code
------------

The following code demonstrates how the Arduino Nano ESP32 connects to the MQTT broker and handles commands:

.. literalinclude:: ../../smart-home.txt
   :language: cpp
   :linenos:
