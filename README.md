# Taller RAG: Vanguardia V1 con Spring Boot y Groq

![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.5-brightgreen.svg?logo=springboot)
![Java 17](https://img.shields.io/badge/Java-17%2B-blue.svg?logo=java)
![Groq](https://img.shields.io/badge/AI-Groq%20API-orange.svg)
![Llama 3](https://img.shields.io/badge/LLM-Llama_3.3_70B-purple.svg)

Este repositorio contiene la entrega técnica del taller sobre integración de **Generación Aumentada por Recuperación (RAG)**. Se utiliza como base una arquitectura Java/Spring Boot (EduRAG-Groq) conectada a un Modelo de Lenguaje de Gran Escala (LLM) alojado en Groq, todo esto contextualizado en torno a nuestro proyecto de aula web **"Vanguardia V1"**.

## 🎯 Objetivo de la Actividad
El propósito es dotar de inteligencia situacional a un asistente de IA mediante arquitectura RAG. En lugar de ofrecer respuestas genéricas e incurrir en "alucinaciones", el chatbot es capaz de responder preguntas técnicas sobre la arquitectura React, flujos de reserva, investigación de operaciones paramétricas y la base de datos de nuestro prototipo *Vanguardia V1*, basándose estrictamente en una base de conocimientos documentales.

## 🛠️ Modificaciones y Niveles Alcanzados
Este fork del proyecto base ha sido ajustado y escalado cumpliendo con los niveles solicitados en el taller:

- **Nivel 1 (Base Documental):** Múltiples `.txt` inyectados en `src/main/resources/documents/` parametrizando flujos de trabajo sobre negocios locales, react *states*, e investigación de operaciones.
- **Nivel 2 (Chunk Size):** Parametrización en el motor de indexado, escalando fragmentos a 600 caracteres para asegurar que el modelo reciba sentencias completas.
- **Nivel 3 (Top-K Adjust):** El motor ahora recupera el Top 5 de piezas informativas (`retrievalService.retrieve`) para elevar la precisión al concatenar el contexto.
- **Nivel 4 (Upgrade de Cerebro):** Migración oficial en `application.properties` para consumir **`llama-3.3-70b-versatile`**, garantizando respuestas más analíticas e inferenciales orgánicamente.

## 🚀 Cómo Ejecutar el Proyecto
1. Clona este repositorio:
   ```bash
   git clone https://github.com/DiexoDev/taller-rag-vanguardia.git
   ```
2. Establece tu API Key de Groq. Obtén la tuya gratuitamente desde [Groq Console](https://console.groq.com/keys) y configura la variable de entorno local:
   ```bash
   export GROQ_API_KEY="gsk_TuLlaveSecretaAca" # En linux/Mac
   set GROQ_API_KEY="gsk_TuLlaveSecretaAca"    # En cmd de Windows
   ```
3. Ejecuta el entorno mediante Maven o usando tu IDE favorito (IntelliJ / Eclipse):
   ```bash
   ./mvnw spring-boot:run
   ```
4. Navega a `http://localhost:8080`, ingresa tus consultas en el chat y el asistente usará recuperación RAG para informarte sobre Vanguardia V1.

## 📄 Documentación Técnica Completa
Para ver el paso a paso detallado, capturas y captación de errores, puedes revisar la documentación de nuestro equipo alojada en [INFORME_TECNICO.md](./INFORME_TECNICO.md) ubicado en la raíz del proyecto.
