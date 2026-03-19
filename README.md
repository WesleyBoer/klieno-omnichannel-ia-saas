# Klieno — Plataforma SaaS de Atendimento Omnichannel com IA

Plataforma própria (SaaS) que centraliza WhatsApp, Instagram, Messenger, Telegram e chat widget em um único dashboard inteligente. Orquestra atendimento híbrido IA + humano com triagem automática, análise de sentimento, escalonamento inteligente e relatórios qualitativos gerados por IA.

**Projeto próprio** — código-fonte privado. Este repositório serve apenas como showcase técnico e referência para o case study detalhado.

## Problema Resolvido

Empresas perdem tempo e clientes alternando entre apps de mensagens.  
Klieno elimina isso com:

- Hub omnichannel unificado
- Pipeline híbrido IA-humano (triagem, roteamento, auto-respostas)
- Análise de sentimento em tempo real → escalonamento automático para agente humano
- Base de conhecimento com RAG (respostas precisas, sem alucinações)
- Atendimento por voz direto no navegador (OpenAI Realtime API)
- Analytics qualitativos automáticos (sumários de conversas, relatórios por e-mail)

## Stack Tecnológico Principal

**Frontend**  
Next.js 16 · React · TypeScript · Tailwind CSS · shadcn/ui  
Vite (chat widget embarcável)

**Monorepo & Build**  
Turborepo (3 pacotes: dashboard, widget, backend)

**Backend & Dados**  
Convex (serverless, realtime DB, subscriptions, filas, cron jobs) — 20+ tabelas

**Inteligência Artificial**  
OpenAI:  
- gpt-5-nano (triagem inicial)  
- gpt-4o-mini (decisão + análise de sentimento — 5 estados)  
- gpt-4.1-mini (respostas personalizadas)  
- gpt-5-mini (analytics assíncronos)  
- text-embedding-3-small (RAG / embeddings)  
- Realtime API (voz STT + TTS + VAD)  
Google Gemini (fallback multimodal)

**Canais Integrados**  
WhatsApp Cloud API · Instagram Graph API · Messenger Platform · Telegram · Chat Widget (Vite — captura contexto silencioso)

**Autenticação & Pagamentos**  
Clerk (auth + billing multi-tenant) · Stripe (assinaturas SaaS)

**Outros**  
Resend (relatórios por e-mail) · Sentry (monitoramento) · Jest + React Testing Library

## Destaques Técnicos e Decisões de Arquitetura

- **Pipeline multi-modelo otimizado por custo** — modelo mais barato para cada etapa
- **RAG + base de conhecimento vetorial** — respostas contextualizadas e precisas
- **Análise de sentimento contextual** (histórico completo, não só última mensagem)
- **Cache semântico SHA256** — respostas instantâneas para perguntas recorrentes
- **Validação HMAC-SHA256** em todos webhooks Meta
- **Widget com captura silenciosa de contexto** (página, dispositivo, idioma…)
- **Arquitetura multi-tenant** — isolamento total por organização
- **Atendimento por voz no navegador** — sem VoIP externo
- **11 Cron Jobs** para automações periódicas
- **Monorepo com Turborepo** — build rápido e dependências orquestradas

## Métricas Técnicas Principais

- Modelos OpenAI integrados: **6**
- Canais suportados: **5**
- Funcionalidades principais: **18**
- Cron Jobs: **11**
- Tabelas Convex: **20+**
- Estados emocionais detectados: **5**
- Desfechos automáticos por conversa: **3** (AUTO_REPLY, ESCALATE, RESOLVE)

## Links e Recursos

- Case study completo com diagramas de arquitetura, pipeline de mensagens (5 fases), pipeline RAG (5 fases), exemplos de análise de sentimento e mais:  
  👉 https://wboer.dev/project/klieno

Projeto próprio — código-fonte confidencial. Detalhes adicionais disponíveis em entrevistas ou calls técnicas.

Tecnologias chave: Next.js · Convex · Turborepo · OpenAI multi-modelo · RAG · omnichannel · WhatsApp Cloud API · Stripe · Clerk · atendimento IA · chatbot híbrido
