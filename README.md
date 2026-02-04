<div align="center">
  <!-- Sube tu logo a la carpeta assets o usa un placeholder -->
  <!-- <img src="./assets/logo-tenlolisto.png" alt="TenloListo Logo" width="150" /> -->

  <h1>TenLoListo 🚀</h1>
  
  <h3>Plataforma SaaS & Marketplace para la Transformación Digital en Cuba</h3>

  <p>
    <b>B2B/B2C Solution • Next.js 15 • React 19 • Supabase • TypeScript</b>
  </p>

  <p>
    <a href="https://tenlolisto.com">🌐 Live Demo (Website)</a> • 
    <a href="#-tech-stack">🛠️ Tech Stack</a> • 
    <a href="#-technical-highlights">💡 Case Study</a>
  </p>

  <!-- Badges de estado y tecnologías -->
  <img src="https://img.shields.io/badge/Status-Active_Development_(65%25)-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Next.js-15.2-black?style=for-the-badge&logo=next.js&logoColor=white" />
  <img src="https://img.shields.io/badge/TypeScript-Strict-blue?style=for-the-badge&logo=typescript&logoColor=white" />
  <img src="https://img.shields.io/badge/Database-Supabase_(Postgres)-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white" />
</div>

---

## 🎯 Sobre el Proyecto

**TenLoListo** es una solución integral diseñada para conectar negocios locales con usuarios, permitiendo descubrir productos, servicios y eventos de manera intuitiva. No es solo un directorio; es un **SaaS completo** que empodera a los negocios para gestionar su presencia digital.

> **Nota Técnica:** Este repositorio documenta la arquitectura y el progreso del proyecto (`tenlolistocore`), cuyo código fuente es privado por razones comerciales.

### El Ecosistema Dual
1.  **Para Negocios (SaaS B2B):** Dashboard administrativo para gestión de inventario, activación/desactivación de productos, creación de eventos con tickets QR y analíticas.
2.  **Para Usuarios (Marketplace B2C):** Bazar digital con sistema de búsqueda, reservas, billetera virtual y social features.

---

## 🛠️ Tech Stack & Arquitectura

El proyecto está construido sobre el "Bleeding Edge" del ecosistema React, priorizando rendimiento y UX.

| Capa | Tecnologías Clave |
|------|-------------------|
| **Frontend Core** | **Next.js 15.2.4** (App Router), **React 19**, TypeScript (94% del código) |
| **UI System** | Tailwind CSS, Radix UI, Shadcn/ui, Lucide React |
| **Backend / DB** | **Supabase** (PostgreSQL, Auth, Edge Functions, Realtime) |
| **State & Forms** | React Context API, React Hook Form + Zod, Custom Hooks consolidados |
| **Features Pro** | Generación de PDFs, QR Codes, Optimización de Imágenes Custom ($0 cost) |

```mermaid
graph TD
    User[👤 Usuario / Negocio] -->|HTTPS| Next[⚡ Next.js 15 Frontend]
    
    subgraph "Core Services"
        Next -->|Auth & RLS| Auth[🔐 Supabase Auth]
        Next -->|Data Fetching| DB[(🐘 PostgreSQL)]
        Next -->|Media| Storage[📂 Bucket Imágenes]
    end
    
    subgraph "Logic Modules"
        DB -->|Trigger| Wallet[💰 Wallet System]
        DB -->|Dynamic Config| Subs[🔄 Subscription Engine]
    end

    Wallet -->|Update Balance| DB
