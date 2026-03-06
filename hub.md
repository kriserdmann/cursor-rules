# 🚀 Hub Local Jaraguá & Spotal OS

## 🎯 Objetivo (UVP)
Desenvolver uma infraestrutura digital hiperlocal para gerenciar a descoberta de eventos e serviços em Jaraguá do Sul, SC, integrando um diretório inteligente (Hub) com um gerador de mini-sites (Spotal).

- **Missão:** Furar as bolhas das redes sociais e centralizar a utilidade da cidade em um só lugar.
- **Valor:** Permitir que profissionais locais sejam encontrados sem depender de algoritmos de entretenimento.

---

## 🛠️ Tech Stack
- **Next.js 15 (App Router):** Frontend e API Routes hospedados na Vercel.
- **TailwindCSS 4:** UI moderna, limpa e baseada em Bento Grids.
- **Supabase:** Autenticação, Banco de Dados PostgreSQL (com RLS) e Storage.
- **OpenRouter / OpenAI API:** Parser de IA para transformar posts em dados estruturados.
- **WhatsApp Business API (Meta):** Interface de conversação e concierge.
- **Leaflet.js:** Mapas interativos para localização de prestadores.

---

## 🏗️ Visão Geral da Arquitetura
O projeto opera como um monorepo compartilhado:

hub-jaragua-monorepo/
├── hub-portal/      # Diretório de descoberta (Next.js 15)
├── spotal-engine/   # Gerador de mini-sites SaaS (Next.js 15)
├── shared/          # Tipos TypeScript e Utils compartilhados
└── supabase/         # Migrations, Edge Functions e Seeds

---

## 📌 Funcionalidades Chave (MVP)

### 1. Diretório de Serviços & Eventos (Hub)
- Busca inteligente por bairros de Jaraguá (Centro, Rau, Baependi, etc.).
- Filtros por "Aberto Agora", "Verificado" e "Urgência".
- Cards de perfil integrados: Foto, Descrição gerada por IA e botão para WhatsApp.

### 2. Spotal Engine (Micro-SaaS)
- Criação instantânea de páginas profissionais para MEIs a partir de dados do Hub.
- Dashboard para o profissional editar horários, serviços e ver métricas.
- Exportação de QR Code para balcões físicos em Jaraguá.

### 3. Concierge WhatsApp (IA)
- Interface de chat onde o morador pergunta "Onde tem eletricista?" e recebe o link.
- Automação de "Agenda da Semana" enviada toda quinta-feira às 18h.

### 4. IA Ingestion (Parser)
- Crawler/Scraper que lê textos brutos de redes sociais e alimenta o Supabase.
- Deduplicação de eventos baseada em data e local.

---

## 📐 Design Patterns & XP Protocol
- **TDD Exigido:** Todo parser de IA e lógica deve ter testes (Ratio alvo: 1.5x).
- **Small Releases:** Commits frequentes, cada um sendo production-ready.
- **Bento Grid Layout:** Interface modular, mobile-first, inspirada em dashboards.
- **Single Source of Truth:** Dados do Spotal e Hub integrados via DB Realtime.

---

## 🔐 Variáveis de Ambiente
NEXT_PUBLIC_SUPABASE_URL="https://your-id.supabase.co"
NEXT_PUBLIC_SUPABASE_ANON_KEY="your-key"
OPENAI_API_KEY="sk-..."
JARAGUA_COORDINATES="-26.4842,-49.0792"

---

## 📅 Pipeline Semanal & Jobs
- **Segunda 08h:** Limpeza de dados obsoletos e backup do DB.
- **Quinta 18h:** Disparo do informativo "O que fazer no FDS" via WhatsApp.
- **Diário:** Sincronização de novos profissionais entre Spotal e Hub.

---

## ⚠️ Common Hurdles (Obstáculos Comuns)
- **Ambiguidade Geográfica:** IA deve sempre assumir Jaraguá do Sul.
- **Vibe Coding vs Engineering:** Não aceitar código sem tratamento de erro ou loading states.
- **Custo de API:** Usar cache agressivo (Next.js ISR) para evitar chamadas redundantes.

---

## 👥 Público-Alvo (Jaraguá do Sul)
- **Moradores:** Buscando serviços confiáveis e eventos sem ruído.
- **MEIs e Profissionais:** Presença digital profissional sem esforço de conteúdo.
- **Loomine Arte & Design:** Agência validadora e principal canal de vendas.

---

## 🚀 Roadmap de Desenvolvimento
- [ ] Setup Inicial (Next.js 15 + Tailwind 4 + Supabase)
- [ ] Schema de Banco de Dados (Negócios, Eventos, Bairros)
- [ ] Engine de Parsing de IA (Texto -> JSON Estruturado)
- [ ] Portal Hub (Home + Busca + Cards)
- [ ] Integração WhatsApp (Bot Concierge)
- [ ] MVP Spotal (Editor de mini-sites básico)
