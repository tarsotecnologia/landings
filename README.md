# Tarso Landing Multi (Vercel)

Projeto com múltiplas landing pages da Tarso Tecnologia para diferentes ICPs, preparado para deploy na Vercel.

## Páginas

- `index.html` — Hub com links para as LPs.
- `ti.html` — Diretores de TI (diagnóstico de arquitetura).
- `portal.html` — CEOs/COOs que precisam de portal/plataforma digital.
- `ecom.html` — Gestores de e-commerce / produto digital.

## Como usar

1. Crie um repositório no GitHub e faça push destes arquivos.
2. No painel da Vercel, clique em "Add New Project" e importe o repositório.
3. Framework = "Other" (ou None), sem comando de build, output na raiz.
4. Troque `https://SEU-N8N-ENDPOINT/webhook/tarso-captura-leads` pelo seu webhook real do n8n.
5. A cada push na branch principal, a Vercel fará novo deploy automaticamente.

## Integração com n8n

Os formulários de todas as LPs enviam via POST para o webhook do n8n.
No n8n, você pode:

- Criar/atualizar leads no seu CRM (Manus / Tarso Hub).
- Aplicar regras de score, origem, deduplicação.
- Notificar SDR via Slack, e-mail ou WhatsApp Business API.
