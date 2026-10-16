# PRD — Site Institucional WhuTech

## Problem statement (resumo)
Site institucional completo da WhuTech (Ibaté — SP): desenvolvimento/reparação de sites, soluções NFC (placas, cardápios, projetos personalizados), sistemas, manutenção de software/hardware, suporte técnico e consultoria. Objetivo: converter visitantes em clientes via WhatsApp oficial (https://wa.me/qr/HXWHPCCA6DXKB1) e formulário de orçamento. Conteúdo em pt-BR, sem dados inventados.

## Decisões do usuário (discovery)
- Formulário de orçamento: salvar no banco de dados + orientar conclusão pelo WhatsApp oficial (nunca simular envio).
- Catálogo de serviços: página única com abas (9 categorias).

## Arquitetura
- Frontend: React + Tailwind + shadcn/ui (tabs, accordion, sheet, select, sonner), componentes em /app/frontend/src/components.
- Backend: FastAPI em /app/backend/server.py — POST/GET /api/orcamentos (MongoDB).
- Logos oficiais em /app/frontend/public/assets (otimizadas 640px) + favicon.png.
- Paleta oficial: #030712 / #07152B / #111827 / #0866FF / #168BFF / #30394A / #F5F7FC / #A8B2C3. Fontes: Manrope (títulos) + Inter (texto).

## Implementado (2026-10-16)
- Header fixo glassmorphism com 7 links + CTA WhatsApp; menu mobile em Sheet.
- Hero com logo completa, título/subtítulo oficiais, 2 CTAs, tags de especialidades.
- Faixa de 4 diferenciais.
- Catálogo com 9 abas completas (O que é / Como funciona / O que podemos fazer / Exemplo prático / Personalização / Como contratar / CTA WhatsApp) com disclaimers honestos.
- Seção "Como trabalhamos" (4 etapas com linha conectora).
- Sobre nós (Wendrew Soares e Hugo Manoel, sem cargos inventados).
- Formulário de orçamento persistido em MongoDB + handoff honesto para WhatsApp.
- FAQ com 13 perguntas em acordeão.
- Contato (WhatsApp, e-mail, Ibaté—SP) + rodapé completo com ano automático.
- Botão flutuante WhatsApp com aria-label.
- SEO: título, description, Open Graph, favicon, lang pt-BR.
- Animações de entrada (IntersectionObserver), prefers-reduced-motion respeitado, data-testids em todos os interativos.

## Verificado
- POST/GET /api/orcamentos OK; 7 links wa.me todos com o link oficial exato; abas ativadas por menu desktop e mobile; FAQ abre; formulário registra e exibe orientação WhatsApp; layout mobile 390px OK.

## Backlog
- P0: nenhum pendente.
- P1: painel administrativo para a WhuTech visualizar os pedidos de orçamento registrados (requer auth).
- P1: política de privacidade/LGPD em página própria.
- P2: blog/cases quando houver projetos reais para exibir (sem inventar).
- P2: versão das logos com fundo transparente (solicitar ao proprietário para eliminar o blend de tela).

## Credenciais
- Sem autenticação no site (ver /app/memory/test_credentials.md — vazio intencionalmente).
