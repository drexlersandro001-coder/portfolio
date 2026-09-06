# Portefólio — Drexler Sandro

Site estático (HTML/CSS/JS puro, sem build) pronto para publicar no GitHub Pages.

**Estrutura actual:** o foco é a carreira profissional (Dossiê + Trajecto Profissional, com as
iniciativas reais de segurança da informação no BFA). Depois há um separador visual ("Depois do
expediente") que muda a paleta de âmbar para teal e introduz o Laboratório Pessoal — os 4
projectos Lovable, agora apresentados como hobby de programação com IA, não como trabalho.

## Antes de publicar — preenche isto

Abre `index.html` e substitui os placeholders da secção de contacto (procura por `o-teu-email`,
`o-teu-utilizador`, `244000000000`) pelos teus dados reais de email, LinkedIn e WhatsApp.

As imagens dos 4 projectos apontam para os screenshots gerados automaticamente pelo Lovable.
Esses links podem mudar ou expirar com o tempo. Para robustez a longo prazo, descarrega-os e
guarda-os localmente:

```bash
mkdir -p assets
curl -o assets/car-control.png "https://screenshot2.lovable.dev/042d1fcd4705b30d50b3b5d0a5b60a51/id-preview-7d7ef6c4--a60543bf-a849-43b4-8e2f-1aa706005bc8.lovable.app-1788705817076.png"
curl -o assets/kwanza-control.png "https://screenshot2.lovable.dev/4548f5f46f80f5c314a80a0343233649/id-preview-d00d3d6e--017f1565-4124-40d4-97b9-597459d5f971.lovable.app-1788691983988.png"
curl -o assets/lista-esperta.png "https://screenshot2.lovable.dev/fb9dc803-794e-43d6-861c-ce39173c308d/id-preview-1fcd09e1--6923cdd7-3650-4cc7-9867-0b2490e6d9ac.lovable.app-1781867146982.png"
curl -o assets/digital-guardian.png "https://screenshot2.lovable.dev/aaa45cc365f259967fbddd73a8b2f1b8/id-preview-2a1229fa--916feb52-4028-4b5d-9210-2703c3739409.lovable.app-1788346243816.png"
```

Depois, no `index.html`, troca cada `src="https://screenshot2..."` por `src="assets/car-control.png"` (etc.).

Quando o Digital Guardian Angola ficar publicado, adiciona o link real no `<span class="case-disabled">`
(troca por um `<a>` igual aos outros três) e muda a classe `dot-status dev` para `dot-status live`.

## Publicar no GitHub Pages — passo a passo

1. **Cria o repositório**
   No GitHub, cria um novo repositório público. Pode chamar-se, por exemplo, `portfolio` ou
   `drexler-sandro.github.io` (este segundo nome tem uma vantagem: fica disponível directamente
   em `https://drexler-sandro.github.io`, sem sufixo de caminho).

2. **Envia os ficheiros**
   Na tua máquina, dentro da pasta com estes 3 ficheiros (`index.html`, `styles.css`, `script.js`):
   ```bash
   git init
   git add .
   git commit -m "Primeiro deploy do portefólio"
   git branch -M main
   git remote add origin https://github.com/<o-teu-utilizador>/<nome-do-repo>.git
   git push -u origin main
   ```

3. **Activa o GitHub Pages**
   No repositório, vai a **Settings → Pages**. Em "Build and deployment", escolhe
   **Source: Deploy from a branch**, selecciona a branch `main` e a pasta `/ (root)`. Grava.

4. **Espera 1–2 minutos**
   O GitHub mostra o link no topo da mesma página (algo como
   `https://<utilizador>.github.io/<nome-do-repo>/`). Actualiza a página se não aparecer logo.

5. **Domínio próprio (opcional)**
   Se mais tarde quiseres um domínio próprio (ex: `drexlersandro.com`), em **Settings → Pages →
   Custom domain** adiciona o domínio e configura o registo DNS (`CNAME` apontando para
   `<utilizador>.github.io`) junto do teu fornecedor de domínio.

## Actualizar o site no futuro

Sempre que quiseres mudar algo (novo projecto, texto, foto):
```bash
git add .
git commit -m "Actualiza projecto X"
git push
```
O GitHub Pages actualiza automaticamente o site publicado em cerca de um minuto.

## Estrutura dos ficheiros

```
.
├── index.html      → conteúdo e estrutura da página
├── styles.css      → todo o visual (cores, tipografia, layout)
├── script.js       → apenas actualiza o ano no rodapé
└── README.md       → este guia
```

Nenhuma dependência, nenhum passo de build — é servido tal como está.
