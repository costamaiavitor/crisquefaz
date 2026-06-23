# Cris que faz — modo automático (GitHub + Netlify) 🌼

Depois de configurado (uma vez só), sua mãe edita os arranjos no painel **/admin**,
clica em Publicar, e o site **se atualiza sozinho** — sem baixar nada, sem arrastar zip.

São 4 etapas. A etapa 4 (login) é a única um pouco técnica — se travar, me chame.

---

## Etapa 1 — Colocar os arquivos no GitHub
1. Entre em **github.com** e faça login.
2. Botão **New** (novo repositório) → nome **`cris-que-faz`** → Público ou Privado, tanto faz → **Create repository**.
3. Na página do repositório vazio, clique em **"uploading an existing file"**.
4. Arraste **todos os arquivos e pastas** que vieram no zip (index.html, a pasta `admin`, `assets`, `css`, `data`, `js`, `netlify.toml`, etc.).
5. Clique em **Commit changes**.

## Etapa 2 — Dizer ao painel qual é o seu repositório
1. No GitHub, abra o arquivo **`admin/config.yml`**.
2. Clique no lápis (editar) e, na linha `repo:`, troque **`SEU_USUARIO`** pelo seu usuário do GitHub.
   Ex.: se seu usuário é `cris123`, fica `repo: cris123/cris-que-faz`.
3. **Commit changes**.

## Etapa 3 — Ligar o GitHub na Netlify (deploy automático)
Assim o site republica sozinho a cada mudança, mantendo o endereço `cris-que-faz.netlify.app`.
1. Entre em **app.netlify.com** e abra o site **cris-que-faz**.
2. Vá em **Site configuration → Build & deploy → Continuous deployment**.
3. Em *Repository*, clique em **Link repository** (ou "Manage repository") → **GitHub** → autorize → escolha o repositório **cris-que-faz**.
4. Build settings: **Build command** vazio · **Publish directory** = `.` (um ponto) → salve.
   (O arquivo `netlify.toml` já deixa isso pronto.)

## Etapa 4 — Ativar o login do painel /admin
O painel entra com o seu login do GitHub. Registra-se um "aplicativo" uma única vez.

**4.1 — Criar o app no GitHub**
1. GitHub → sua foto (canto superior direito) → **Settings** → no fim do menu **Developer settings** → **OAuth Apps** → **New OAuth App**.
2. Preencha:
   - **Application name:** `Cris que faz`
   - **Homepage URL:** `https://cris-que-faz.netlify.app`
   - **Authorization callback URL:** `https://api.netlify.com/auth/done`
3. **Register application** → copie o **Client ID** → clique em **Generate a new client secret** → copie o **Client Secret**.

**4.2 — Colocar na Netlify**
1. Netlify → seu site → **Site configuration → Access & security → OAuth**
   (em alguns layouts aparece como "Authentication providers").
2. **Install provider** → **GitHub** → cole o **Client ID** e o **Client Secret** → **Save**.

---

## Pronto! Como usar daqui pra frente
- Acesse **https://cris-que-faz.netlify.app/admin.html**
- Clique em **Login with GitHub** e autorize.
- Abra **"Catálogo e Contato"**. Ali dá pra:
  - **Adicionar / editar / remover arranjos** (nome, categoria, preço, descrição, **foto**, selo, destaque).
  - Mudar **WhatsApp, Instagram, e-mail** e horário.
- Clique em **Publish (Publicar)**. Em ~1 minuto o site atualiza sozinho. ✅

## Para a sua mãe usar
- Ela acessa o mesmo `/admin` e faz login com o GitHub.
- Se quiser que ela use a conta **dela**: convide-a como colaboradora do repositório
  (GitHub → repositório → **Settings → Collaborators**). Ou ela usa o mesmo login que você.

## Observações
- O painel antigo (baixar zip e arrastar) continua funcionando, mas com o modo automático você não precisa mais dele.
- As fotos que ela subir no /admin vão automaticamente para a pasta `assets/produtos`.
- Travou em alguma etapa (principalmente a 4)? Me chame aqui que eu te ajudo no detalhe.

Feito com carinho 🌼
