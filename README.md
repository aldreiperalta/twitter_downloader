# 🎬 Twitter Video Downloader

Aplicativo para baixar vídeos do Twitter/X diretamente pelo navegador.

## 📋 Opções de Uso

### ✅ **Opção 1: HTML Puro (Mais Fácil - Recomendado)**

Use o arquivo `twitter_downloader_complete.html`

**Vantagens:**
- Funciona imediatamente no navegador
- Sem configurações necessárias
- Hospedável no GitHub Pages, Netlify, Vercel, etc.

**Como usar:**
1. Baixe o arquivo `twitter_downloader_complete.html`
2. Abra no navegador (duplo clique)
3. Cole o link do tweet
4. Clique em "Extrair Vídeo"

### ⚙️ **Opção 2: Com Servidor Backend (Vercel)**

Para máxima confiabilidade, configure um servidor backend.

---

## 🚀 Hospedagem no GitHub Pages (Opção 1)

### Passo 1: Criar repositório
```bash
# Via GitHub Web:
1. Acesse github.com
2. Clique em "New repository"
3. Nome: "twitter-video-downloader"
4. Deixe como Public
5. Crie o repositório
```

### Passo 2: Adicionar o arquivo
```bash
# Clone o repositório
git clone https://github.com/SEU_USUARIO/twitter-video-downloader.git
cd twitter-video-downloader

# Copie o arquivo HTML
cp ~/Downloads/twitter_downloader_complete.html index.html

# Faça commit
git add index.html
git commit -m "Add Twitter video downloader"
git push origin main
```

### Passo 3: Ativar GitHub Pages
1. No repositório, vá para **Settings** ⚙️
2. Clique em **Pages** (menu esquerdo)
3. Em **Source**, selecione:
   - Branch: `main`
   - Folder: `/ (root)`
4. Clique em **Save**
5. Aguarde 2-3 minutos...
6. Sua URL será: `https://SEU_USUARIO.github.io/twitter-video-downloader/`

---

## 🌐 Hospedagem no Vercel (Opção 2 - Com Backend)

Para maior confiabilidade, use um servidor backend que funciona 24/7.

### Passo 1: Preparar arquivos

Crie a seguinte estrutura:
```
twitter-video-downloader/
├── api/
│   └── download.js        ← arquivo API
├── public/
│   └── index.html         ← arquivo HTML
├── package.json           ← dependências
└── vercel.json            ← configuração (opcional)
```

### Passo 2: Criar arquivo `vercel.json`
```json
{
  "buildCommand": "npm install",
  "rewrites": [
    {
      "source": "/api/download",
      "destination": "/api/download.js"
    }
  ]
}
```

### Passo 3: Deploy no Vercel

```bash
# Instale o Vercel CLI
npm install -g vercel

# Faça login
vercel login

# Deploy
vercel --prod
```

Ou use o GitHub:
1. Faça push do código para GitHub
2. Acesse [vercel.com](https://vercel.com)
3. Clique em "New Project"
4. Selecione o repositório GitHub
5. Vercel fará deploy automaticamente

### Passo 4: Configurar o URL da API no HTML

Edite a linha no `index.html`:
```javascript
// ANTES:
const API_URL = 'https://seu-projeto.vercel.app/api/download';

// DEPOIS (com seu projeto):
const API_URL = 'https://meu-projeto-abc123.vercel.app/api/download';
```

---

## 📱 Como Usar

1. **Cole um link do tweet**
   - Exemplo: `https://twitter.com/user/status/1234567890`
   - Funciona com Twitter.com e X.com

2. **Clique em "Extrair Vídeo"**
   - Aguarde alguns segundos
   - O app buscará os vídeos disponíveis

3. **Selecione a qualidade**
   - Escolha a versão desejada
   - O download iniciará automaticamente

---

## ✅ Requisitos

- **Tweet público** (não funciona com tweets privados)
- **Contém vídeo ou GIF** (imagens não funcionam)
- **Conexão com internet**

---

## ❌ Troubleshooting

### Erro "Failed to fetch"
- A API pode estar down temporariamente
- Tente novamente em alguns minutos
- Verifique se o tweet é público

### Nenhum vídeo encontrado
- Certifique-se de que o tweet contém um vídeo
- Imagens não funcionam, apenas vídeos
- O tweet precisa ser público

### O download não funciona
- Verifique as permissões do navegador
- Tente outro navegador (Chrome, Firefox, Safari)
- Desabilite bloqueadores de anúncios

---

## 🔧 Estrutura dos Arquivos

### `twitter_downloader_complete.html`
- Interface web completa
- Funciona standalone
- Usa APIs públicas como fallback

### `api/download.js` (Vercel)
- Servidor backend Node.js
- Faz proxy das requisições
- Evita problemas de CORS

### `package.json`
- Dependências do Node.js
- Configuração do projeto

---

## 📦 APIs Utilizadas

O aplicativo tenta usar estas APIs em ordem:
1. TwitSave (`https://twitsave.com`)
2. SSSTwitter (`https://ssstwitter.com`)
3. Twitter oEmbed

Se uma falhar, tenta a próxima automaticamente.

---

## 🤝 Contribuições

Sinta-se livre para:
- Reportar bugs
- Sugerir melhorias
- Fazer fork e customizar

---

## ⚖️ Aviso Legal

Este projeto é para **uso pessoal e educacional**. 
- Respeite os direitos autorais
- Não distribua conteúdo protegido
- Use responsavelmente

---

## 📞 Suporte

Se encontrar problemas:
1. Verifique o console do navegador (F12)
2. Tente outro navegador
3. Aguarde alguns minutos e tente novamente
4. Abra uma issue no GitHub

---

**Desenvolvido com ❤️ para a comunidade**
