# Spartan Airsoft — Deploy Vercel

Site estático. Sem build step.

## Subir na Vercel (3 opções)

### 1. Drag & drop (mais rápido)
1. Acesse https://vercel.com/new
2. Arraste a pasta `deploy/` inteira pra área de upload
3. Clique em Deploy
4. Vercel devolve uma URL `*.vercel.app` em ~30s

### 2. CLI
```bash
npm i -g vercel
cd deploy
vercel
```
Aceita os defaults. Pra produção: `vercel --prod`.

### 3. Git
1. Cria um repo no GitHub com o conteúdo de `deploy/`
2. Em vercel.com → Add New → Project → Import o repo
3. Framework: **Other** · Build Command: (vazio) · Output: `.`

## Estrutura
- `index.html` — landing inteira
- `assets/` — fotos, logo
- `vercel.json` — cache de 1 ano em `/assets/*`

## Antes de mostrar pros caras — formulário
O `SHEETS_ENDPOINT` no `index.html` está vazio. Os cadastros vão pra `localStorage` do navegador (não chegam em lugar nenhum). Pra conectar ao Google Sheets, siga `apps-script.js` na raiz do projeto e cole a URL no `index.html`.
