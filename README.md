# Propuesta de Negocio Maderoh

**Fecha:** 2025-10-21  
**Preparado por:** Gerry

## Índice de Contenidos

1. [Propósito y Estructura del Equipo](#1-propósito-y-estructura-del-equipo)
   - 1.1 [Roles y Responsabilidades](#11-roles-y-responsabilidades)
   - 1.2 [Plan de Mentoría](#12-plan-de-mentoría)
   - 1.3 [Flujo de Trabajo de Desarrollo](#13-flujo-de-trabajo-de-desarrollo)

2. [Producto 1 — Maderoh](#2-producto-1--maderoh)
   - 2.1 [Visión General](#21-visión-general)
   - 2.2 [Valor que Gerry Agregará](#22-valor-que-gerry-agregará)
   - 2.3 [Funcionalidades MVP](#23-funcionalidades-mvp)
   - 2.4 [Criterios de Aceptación](#24-criterios-de-aceptación)

3. [Producto 2 — Motor de Cursos](#3-producto-2--motor-de-cursos)
   - 3.1 [Visión General](#31-visión-general)
   - 3.2 [Valor que Gerry Agregará](#32-valor-que-gerry-agregará)
   - 3.3 [Funcionalidades MVP](#33-funcionalidades-mvp)
   - 3.4 [Criterios de Aceptación](#34-criterios-de-aceptación)

4. [Elementos Pendientes](#4-elementos-pendientes)

---

## 1. Propósito y Estructura del Equipo

Proponer una estructura de asociación clara donde:
- Gerry construye y opera el backend, infraestructura y servicios técnicos principales (B2B).
- Solkin recibe mentoría y maneja tareas de frontend e implementación.
- Yoe proporciona orientación empresarial mínima pero de alto impacto (marketing, dirección de producto, insights de clientes).

### 1.1 Roles y Responsabilidades

**Gerry (Backend)**
- Construir APIs, infraestructura, pipelines CI/CD y operaciones de producción.
- Liderar arquitectura, escalabilidad y mentorear a Solkin.
- **Entregables:** Backend MVP, monitoreo, DevOps.

**Solkin (Frontend)**
- Implementar frontend, UI/UX y pruebas unitarias de código.
- **Entregables:** Frontend MVP, mejoras UI/UX.

**Yoe (Negocios/Asesor)**
- Validación de mercado, pricing, go-to-market e introducción de clientes.
- **Entregables:** Plan comercial, leads.

### 1.2 Plan de Mentoría

- **Currículum de integración:**
  - Visión general del código base, configuración de desarrollo local, estándares de codificación, primera corrección pequeña de frontend.
  - Implementar una funcionalidad de frontend (con pair-programming y revisiones de PR).
  - Propiedad de una pequeña integración o flujo de usuario, escribir pruebas y responder a feedback de usuarios.
  - Entrega independiente de una mejora orientada al cliente.
- **Mentorías:** recorrido de arquitectura, revisión de código, orientación profesional.

### 1.3 Flujo de Trabajo de Desarrollo

- **Repo + modelo de branching:** GitFlow + CI/CD con feature-branch y despliegues automatizados
- **PR y revisión:** Template de PR, Gerry como revisor principal, mensajes descriptivos
- **CI/CD:** GitHub Actions con linters, pruebas, build y deploy automático a staging
- **Desarrollo local:** Docker compose para DB/servicios, documentación completa
- **Calidad de código:** Prettier + ESLint, pruebas automatizadas backend/frontend
- **Ambientes:** desarrollo, staging, producción con configs separadas
- **Puente Producto-Ingeniería:** proceso de requerimientos, gestión deuda técnica, releases balanceadas
- **Integración Financiera:** monitoreo costos, métricas técnicas vinculadas a KPIs, framework priorización MVP

---

## 2. Producto 1 — Maderoh

### 2.1 Visión General

Sitio de marketing público para Maderoh (muebles de madera y metal). Objetivo principal: permitir a los usuarios finales obtener estimaciones de precios automatizadas para piezas de mobiliario, luego canalizar leads a ventas (WhatsApp) o completar pago vía checkout.

Capacidades secundarias: 
- Gestión de órdenes para propietarios 
- Seguimiento de órdenes para clientes.

**Estado actual:** Yoe y Solkin manejan la producción y un sitio mínimo de leads; Solkin tiene un sitio mínimo existente que canaliza leads a WhatsApp.

### 2.2 Valor que Gerry Agregará

- Construir y operar el backend e infraestructura que impulsa las estimaciones de precios automatizadas, checkouts de pago, gestión de órdenes y seguimiento.
- Configurar un flujo de trabajo de desarrollo, mejores prácticas y CI/CD para que Solkin pueda enfocarse en frontend, UX e iteración rápida.
- Supervisar decisiones de arquitectura, ciberseguridad, monitoreo y operaciones de producción.
- Gestionar proyectos técnicos y desarrollo de funcionalidades usando herramientas de gestión de proyectos (Jira o GitHub Projects) para seguir progreso, planificación de sprints y entregables.

### 2.3 Funcionalidades MVP

1. **Páginas de marketing públicas + catálogo de productos** (páginas de contenido simples y templates de artículos)
2. **Estimador de precios:** estimador basado en formularios que calcula precio basado en opciones (materiales, dimensiones, acabados, cantidad)
3. **CTA a canal de ventas:** "Solicitar estimación" -> abrir chat de WhatsApp (deep link) + adjuntar resumen de precio estimado; opción para continuar a checkout
4. **Checkout de pago:** checkout simple de artículo único / basado en estimación (Stripe recomendado) y recibo por email
5. **Dashboard de administración (para propietarios de Maderoh):**
   - Ver leads / solicitudes de estimación
   - Ver órdenes y estados
   - Actualizar manualmente estado de orden (ej., aceptado, en producción, enviado, entregado)
6. **Seguimiento de usuario final:** página de estado de orden (con ID de orden + seguimiento simple)
7. **Seguridad básica, logging y backups**

### 2.4 Criterios de Aceptación

**MVP:**
- El estimador retorna precio determinístico para inputs de muestra.
- Los leads pueden enviar cotizaciones generados por el sitio al canal de ventas (WhatsApp).

**2da Fase:**
- Los usuarios pueden iniciar checkout y pagar exitosamente en modo de prueba; los recibos se registran.
- El admin puede ver órdenes/leads, actualizar estado, y los cambios se reflejan en el seguimiento del usuario.
- Existe despliegue de staging; producción desplegable vía CI; monitoreo básico en su lugar.

---

## 3. Producto 2 — Motor de Cursos

### 3.1 Visión General

Plataforma multitenant para cursos especializados. Objetivo: motor escalable para múltiples sitios educativos aprovechando experiencia práctica del equipo.

Capacidades secundarias:
- Seguimiento de progreso de estudiantes
- Sistema de certificaciones

**Estado actual:** Gerry mentoreando a Solkin en desarrollo web, Yoe y Solkin iniciando cursos de creación de muebles, Gerry estudiando maestría en ciberseguridad.

### 3.2 Valor que Gerry Agregará

- Construir arquitectura multitenant escalable para sitios educativos independientes.
- Desarrollar sistema de gestión de contenido, progreso y evaluaciones automatizadas.
- Implementar integraciones con pagos, certificaciones y analytics.
- Gestionar desarrollo técnico usando herramientas de project management.

### 3.3 Funcionalidades MVP

1. **Core multitenant:** sistema de tenants independientes + dashboard admin por tenant
2. **Gestión de cursos:** creador de cursos con módulos, subida multimedia, editor de texto
3. **Experiencia estudiante:** registro por tenant, navegación con progreso, notas personales
4. **Evaluaciones básicas:** quizes de opción múltiple, asignaciones, calificaciones
5. **Panel instructor:** vista de estudiantes, gestión de contenido, comunicación básica
6. **Pagos:** compra individual + suscripciones (Stripe), códigos descuento
7. **Analytics básicos:** tiempo por lección, tasas completación, puntos de abandono

### 3.4 Criterios de Aceptación

**MVP:**
- Dos tenants: "Escuela Maderoh" y "AprendeCoding" con branding independiente.
- Instructores crean cursos con 3 tipos de contenido (video, texto, quiz).

**2da Fase:**
- Estudiantes se inscriben, acceden contenido y ven progreso.
- Sistema de pagos funcional para cursos individuales.
- Dashboard admin gestiona usuarios y contenido por tenant.

---

## 4. Elementos Pendientes

### 4.1 Acciones Iniciales

- **Todos:** leer y comentar esta propuesta.
- **Decidir enfoque de compensación**
- **Confirmar compromisos de tiempo y frecuencia de syncs.**
- **Gerry + Solkin:** 
  - Redactar una hoja de ruta técnica de una página para MVP.
  - Configurar ambiente de desarrollo, acceso a GitHub y ejecutar primera build local.
- **Definir métricas de éxito para los productos propuestos**

---
