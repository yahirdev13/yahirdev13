<div align="center">

```
██╗   ██╗ █████╗ ██╗  ██╗██╗██████╗     ██████╗ ███████╗██╗   ██╗
╚██╗ ██╔╝██╔══██╗██║  ██║██║██╔══██╗    ██╔══██╗██╔════╝██║   ██║
 ╚████╔╝ ███████║███████║██║██████╔╝    ██║  ██║█████╗  ██║   ██║
  ╚██╔╝  ██╔══██║██╔══██║██║██╔══██╗    ██║  ██║██╔══╝  ╚██╗ ██╔╝
   ██║   ██║  ██║██║  ██║██║██║  ██║    ██████╔╝███████╗ ╚████╔╝ 
   ╚═╝   ╚═╝  ╚═╝╚═╝  ╚═╝╚═╝╚═╝  ╚═╝    ╚═════╝ ╚══════╝  ╚═══╝  
```

### Yahir Díaz · Full-Stack Engineer

**I build the software companies run on: ERP integrations, multi-tenant SaaS and internal tools.**<br>
*AI writes code fast. I make sure it holds up in production.*

[![Portfolio](https://img.shields.io/badge/Portfolio-yahirdiaz--dev.vercel.app-0B1626?style=for-the-badge&logo=vercel&logoColor=white)](https://yahirdiaz-dev.vercel.app)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-yahirdev13-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/yahirdev13)
[![Email](https://img.shields.io/badge/Email-yahir.dev13-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:yahir.dev13@gmail.com)
![AI-native](https://img.shields.io/badge/AI--native-Claude_Code-D97757?style=for-the-badge&logo=claude&logoColor=white)

**Shipping to production since 2022** · **15+ client deliveries at Tersoft** · **Cuernavaca, Mexico 🇲🇽**

</div>

---

## 👋 About me

Full-Stack Engineer at **Tersoft** since December 2024. There I co-built and now maintain **SageConnect**, my largest system, and ship ERP work on SAGE 300 and Odoo. As an independent I build products for small businesses: a workshop ERP, a SaaS for cleaning agencies (co-developed) and websites for a clinic and a gym.

I work AI-native: **Claude Code** is my daily engine, and specs, hard rules and CI keep its output correct. I care about what happens after the deploy: fewer manual steps, fewer errors, and systems people use without asking for help.

```ts
const yahir = {
  role: "Full-Stack Engineer @ Tersoft",
  basedIn: "Cuernavaca, Mexico · UTC−6",
  stack: ["TypeScript", "React", "Next.js", "Node.js", "PostgreSQL", "SQL Server"],
  integrations: ["SAGE 300", "Odoo", "CFDI 4.0", "Stripe"],
  engine: "Claude Code + specs, tests and CI",
  shippingSince: 2022,
};
```

---

## ⭐ Featured · SageConnect, my largest system

> **Co-builder, from design to code · sole maintainer since May 2026**
>
> An always-on integration between **SAGE 300** and a **supplier portal**. Invoices, purchase orders, payments and payment complements move on their own, for several companies at once, each with its own database.

```mermaid
flowchart LR
    clock["⏱️ Clock<br/>every 15 min"] --> lock{"🔒 Lock<br/>one cycle at a time"}
    button["▶️ Run now<br/>button"] --> lock
    lock -- busy --> skip["⏭️ Skipped"]
    lock -- free --> cycle
    subgraph cycle ["For each company · 7 steps · 5 min limit each"]
        direction LR
        down["Portal → company<br/>suppliers · invoices"] --> up["SAGE → portal<br/>payments · purchase orders"]
    end
    cycle --> sage[("📥 Import into<br/>SAGE 300")]
```

- 🔒 **One lock** shared by the scheduler and the Run now button, so two cycles never overlap. It frees itself at 14 minutes, one before the next cycle.
- ⏱️ **Every wait has a ceiling:** a portal call gives up at 30 s, a step at 5 min, the import into SAGE at 10 min.
- ♻️ **Retries without duplicates:** failed payments (every 30 min) and purchase orders (every 4 h) from the last 30 days get another try, and an order that already reached the portal is reconciled, not created twice.
- 📊 **20k lines** of JavaScript and **64 test files** on main, with **300+ of my commits** in the public repo.

`Node.js` `Express` `SQL Server` `Jest` · **[Read the case study →](https://yahirdiaz-dev.vercel.app/work/sageconnect)** · **[View the repo →](https://github.com/FReptar0/sageconnect)**

---

## 🗂️ Projects

| | Project | What it does | My role | Stack | Status |
|:-:|---|---|---|---|---|
| ⭐ | **[SageConnect](https://yahirdiaz-dev.vercel.app/work/sageconnect)** | Syncs SAGE 300 with a supplier portal for several companies, every 15 minutes | Co-builder · sole maintainer | Node.js · Express · SQL Server | 🟢 In production since 2023 |
| 🏭 | **[SageSync](https://yahirdiaz-dev.vercel.app/work/sagesync)** | Keeps a mining operation's warehouse stock in Fracttal in step with SAGE 300, three times a day | Sole developer since May 2026 | Node.js · SQL Server · Fracttal API | 🟢 In production |
| 💰 | **[Commission engine](https://yahirdiaz-dev.vercel.app/work/commission-engine)** | Odoo 18 module that turns a distributor's invoices into monthly sales commissions | Lead developer | Odoo · Python · PostgreSQL | 🟢 In production since Apr 2026 |
| 🔧 | **Pegasus — Workshop OS** | ERP/CRM for a family auto-repair shop: service-order state machine, atomic folios, row-level security | Built end to end | Next.js · TypeScript · Prisma · Supabase | 🟡 v0.4 · preparing go-live |
| 🧹 | **Cleany** | Multi-tenant SaaS for cleaning agencies: crew scheduling, Stripe billing, QR + PIN sign-in | Co-developer | React · Fastify · PostgreSQL · Stripe | 🟢 Live |
| 🏋️ | **A&D Fitness Center** | Gym website plus the coaching system behind it: routines, meal plans and progress | End to end | HTML · CSS · JavaScript | 🟢 In use |
| 🩺 | **[Clínica Biomotion](https://clinica-integral-biomotion.vercel.app)** | Website redesign for an integrated health clinic, with booking by WhatsApp | End to end | HTML · CSS · JavaScript | 🟢 Live |
| 📱 | **[Finite](https://finite-app-seven.vercel.app)** | iPhone lock-screen wallpapers with life metrics and countdowns, rendered server-side | Side project | Next.js · Satori | 🟢 Live |

---

## 🤖 How I work with AI

| 01 · Discuss | 02 · Plan | 03 · Execute | 04 · Verify |
|---|---|---|---|
| Pin down scope and gray areas with the people who will use it, before any code. | Every phase gets a plan with verification criteria. The agent does not improvise. | Claude Code implements on short branches, with atomic, traceable commits. | Types, lint and tests green, and I review every change against the plan. |

**What I don't delegate:** the data model · money and tax rules · what not to build · the final review.

---

## 💼 Experience

**Full-Stack Engineer · Tersoft** — *Dec 2024 – present*<br>
SageConnect, SageSync and the commission engine; 15+ Odoo implementations for manufacturing, distribution, retail, logistics and healthcare clients; a standard Odoo.sh deployment pipeline that cut client onboarding from weeks to days.

**Full-Stack Engineer · Independent** — *2022 – present*<br>
Products for small businesses: Pegasus, Cleany, Clínica Biomotion and A&D Fitness.

**Web Developer · Jardines de México** — *May – Sep 2023*<br>
A CFDI e-invoicing system in React, and accounting workflows moved from Excel to a web app.

🎓 **B.Eng. in Software Development & Management** — Universidad Tecnológica Emiliano Zapata (UTEZ), 2025

---

## 🛠️ Stack

**Languages**<br>
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)

**Frontend**<br>
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![Preact](https://img.shields.io/badge/Preact-673AB8?style=flat-square&logo=preact&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)

**Backend & APIs**<br>
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)
![Fastify](https://img.shields.io/badge/Fastify-000000?style=flat-square&logo=fastify&logoColor=white)

**Data**<br>
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=flat-square)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=flat-square&logo=prisma&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white)

**Integrations**<br>
![SAGE 300](https://img.shields.io/badge/SAGE_300-00A651?style=flat-square)
![Odoo](https://img.shields.io/badge/Odoo-714B67?style=flat-square&logo=odoo&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-635BFF?style=flat-square&logo=stripe&logoColor=white)
![CFDI 4.0](https://img.shields.io/badge/CFDI_4.0-006847?style=flat-square)

**Quality & delivery**<br>
![Jest](https://img.shields.io/badge/Jest-C21325?style=flat-square&logo=jest&logoColor=white)
![Vitest](https://img.shields.io/badge/Vitest-6E9F18?style=flat-square&logo=vitest&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=flat-square)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white)

**AI**<br>
![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=flat-square&logo=claude&logoColor=white)
![Gemini API](https://img.shields.io/badge/Gemini_API-8E75B2?style=flat-square&logo=googlegemini&logoColor=white)

---

## 📫 Contact

<div align="center">

[![Portfolio](https://img.shields.io/badge/Portfolio-yahirdiaz--dev.vercel.app-0B1626?style=for-the-badge&logo=vercel&logoColor=white)](https://yahirdiaz-dev.vercel.app)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-yahirdev13-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/yahirdev13)
[![Email](https://img.shields.io/badge/Email-yahir.dev13-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:yahir.dev13@gmail.com)

Happy to talk about integrations, SaaS or shipping with AI.

</div>

<details>
<summary><b>🇲🇽 Versión en español</b></summary>

<br>

**Yahir Díaz · Full-Stack Engineer.** Construyo el software con el que operan las empresas: integraciones con ERPs, SaaS multi-tenant y herramientas internas. *La IA escribe código rápido; yo me encargo de que funcione en producción.*

Full-Stack Engineer en **Tersoft** desde diciembre de 2024. Ahí co-construí y hoy mantengo **SageConnect**, mi sistema más grande, y entrego proyectos de ERP sobre SAGE 300 y Odoo. Por mi cuenta hago productos para negocios pequeños: un ERP para un taller, un SaaS para agencias de limpieza (co-desarrollado) y sitios para una clínica y un gimnasio. Trabajo con IA todos los días: Claude Code es mi motor, y uso specs, reglas duras y CI para que lo que produce sea correcto.

| | Proyecto | Qué hace | Mi rol | Estado |
|:-:|---|---|---|---|
| ⭐ | **[SageConnect](https://yahirdiaz-dev.vercel.app/es/work/sageconnect)** | Sincroniza SAGE 300 con un portal de proveedores para varias empresas, cada 15 minutos | Co-builder · único maintainer | 🟢 En producción desde 2023 |
| 🏭 | **[SageSync](https://yahirdiaz-dev.vercel.app/es/work/sagesync)** | Mantiene el inventario de una operación minera igual en Fracttal que en SAGE 300, tres veces al día | Desarrollador único desde mayo de 2026 | 🟢 En producción |
| 💰 | **[Motor de comisiones](https://yahirdiaz-dev.vercel.app/es/work/commission-engine)** | Módulo de Odoo 18 que convierte las facturas de una distribuidora en las comisiones mensuales de sus vendedores | Desarrollador principal | 🟢 En producción desde abril de 2026 |
| 🔧 | **Pegasus — Workshop OS** | ERP/CRM para un taller mecánico familiar: máquina de estados de órdenes, folios atómicos y row-level security | De punta a punta | 🟡 v0.4 · por salir |
| 🧹 | **Cleany** | SaaS multi-tenant para agencias de limpieza: programación de cuadrillas, cobro con Stripe y acceso con QR + PIN | Co-desarrollador | 🟢 En vivo |
| 🏋️ | **A&D Fitness Center** | Sitio de un gimnasio y el sistema de entrenamiento detrás: rutinas, dietas y progreso | De punta a punta | 🟢 En uso |
| 🩺 | **[Clínica Biomotion](https://clinica-integral-biomotion.vercel.app)** | Rediseño del sitio de una clínica integral, con citas por WhatsApp | De punta a punta | 🟢 En vivo |
| 📱 | **[Finite](https://finite-app-seven.vercel.app)** | Fondos de pantalla para iPhone con métricas de vida y cuentas regresivas | Proyecto personal | 🟢 En vivo |

**Cómo trabajo con IA:** discutir → planear → ejecutar → verificar, una fase a la vez. El modelo de datos, las reglas de dinero, lo que no se construye y la revisión final son míos.

**Portafolio en español:** [yahirdiaz-dev.vercel.app/es](https://yahirdiaz-dev.vercel.app/es)

</details>
