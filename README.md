# 🍽️ Plato Solidario

**Plataforma tecnológica de logística social y distribución de raciones de almuerzo no reclamadas**

Proyecto de investigación — Ingeniería de Software 1
Universidad de Pamplona | Facultad de Ingenierías y Arquitectura

## 📋 Descripción

Plato Solidario es la especificación de una plataforma tecnológica (app móvil + panel web) que **intercepta y redistribuye en tiempo real** las raciones de almuerzo **ya adquiridas por estudiantes** que, por algún motivo, no pueden ir a reclamarlas ese día.

En lugar de que esa ración se pierda, el sistema la pone a disposición de otro estudiante que ese día **no cuenta con almuerzo**. Es un modelo de solidaridad entre la misma comunidad estudiantil: quien pagó su servicio pero no lo usa un día, le da la oportunidad a otro de aprovecharlo.

El sistema opera bajo una **ventana crítica de 30 minutos** (2:00 PM – 2:30 PM), liberando automáticamente el inventario de raciones no reclamadas y permitiendo que los estudiantes interesados reserven una bajo política *First-Come, First-Served* (FCFS), validando la entrega mediante códigos QR dinámicos con expiración controlada.

## ✨ Características principales

- 🔐 **Autenticación institucional** vía OAuth2, restringida a correos `@unipamplona.edu.co`
- ⚡ **Liberación automática de inventario** a las 2:00 PM en punto
- 🔔 **Notificaciones push masivas** entregadas en menos de 10 segundos
- 🎯 **Reservas bajo política FCFS** con control de concurrencia mediante Redis (operaciones atómicas)
- 📱 **Códigos QR dinámicos** con vigencia máxima de 15 minutos, firmados con JWT (RS256)
- 📊 **Tablero analítico** con métricas de impacto y reducción de desperdicio en tiempo real
- 🛡️ Cumplimiento de la **Ley 1581 de 2012** (protección de datos personales en Colombia)

## 🏗️ Arquitectura

El sistema sigue un modelo de contenedores (C4) compuesto por:

| Componente | Tecnología propuesta |
|---|---|
| App Móvil | iOS / Android (Firebase Cloud Messaging) |
| Panel Web | SPA para operarios y administradores |
| API Gateway / Backend | Node.js (Fastify) o Go |
| Caché de inventario | Redis (operaciones atómicas `DECR`) |
| Base de datos persistente | PostgreSQL 15+ |
| Mensajería push | Firebase Cloud Messaging (FCM) |

## 📄 Contenido del repositorio

- [`PlatoSolidario_SOFT.pdf`](./PlatoSolidario_FINAL.pdf) — Documentación completa del proyecto: SRS, SAD, diseño, diccionario de datos, plan de pruebas y bibliografía.

## 📚 Documentos incluidos

1. Introducción y marco de trabajo (objetivos y alcance)
2. Requerimientos del software (SRS) — funcionales, no funcionales y matriz de trazabilidad
3. Arquitectura de software (SAD) — diagrama C4 y decisiones de arquitectura (ADR)
4. Diseño del software — diagrama de clases y contratos de API
5. Construcción de software — script DDL y diccionario de datos
6. Pruebas de software — plan de pruebas, casos de prueba y cobertura de código
7. Bibliografía y referencias

## 👤 Autora

**Estefany Dayana Vela Rangel**
Programa de Ingeniería de Software
Universidad de Pamplona — 2026

## 📌 Estado del proyecto

📝 Fase de documentación y especificación (sin implementación de código fuente).
