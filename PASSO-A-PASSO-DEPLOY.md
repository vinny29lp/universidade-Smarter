# 🚀 Passo a passo: subir a Universidade Smarter no domínio

## Visão geral
Vamos usar **GitHub + Vercel** (ambos grátis) para hospedar o site, e configurar o DNS no HostGator pra apontar `universidade.smarterestagios.com.br` para o Vercel.

Tempo total: ~15 minutos.

---

## PARTE 1 — Baixar o projeto

1. No chat, clique no botão **"Baixar projeto"** que vou te enviar logo abaixo
2. Salve o arquivo `.zip` no seu Mac
3. Descompacte (duplo clique no arquivo)

Você vai ter uma pasta chamada `treinamento-smarter` (ou parecido) com os arquivos do site.

---

## PARTE 2 — Subir para o GitHub

### Se você ainda não tem conta no GitHub:
1. Acesse https://github.com/signup
2. Crie a conta (use seu e-mail Smarter)

### Criar o repositório:
1. Acesse https://github.com/new
2. **Repository name:** `universidade-smarter`
3. **Private** ✅ (recomendado — só você acessa o código)
4. **NÃO** marque "Add a README" (já existe)
5. Clique em **"Create repository"**

### Subir os arquivos (mais fácil — direto pelo navegador):
1. Na página do repositório recém-criado, clique em **"uploading an existing file"**
2. Arraste TODOS os arquivos da pasta descompactada para a área cinza
3. Aguarde o upload terminar (~30 segundos)
4. Em "Commit changes", clique no botão verde **"Commit changes"**

✅ Pronto. Seu código está no GitHub.

---

## PARTE 3 — Conectar no Vercel

1. Acesse https://vercel.com/signup
2. Clique em **"Continue with GitHub"** (usa sua conta GitHub para entrar)
3. Autorize o Vercel a acessar seus repositórios
4. Na tela inicial do Vercel, clique em **"Add New..." → "Project"**
5. Procure por `universidade-smarter` na lista
6. Clique em **"Import"**
7. Na próxima tela, **NÃO MUDE NADA**, só clique em **"Deploy"**
8. Aguarde ~1 minuto

✅ Seu site está no ar! O Vercel te dá uma URL temporária tipo `universidade-smarter-xxx.vercel.app`. Teste — deve funcionar perfeitamente.

---

## PARTE 4 — Apontar o domínio no HostGator

### No painel do Vercel:
1. Na página do projeto, clique em **"Settings" → "Domains"** (menu lateral)
2. No campo de texto, digite: `universidade.smarterestagios.com.br`
3. Clique em **"Add"**
4. O Vercel vai mostrar uma instrução tipo:
   > "Add the following CNAME record: **Type: CNAME, Name: universidade, Value: cname.vercel-dns.com**"
5. **Deixe essa aba aberta!** Você vai precisar desses valores.

### No painel do HostGator:
1. Acesse https://financeiro.hostgator.com.br/ e faça login
2. Vá em **"Meus produtos e serviços" → seu plano**
3. Acesse o **cPanel** (ou painel de DNS)
4. Procure por **"Zone Editor"** ou **"Editor de Zona DNS"**
5. Localize o domínio `smarterestagios.com.br` e clique em **"Manage"** / **"Gerenciar"**
6. Clique em **"+ Add Record"** / **"Adicionar Registro"**
7. Preencha:
   - **Type / Tipo:** CNAME
   - **Name / Nome:** `universidade` (só essa palavra; o HostGator completa com `.smarterestagios.com.br` automaticamente)
   - **TTL:** 14400 (ou padrão)
   - **Address / Aponta para:** `cname.vercel-dns.com` (ou o valor que o Vercel te deu)
8. Salve

✅ Pronto. Agora é só esperar a propagação do DNS.

---

## PARTE 5 — Aguardar e testar

- **Tempo de propagação:** entre 5 minutos e 24 horas (geralmente menos de 1h)
- Para checar se já propagou: https://dnschecker.org/ (digite o domínio)
- Quando todos os pontos do mapa estiverem verdes, está pronto

Acesse https://universidade.smarterestagios.com.br no navegador. 🎉

O Vercel vai gerar um certificado HTTPS automaticamente (cadeado verde).

---

## DÚVIDAS COMUNS

**"Não acho o Zone Editor no HostGator"**
→ No cPanel, role até a seção "Domínios" ou use a busca no topo do cPanel.

**"O Vercel diz 'Invalid Configuration'"**
→ Aguarde 10 minutos e clique em "Refresh" no Vercel. DNS demora.

**"Quero usar um domínio diferente"**
→ Mesmo passo a passo, só muda o subdomínio na PARTE 4.

**"Como atualizo o site depois?"**
→ Sobe os arquivos atualizados no GitHub (mesmo botão "Add file → Upload files"). O Vercel detecta e reimplanta sozinho em ~30 segundos.

---

## PRECISA DE AJUDA?
Me chama no chat com print do que está aparecendo. Te respondo na hora.
