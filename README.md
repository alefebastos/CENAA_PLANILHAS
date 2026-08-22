# Horizonte — Consolidador de Laudos de Solo

App estático (HTML + JS puro, sem backend) que roda inteiramente no navegador.
Nenhum arquivo enviado pelo usuário sai do computador dele — não há upload para servidor.

## Deploy no Vercel

**Opção 1 — CLI (mais rápido)**
```bash
npm i -g vercel
cd horizonte
vercel        # ambiente de preview
vercel --prod # produção
```

**Opção 2 — GitHub**
1. Suba esta pasta para um repositório no GitHub.
2. Em vercel.com → "Add New Project" → importe o repositório.
3. Não precisa configurar build command nem output directory — é um site estático,
   o `index.html` na raiz já é servido diretamente.
4. Deploy.

**Opção 3 — Drag and drop**
Em vercel.com → "Add New Project" → arraste a pasta `horizonte` (ou o zip extraído)
na área de upload.

## Estrutura
```
horizonte/
├── index.html     # app inteiro (UI + lógica de leitura/preenchimento de planilhas)
├── vercel.json     # config de headers e URLs limpas
└── README.md
```

## Observação
A leitura/escrita de .xlsx é feita com SheetJS carregado via CDN (cdnjs.cloudflare.com).
Se o ambiente de deploy bloquear CDNs externos, baixe o `xlsx.full.min.js` e sirva localmente,
trocando o `<script src="...">` no `index.html`.
