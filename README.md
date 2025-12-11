# Tarso Landing Multi (Vercel) — Versão com mensagem de sucesso

Projeto com múltiplas landing pages da Tarso Tecnologia para diferentes ICPs, preparado para deploy na Vercel,
com formulários integrados ao Manus via POST e mensagem de sucesso amigável (sem tela em branco com JSON).

## Páginas

- `index.html` — Hub com links para as LPs.
- `ti.html` — Diretores de TI (diagnóstico de arquitetura).
- `portal.html` — CEOs/COOs que precisam de portal/plataforma digital.
- `ecom.html` — Gestores de e-commerce / produto digital.
- `cfo.html` — CFOs e Heads de Operações que precisam de integração financeira.

## Como funciona o envio do formulário

- Cada formulário aponta diretamente para o endpoint público do Manus (via atributo `action`).
- O formulário é enviado para um `<iframe>` oculto (atributo `target`).
- O usuário continua na mesma página.
- Quando o iframe carrega a resposta (JSON do Manus), um script:
  - exibe uma mensagem de sucesso discreta e amigável,
  - reseta o formulário,
  - atualiza o texto do botão para indicar sucesso.

Não há necessidade de n8n ou backend próprio para evitar a tela branca com JSON.

## O que você precisa alterar

1. Em cada arquivo de LP (`ti.html`, `portal.html`, `ecom.html`, `cfo.html`), troque:
   - `https://SEU-ENDPOINT-MANUS-AQUI`
   pelo endpoint real de recepção do Manus.

2. (Opcional) Ajuste os textos da mensagem de sucesso se quiser personalizar por ICP.

## Como usar na Vercel

1. Crie um repositório no GitHub e faça push destes arquivos.
2. No painel da Vercel, clique em "Add New Project" e importe o repositório.
3. Framework = "Other" (ou None), sem comando de build, output na raiz.
4. A cada push na branch principal, a Vercel fará novo deploy automaticamente.
