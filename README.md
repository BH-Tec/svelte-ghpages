# Tutorial

### Passo 1: Configurar o `gh-pages`

1. **Instalar a biblioteca `gh-pages`**:
   Adicione a biblioteca `gh-pages` ao seu projeto como uma devDependence:

   ```bash
   pnpm add gh-pages -D
   ```

2. **Adicionar script de build**:
   No arquivo `package.json`, adicione o script `build` para gerar o build do seu projeto.

   ```json
   "scripts": {
     "deploy": "pnpm run build && pnpm run gh-pages",
   }
    ```

3. Configurar a base do projeto
   No arquivo `vite.config.js`, add a configuração:

   ```javascript
   import { defineConfig } from 'vite'
   import { svelte } from '@sveltejs/vite-plugin-svelte'

   export default defineConfig({
     plugins: [svelte()],
     base: '/nome-do-repositorio/'  // Substitua "nome-do-repositorio" pelo nome do seu repositório GitHub
   })
   ```

### Passo 2: Publicando no GitHub Pages

1. **Publicar no GitHub Pages**:
   ```bash
   pnpm run deploy
   ```

### Passo 3: Configurar o GitHub Pages no repositório

1. **Ativar o GitHub Pages**:
   Depois de fazer o deploy, vá até a página de configurações do seu repositório no GitHub:

   1. Acesse o repositório no GitHub.
   2. Clique na aba `Settings`.
   3. No menu lateral, clique em `Pages`.
   4. Em `Source`, selecione `gh-pages branch` no dropdown e clique em `Save`.

2. **Acessar a página**:
   Aguarde alguns minutos e sua aplicação estará disponível em `https://seu-usuario.github.io/seu-repositorio`. Você pode verificar acessando esse URL diretamente no navegador.
