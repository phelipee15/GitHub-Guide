# 🐙 Guia Completo de GitHub — Minicurso

> **Do zero ao perfil profissional**: Git, GitHub e como se destacar na plataforma.

---

## 📋 Índice

1. [O que é Git e GitHub?](#1-o-que-é-git-e-github)
2. [Instalando o Git](#2-instalando-o-git)
3. [Configurando o Git](#3-configurando-o-git)
4. [Integrando o Git com o VS Code](#4-integrando-o-git-com-o-vs-code)
5. [Comandos Git Essenciais](#5-comandos-git-essenciais)
6. [Criando sua Conta no GitHub](#6-criando-sua-conta-no-github)
7. [Repositórios: o básico](#7-repositórios-o-básico)
8. [Montando seu Perfil no GitHub](#8-montando-seu-perfil-no-github)
9. [Ferramentas para turbinar seu README](#9-ferramentas-para-turbinar-seu-readme)
10. [Exemplo de Perfil Profissional](#10-exemplo-de-perfil-profissional)
11. [Boas práticas e dicas finais](#11-boas-práticas-e-dicas-finais)

---

## 1. O que é Git e GitHub?

**Git** é um sistema de controle de versão. Ele registra o histórico de alterações do seu código, permitindo voltar a versões anteriores, trabalhar em equipe sem conflitos e criar ramificações independentes do projeto.

**GitHub** é uma plataforma online que hospeda repositórios Git. Além de armazenar código, ele funciona como portfólio, rede social para devs e ferramenta de colaboração.

```
Git  →  ferramenta instalada no seu computador
GitHub → plataforma na nuvem que usa Git
```

> 💡 Analogia: o Git é o "histórico de versões" do Word. O GitHub é o Google Drive onde você guarda e compartilha esses arquivos.

---

## 2. Instalando o Git

### Windows

1. Acesse: https://git-scm.com/download/win
2. Baixe o instalador e execute
3. Durante a instalação, mantenha as opções padrão
4. Na etapa **"Choosing the default editor"**, selecione **Visual Studio Code** (se já tiver instalado)
5. Conclua a instalação

**Verificar se instalou corretamente:**
```bash
git --version
# Saída esperada: git version 2.x.x
```

### Linux (Ubuntu/Debian)
```bash
sudo apt update
sudo apt install git
```

### macOS
```bash
# Via Homebrew
brew install git

# Ou instale pelo Xcode Command Line Tools
xcode-select --install
```

---

## 3. Configurando o Git

Após instalar, configure seu nome e e-mail. Essas informações aparecem em todos os seus commits.

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"
```

**Verificar configurações:**
```bash
git config --list
```

> ⚠️ Use o mesmo e-mail da sua conta do GitHub para que os commits apareçam corretamente no seu perfil.

---

## 4. Integrando o Git com o VS Code

O VS Code possui suporte nativo ao Git. Veja como usá-lo:

### Abrindo o controle de versão

- Clique no ícone de **ramificação** na barra lateral esquerda (ou `Ctrl+Shift+G`)
- Ou use o terminal integrado (`Ctrl+`\``) para rodar comandos Git normalmente

### Funcionalidades visuais do VS Code

| Ação | Como fazer no VS Code |
|---|---|
| Ver arquivos modificados | Aba "Source Control" na barra lateral |
| Fazer commit | Escrever mensagem no campo e clicar ✓ |
| Publicar no GitHub | Botão "Publish Branch" ou "Sync Changes" |
| Ver histórico | Extensão **GitLens** (recomendada) |
| Resolver conflitos | Editor visual de merge integrado |

### Extensões recomendadas para Git no VS Code

- **GitLens** — histórico detalhado, blame, comparações
- **GitHub Pull Requests** — gerenciar PRs diretamente no editor
- **Git Graph** — visualização gráfica dos branches

### Autenticando com o GitHub no VS Code

1. Abra a paleta de comandos: `Ctrl+Shift+P`
2. Digite: `GitHub: Sign In`
3. Siga o fluxo de autenticação pelo navegador

---

## 5. Comandos Git Essenciais

### Fluxo básico do dia a dia

```bash
# 1. Clonar um repositório existente
git clone https://github.com/usuario/repositorio.git

# 2. Ver o status dos arquivos
git status

# 3. Adicionar arquivos para o commit
git add .                  # todos os arquivos
git add arquivo.txt        # arquivo específico

# 4. Criar um commit
git commit -m "feat: adiciona funcionalidade X"

# 5. Enviar para o GitHub
git push origin main

# 6. Atualizar o repositório local
git pull origin main
```

### Trabalhando com branches

```bash
# Criar e entrar em uma nova branch
git checkout -b minha-feature

# Listar branches
git branch

# Voltar para a main
git checkout main

# Mesclar uma branch
git merge minha-feature
```

### Comandos úteis

```bash
# Ver histórico de commits
git log --oneline

# Desfazer alterações não commitadas
git restore arquivo.txt

# Ver diferenças antes de commitar
git diff
```

### Padrão de mensagens de commit (Conventional Commits)

```
feat: nova funcionalidade
fix: correção de bug
docs: alteração em documentação
style: formatação, sem mudança de lógica
refactor: refatoração de código
chore: tarefas de manutenção
```

---

## 6. Criando sua Conta no GitHub

1. Acesse: https://github.com/signup
2. Escolha um **username** profissional — ele aparecerá em todos os seus repositórios e no seu perfil público
3. Confirme o e-mail
4. Configure uma foto de perfil e bio em: `Settings → Profile`

> 💡 Dica de username: evite números aleatórios. Prefira algo como `phelipemelo`, `phelipe-dev` ou similar — limpo e memorável.

---

## 7. Repositórios: o básico

### Criar um repositório pelo GitHub

1. Clique em **"New"** no canto superior esquerdo
2. Dê um nome ao repositório
3. Escolha entre **público** ou **privado**
4. Marque **"Add a README file"** para já inicializar o repo
5. Clique em **"Create repository"**

### Estrutura básica de um repositório bem organizado

```
meu-projeto/
├── README.md          ← documentação principal
├── .gitignore         ← arquivos ignorados pelo git
├── LICENSE            ← licença do projeto
├── src/               ← código fonte
│   └── main.py
└── docs/              ← documentação extra
```

### O arquivo `.gitignore`

Evita que arquivos desnecessários sejam enviados ao GitHub:

```gitignore
# Dependências
node_modules/
__pycache__/

# Variáveis de ambiente
.env

# Arquivos do sistema
.DS_Store
Thumbs.db
```

> Gere um .gitignore automático para sua linguagem em: https://gitignore.io

---

## 8. Montando seu Perfil no GitHub

### O repositório especial de perfil

O GitHub permite criar um repositório com o **mesmo nome do seu username**. O `README.md` desse repositório é exibido diretamente no seu perfil público.

**Como criar:**
1. Vá em `New repository`
2. Nome do repositório = seu username (ex: `phelipee15`)
3. Marque como **Público**
4. Ative **"Add a README file"**
5. Crie o repositório

### Estrutura recomendada para o README do perfil

```markdown
<!-- Banner animado no topo -->

## Sobre mim
(quem você é, onde está, o que faz)

## Tecnologias & Ferramentas
(badges das linguagens e ferramentas que usa)

## Projetos em destaque
(links para seus melhores repositórios)

## Estatísticas do GitHub
(cards gerados automaticamente)

## Contato
(LinkedIn, e-mail, Discord, etc.)
```

---

## 9. Ferramentas para turbinar seu README

### 🎨 Gerador visual de perfil

> **https://profile-readme-generator.com/pt-BR**

Interface visual, sem precisar escrever código. Você arrasta blocos e o site gera o Markdown automaticamente. Ideal para quem está começando.

### 🖼️ Banners animados — Capsule Render

```markdown
![Banner](https://capsule-render.vercel.app/api?type=waving&color=0:1a2a6c,100:2b4aad&height=200&section=header&text=Seu+Nome&fontSize=48&fontColor=ffffff)
```

Personalize em: https://github.com/kyechan99/capsule-render

Parâmetros úteis:

| Parâmetro | Descrição | Exemplo |
|---|---|---|
| `type` | Estilo do banner | `waving`, `rect`, `soft`, `egg` |
| `color` | Gradiente (hex) | `0:1a2a6c,100:ff6b6b` |
| `text` | Texto exibido | `Seu+Nome` |
| `animation` | Animação | `fadeIn`, `twinkling`, `blinking` |

### 🏷️ Badges de tecnologia

**Shields.io** — personalizável:
```markdown
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
```

**Skill Icons** — ícones prontos e bonitos:
```markdown
![Skills](https://skillicons.dev/icons?i=python,js,nodejs,git,vscode)
```

Veja todos os ícones disponíveis em: https://skillicons.dev

### 📊 Cards de estatísticas do GitHub

```markdown
<!-- Estatísticas gerais -->
![Stats](https://github-readme-stats.vercel.app/api?username=SEU_USERNAME&show_icons=true&theme=tokyonight)

<!-- Linguagens mais usadas -->
![Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=SEU_USERNAME&layout=compact&theme=tokyonight)
```

Temas disponíveis: `dark`, `radical`, `tokyonight`, `dracula`, `gruvbox`, `cobalt`, `synthwave`

### 🏆 Troféus do GitHub

```markdown
![Trophies](https://github-profile-trophy.vercel.app/?username=SEU_USERNAME&theme=darkhub&no-frame=true&row=1&column=7)
```

### 🐍 Animação da cobrinha (contribuições)

Para ativar a cobrinha que "come" seu gráfico de contribuições, você precisa de um **GitHub Actions**. Crie o arquivo `.github/workflows/snake.yml` no seu repositório de perfil:

```yaml
name: Generate Snake

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:

jobs:
  generate:
    runs-on: ubuntu-latest
    steps:
      - uses: Platane/snk@v3
        with:
          github_user_token: ${{ secrets.GITHUB_TOKEN }}
          outputs: |
            dist/snake.svg
            dist/snake-dark.svg?palette=github-dark
      - uses: crazy-max/ghaction-github-pages@v3
        with:
          target_branch: snake-output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

Depois de rodar o workflow, use no README:
```markdown
![Snake](https://raw.githubusercontent.com/SEU_USERNAME/SEU_USERNAME/snake-output/snake.svg)
```

### 👁️ Contador de visitas

```markdown
![Visitors](https://komarev.com/ghpvc/?username=SEU_USERNAME&color=1a2a6c&style=flat-square&label=Visitantes)
```

---

## 10. Exemplo de Perfil Profissional

Abaixo um template completo e funcional para copiar e adaptar:

```markdown
<!-- Banner -->
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a2a6c,100:2b4aad&height=200&section=header&text=Seu+Nome&fontSize=48&fontColor=ffffff&fontAlignY=38&desc=Developer+|+Back-end+|+Data+Science&descAlignY=58&animation=fadeIn" width="100%"/>
</div>

<!-- Redes sociais -->
<div align="center">
  <a href="https://linkedin.com/in/seu-perfil">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/>
  </a>
  <a href="mailto:seuemail@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white"/>
  </a>
  <a href="https://github.com/seu-username">
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white"/>
  </a>
</div>

## 👋 Sobre mim

```python
dev = {
    "nome":       "Seu Nome",
    "localização":"Sua Cidade, Brasil",
    "formação":   "Sua Universidade",
    "interesses": ["Back-end", "Data Science", "Automação"],
    "status":     "Em constante evolução"
}
` `` ← remova o espaço

## 🛠️ Tecnologias

<div align="center">
  <img src="https://skillicons.dev/icons?i=python,js,nodejs,git,vscode,sqlite"/>
</div>

## 📊 Estatísticas

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=SEU_USERNAME&show_icons=true&theme=tokyonight" height="180"/>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=SEU_USERNAME&layout=compact&theme=tokyonight" height="180"/>
</div>

<!-- Footer -->
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a2a6c,100:2b4aad&height=100&section=footer" width="100%"/>
</div>
```

---

## 11. Boas práticas e dicas finais

### ✅ Para o perfil

- Mantenha o README **atualizado** — tecnologias desatualizadas passam imagem de abandono
- Adicione um **bloco "Sobre mim"** com suas áreas de interesse e projetos atuais
- Use **alinhamento centralizado** (`<div align="center">`) para um visual mais limpo
- Inclua **links funcionais** para LinkedIn, portfólio e projetos em destaque

### ✅ Para os repositórios

- Todo repositório relevante deve ter um `README.md` explicando o projeto
- Use **descrição** e **tópicos (tags)** em cada repo para facilitar descoberta
- Crie **releases** em projetos que versiona publicamente
- Fixe até 6 repositórios no topo do perfil: `Perfil → Customize your pins`

### ✅ Para contribuições

- Faça commits **frequentes e com mensagens claras**
- O gráfico de contribuições fica verde com commits, PRs, issues e code reviews
- Contribua com projetos open source — aparece no histórico do perfil

### ✅ Para o GitHub Pages

O GitHub oferece hospedagem gratuita para sites estáticos:

1. Crie um repositório com nome `SEU_USERNAME.github.io`
2. Suba um `index.html`
3. Ative em `Settings → Pages → Source: main branch`
4. Acesse em: `https://SEU_USERNAME.github.io`

---

## 📚 Recursos úteis

| Recurso | Link |
|---|---|
| Gerador visual de perfil | https://profile-readme-generator.com/pt-BR |
| Shields.io (badges) | https://shields.io |
| Skill Icons | https://skillicons.dev |
| Capsule Render (banners) | https://github.com/kyechan99/capsule-render |
| GitHub Stats | https://github.com/anuraghazra/github-readme-stats |
| Troféus | https://github.com/ryo-ma/github-profile-trophy |
| Gitignore gerador | https://gitignore.io |
| Conventional Commits | https://www.conventionalcommits.org/pt-br |

---

<div align="center">
  <sub>Guia criado para o minicurso de GitHub • Bons estudos! 🚀</sub>
</div>
```