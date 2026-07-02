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
         - Google OAuth consent screen kept in **Testing** mode, with only authorized family email addresses listed as test users — any Google account not on the list is blocked at the OAuth level before even reaching the application.
         - Authorized redirect URIs in Google Cloud Console are scoped exclusively to the production domain, preventing OAuth flows from being initiated from unauthorized origins or third-party environments.

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
         - O ecrã de consentimento OAuth do Google mantido em modo **Testing**, com apenas os emails da família autorizados como utilizadores de teste — qualquer conta Google que não esteja na lista é bloqueada ao nível do OAuth, antes sequer de chegar à aplicação.
         - Os URIs de redirecionamento autorizados na Google Cloud Console estão configurados exclusivamente para o domínio de produção, impedindo que fluxos OAuth sejam iniciados a partir de origens não autorizadas ou ambientes externos.

      2. **Controlo em Tempo Real**

         - Comunicação bi-direcional usando o hook `useMqtt`.
         - Lógica de dispositivos centralizada em `src/lib/devices.ts`.

      3. **Interface do Dashboard**

         - Estética "Industrial Dark" com glassmorphism.
         - Componentes customizados: `DeviceSwitch`, `DeviceSlider`, `TempSensor`, e `TempChart`.

      **Estrutura de Tópicos MQTT**

      Todos os tópicos seguem o padrão: `home/[room]/[device]`.

User Interface
--------------

.. tab-set::

   .. tab-item:: English

      Below you can see the login page on the left and the main user interface on the right. Access is secure, and the main interface allows you to manage devices and monitor the system in real-time.

      .. list-table:: 
         :widths: 30 70
         :class: borderless

         * - .. image:: images/Login_Page.png
               :width: 95%
               :alt: Login Page

           - .. image:: images/Main_Page.png
               :width: 100%
               :alt: Main Page

   .. tab-item:: Português 

      Abaixo podes ver a página de login à esquerda e a interface principal do utilizador à direita. O acesso é seguro e a interface principal permite gerir os dispositivos e monitorizar o sistema em tempo real.

      .. list-table:: 
         :widths: 30 70
         :class: borderless

         * - .. image:: images/Login_Page.png
               :width: 95%
               :alt: Página de Login

           - .. image:: images/Main_Page.png
               :width: 100%
               :alt: Página Principal

Arduino Code
------------

The following code demonstrates how the Arduino Nano ESP32 connects to the MQTT broker and handles commands:

.. literalinclude:: code/smart-home.txt
   :language: cpp
   :linenos: