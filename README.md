<!-- SVG Icons usados como títulos de seção são embutidos inline via HTML -->

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:161b22,100:21262d&height=180&section=header&text=Guia%20GitHub&fontSize=44&fontColor=ffffff&fontAlignY=38&desc=Do%20repositório%20ao%20perfil%20profissional&descAlignY=58&descSize=16&animation=fadeIn" width="100%"/>

</div>

---

## Índice

1. [O que é Git e GitHub](#1-o-que-é-git-e-github)
2. [Criando seu primeiro repositório](#2-criando-seu-primeiro-repositório)
3. [Criando seu perfil](#3-criando-seu-perfil)
4. [Ferramentas](#4-ferramentas)
5. [Template Completo](#5-template-completo)
6. [Instalando o Git](#6-instalando-o-git)
7. [Configurando o Git](#7-configurando-o-git)
8. [Integrando com VS Code](#8-integrando-com-vs-code)
9. [Comandos Git](#9-comandos-git)
10. [Boas Práticas](#10-boas-práticas)

---

## 1. O que é Git e GitHub

<img src="https://raw.githubusercontent.com/FortAwesome/Font-Awesome/6.x/svgs/brands/git-alt.svg" width="18" align="center"/> **Git** é um sistema de controle de versão distribuído. Ele rastreia o histórico de alterações do seu código, permite voltar a versões anteriores, trabalhar em equipe sem conflitos e criar ramificações independentes do projeto — tudo isso localmente, no seu computador.

<img src="https://raw.githubusercontent.com/FortAwesome/Font-Awesome/6.x/svgs/brands/github.svg" width="18" align="center"/> **GitHub** é uma plataforma online que hospeda repositórios Git na nuvem. Além de armazenar código, funciona como portfólio público, rede social para desenvolvedores e ferramenta de colaboração em projetos.

```
Git    →  ferramenta instalada na sua máquina (controle de versão local)
GitHub →  plataforma na nuvem que armazena e compartilha repositórios Git
```

> **Analogia:** o Git é o histórico de versões de um documento. O GitHub é o Google Drive onde você salva e compartilha esse documento com o mundo.

### Conceitos fundamentais

| Conceito | Definição |
|---|---|
| **Repositório** | Pasta rastreada pelo Git que contém seu projeto e todo seu histórico |
| **Commit** | Registro de uma alteração, como um "salvar com mensagem" |
| **Branch** | Ramificação independente do projeto para desenvolver sem afetar o principal |
| **Merge** | Unificação de duas branches em uma só |
| **Clone** | Cópia local de um repositório remoto |
| **Push / Pull** | Enviar / receber alterações do repositório remoto |

---

## 2. Criando seu primeiro repositório

### Pelo GitHub (interface web)

1. Acesse [github.com](https://github.com) e clique em **"New"** no canto superior esquerdo
2. Preencha as informações:
   - **Repository name** — nome do projeto (use kebab-case: `meu-projeto`)
   - **Description** — uma linha descrevendo o projeto
   - **Public / Private** — público aparece no seu perfil; privado só você vê
3. Marque **"Add a README file"** para inicializar o repositório
4. Opcionalmente adicione um **`.gitignore`** para sua linguagem
5. Clique em **"Create repository"**

### Estrutura recomendada de um repositório

```
meu-projeto/
├── README.md          ← documentação principal (obrigatório)
├── .gitignore         ← arquivos ignorados pelo Git
├── LICENSE            ← licença de uso
├── src/               ← código fonte
│   └── main.py
└── docs/              ← documentação adicional
```

### O arquivo README.md

O `README.md` é a primeira coisa que alguém vê ao abrir seu repositório. Ele deve conter:

- O que é o projeto e para que serve
- Como instalar e executar
- Como contribuir (em projetos colaborativos)
- Exemplos de uso

### O arquivo .gitignore

Evita que arquivos desnecessários sejam versionados e enviados ao GitHub:

```gitignore
# Dependências
node_modules/
__pycache__/
*.pyc

# Variáveis de ambiente (nunca versione credenciais)
.env
.env.local

# Arquivos de sistema
.DS_Store
Thumbs.db

# Build e dist
dist/
build/
```

> Gere um `.gitignore` automático para sua linguagem em: https://gitignore.io

---

## 3. Criando seu perfil

### O repositório especial de perfil

O GitHub tem um recurso especial: se você criar um repositório com o **mesmo nome do seu username**, o `README.md` desse repositório é exibido diretamente na sua página de perfil público.

**Como criar:**

1. Clique em **"New repository"**
2. No campo de nome, digite exatamente o seu username (ex: `phelipee15`)
3. O GitHub reconhece automaticamente e exibe a mensagem: *"You found a secret!"*
4. Marque como **Public**
5. Ative **"Add a README file"**
6. Clique em **"Create repository"**

A partir daí, tudo que você escrever no `README.md` desse repositório aparece no seu perfil.

### Estrutura recomendada para o README de perfil

```markdown
<!-- 1. Banner animado no topo -->

<!-- 2. Badges de redes sociais (LinkedIn, GitHub, Discord, etc.) -->

<!-- 3. Bloco "Sobre mim" com suas informações em destaque -->

<!-- 4. Tecnologias e ferramentas que você usa -->

<!-- 5. Projetos em destaque (links para repos) -->

<!-- 6. Estatísticas do GitHub (cards automáticos) -->

<!-- 7. Contador de visitas -->

<!-- 8. Footer animado -->
```

### Dicas para o username

O seu username aparece em todos os seus repositórios, commits e na URL do perfil. Escolha algo:

- **Profissional** e fácil de lembrar
- **Sem números aleatórios** — prefira `joaosilva` a `joao123456`
- **Consistente** com outras redes (LinkedIn, Discord) se possível

---

## 4. Ferramentas

### Gerador visual de perfil

> **https://profile-readme-generator.com/pt-BR**

Interface visual sem precisar escrever código. Você arrasta blocos, preenche os campos e o site gera o Markdown pronto. Ideal para o primeiro contato.

---

### Capsule Render — Banners animados

Gera banners animados para o topo e rodapé do README.

```markdown
![Banner](https://capsule-render.vercel.app/api?type=waving&color=0:1a2a6c,100:2b4aad&height=200&section=header&text=Seu+Nome&fontSize=48&fontColor=ffffff&animation=fadeIn)
```

Documentação e exemplos: https://github.com/kyechan99/capsule-render

| Parâmetro | Descrição | Valores |
|---|---|---|
| `type` | Estilo do banner | `waving`, `rect`, `soft`, `egg`, `cylinder` |
| `color` | Cor ou gradiente | `#1a2a6c` ou `0:1a2a6c,100:ff6b6b` |
| `text` | Texto exibido | `Seu+Nome` (use `+` no lugar de espaço) |
| `desc` | Subtítulo | `Developer+%7C+Back-end` |
| `animation` | Animação | `fadeIn`, `twinkling`, `blinking`, `scaleIn` |
| `section` | Posição | `header` ou `footer` |

---

### Shields.io — Badges personalizáveis

Gera badges de tecnologias, redes sociais, status e muito mais.

```markdown
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
```

Estrutura de uma badge:

```
https://img.shields.io/badge/LABEL-COLOR?style=STYLE&logo=LOGO&logoColor=white
```

| Parâmetro | Exemplo |
|---|---|
| `LABEL` | Nome da tecnologia: `Python`, `LinkedIn` |
| `COLOR` | Hex sem `#`: `3776AB`, `0A66C2` |
| `style` | `for-the-badge`, `flat`, `flat-square`, `plastic` |
| `logo` | Nome do ícone no SimpleIcons: `python`, `github`, `discord` |

Gerador online: https://shields.io

---

### Skill Icons — Ícones de tecnologia

Gera uma linha de ícones de tecnologias de forma limpa e padronizada.

```markdown
![Skills](https://skillicons.dev/icons?i=python,js,lua,nodejs,c,git,vscode,sqlite)
```

Parâmetros opcionais:

```markdown
<!-- Ícones por linha (padrão: todos em uma linha) -->
![Skills](https://skillicons.dev/icons?i=python,js,nodejs&perline=4)

<!-- Tema claro -->
![Skills](https://skillicons.dev/icons?i=python,js&theme=light)
```

Lista completa de ícones disponíveis: https://skillicons.dev

---

### GitHub Readme Stats — Cards de estatísticas

Gera cards automáticos com suas estatísticas do GitHub.

```markdown
<!-- Estatísticas gerais -->
![Stats](https://github-readme-stats.vercel.app/api?username=SEU_USERNAME&show_icons=true&theme=tokyonight)

<!-- Linguagens mais usadas -->
![Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=SEU_USERNAME&layout=compact&theme=tokyonight)
```

Temas disponíveis: `dark`, `radical`, `tokyonight`, `dracula`, `gruvbox`, `cobalt`, `synthwave`, `highcontrast`

Documentação: https://github.com/anuraghazra/github-readme-stats

---

### GitHub Profile Trophy — Troféus

Exibe troféus baseados nas suas contribuições, commits, seguidores e mais.

```markdown
![Trophies](https://github-profile-trophy.vercel.app/?username=SEU_USERNAME&theme=darkhub&no-frame=true&row=1&column=7)
```

---

### Animação da cobrinha

A cobrinha percorre seu gráfico de contribuições e "come" os quadrados verdes. Funciona via GitHub Actions, que roda automaticamente todo dia.

**1. Crie o arquivo** `.github/workflows/snake.yml` no seu repositório de perfil:

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

**2. Execute o workflow** manualmente na aba **Actions** do repositório.

**3. Use no README:**

```markdown
![Snake](https://raw.githubusercontent.com/SEU_USERNAME/SEU_USERNAME/snake-output/snake.svg)
```

---

### Contador de visitas

Exibe quantas pessoas já visitaram seu perfil.

```markdown
![Visitors](https://komarev.com/ghpvc/?username=SEU_USERNAME&color=1a2a6c&style=flat-square&label=Visitantes+no+perfil)
```

---

## 5. Template Completo

Copie, substitua `SEU_USERNAME` e `SEU_NOME` e personalize à vontade:

```markdown
<!-- Banner -->
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a2a6c,50:3e5abb,100:2b4aad&height=200&section=header&text=SEU_NOME&fontSize=48&fontColor=ffffff&fontAlignY=38&desc=Developer+%7C+Back-end+%7C+Data+Science&descAlignY=58&descSize=18&animation=fadeIn" width="100%"/>
</div>

<!-- Redes sociais -->
<div align="center">
  <a href="https://linkedin.com/in/seu-perfil">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
  </a>
  <a href="mailto:seuemail@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail"/>
  </a>
  <a href="https://github.com/SEU_USERNAME">
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
  </a>
  <a href="https://discord.com/users/SEU_ID">
    <img src="https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Discord"/>
  </a>
</div>

<br/>

<!-- Contador de visitas -->
<div align="center">
  <img src="https://komarev.com/ghpvc/?username=SEU_USERNAME&color=1a2a6c&style=flat-square&label=Visitantes+no+perfil"/>
</div>

## Sobre mim

```python
dev = {
    "nome":       "Seu Nome Completo",
    "localização":"Sua Cidade, Brasil",
    "formação":   "Sua Universidade",
    "interesses": ["Back-end", "Data Science", "Automação"],
    "status":     "Em constante evolução"
}
```

## Tecnologias e Ferramentas

<div align="center">
  <img src="https://skillicons.dev/icons?i=python,js,nodejs,c,lua,git,vscode,sqlite"/>
</div>

## Estatísticas

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=SEU_USERNAME&show_icons=true&theme=tokyonight" height="180"/>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=SEU_USERNAME&layout=compact&theme=tokyonight" height="180"/>
</div>

<br/>

<!-- Cobrinha -->
<div align="center">
  <img src="https://raw.githubusercontent.com/SEU_USERNAME/SEU_USERNAME/snake-output/snake.svg" alt="Snake animation"/>
</div>

<!-- Troféus -->
<div align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=SEU_USERNAME&theme=darkhub&no-frame=true&row=1&column=7" alt="Troféus"/>
</div>

<!-- Footer -->
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a2a6c,50:3e5abb,100:2b4aad&height=100&section=footer" width="100%"/>
</div>
```

---

## 6. Instalando o Git

### Windows

1. Acesse: https://git-scm.com/download/win
2. Baixe o instalador e execute
3. Durante a instalação, mantenha as opções padrão
4. Na etapa **"Choosing the default editor"**, selecione **Visual Studio Code**
5. Conclua a instalação

Verificação após instalar:

```bash
git --version
# Saída esperada: git version 2.x.x.windows.x
```

### Linux — Ubuntu / Debian

```bash
sudo apt update
sudo apt install git -y
git --version
```

### macOS

```bash
# Via Homebrew (recomendado)
brew install git

# Ou via Xcode Command Line Tools
xcode-select --install
```

---

## 7. Configurando o Git

Após instalar, configure seu nome e e-mail. Essas informações ficam registradas em todos os seus commits.

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"
```

> Use o **mesmo e-mail da sua conta do GitHub** para que os commits apareçam corretamente no gráfico de contribuições do seu perfil.

Defina o VS Code como editor padrão do Git:

```bash
git config --global core.editor "code --wait"
```

Verifique todas as configurações:

```bash
git config --list
```

---

## 8. Integrando com VS Code

O VS Code possui suporte nativo ao Git sem necessidade de extensões.

### Abrindo o controle de versão

- Clique no ícone de ramificação na barra lateral esquerda
- Ou use o atalho `Ctrl+Shift+G`
- Ou abra o terminal integrado com `Ctrl+`` ` `` ` para rodar comandos diretamente

### Funcionalidades da aba Source Control

| Ação | Como fazer |
|---|---|
| Ver arquivos modificados | Listados automaticamente na aba Source Control |
| Fazer stage de arquivos | Clicar no `+` ao lado do arquivo |
| Criar um commit | Escrever a mensagem no campo e pressionar `Ctrl+Enter` |
| Publicar no GitHub | Botão **"Publish Branch"** (primeiro push) |
| Sincronizar alterações | Botão **"Sync Changes"** (push + pull) |
| Resolver conflitos de merge | Editor visual integrado com as duas versões lado a lado |

### Extensões recomendadas

**GitLens** — a extensão mais completa para Git no VS Code. Adiciona histórico por linha, blame inline, comparação entre commits e navegação pelo histórico completo do projeto.

**Git Graph** — exibe uma visualização gráfica e interativa de todos os branches e commits do repositório.

**GitHub Pull Requests** — permite criar, revisar e fazer merge de Pull Requests diretamente no editor.

### Autenticando com o GitHub

1. Abra a paleta de comandos: `Ctrl+Shift+P`
2. Digite e selecione: **`GitHub: Sign In`**
3. Siga o fluxo de autenticação no navegador
4. Após autenticar, o VS Code sincroniza automaticamente com seus repositórios

---

## 9. Comandos Git

### Iniciando um projeto

```bash
# Inicializar um repositório do zero na pasta atual
git init

# Clonar um repositório existente do GitHub
git clone https://github.com/usuario/repositorio.git

# Clonar para uma pasta com nome diferente
git clone https://github.com/usuario/repositorio.git minha-pasta
```

### Fluxo básico diário

```bash
# Verificar o estado atual dos arquivos
git status

# Adicionar todos os arquivos modificados para o próximo commit
git add .

# Adicionar um arquivo específico
git add src/main.py

# Criar um commit com mensagem
git commit -m "feat: adiciona tela de login"

# Enviar commits para o GitHub
git push origin main

# Receber atualizações do GitHub
git pull origin main
```

### Branches

```bash
# Listar todas as branches
git branch

# Criar uma nova branch
git branch minha-feature

# Criar e já entrar na branch
git checkout -b minha-feature

# Mudar para uma branch existente
git checkout main

# Mesclar uma branch na branch atual
git merge minha-feature

# Deletar uma branch (após o merge)
git branch -d minha-feature
```

### Histórico e inspeção

```bash
# Ver histórico resumido de commits
git log --oneline

# Ver histórico com gráfico de branches
git log --oneline --graph --all

# Ver o que mudou em um arquivo antes de commitar
git diff arquivo.py

# Ver detalhes de um commit específico
git show abc1234
```

### Desfazendo alterações

```bash
# Descartar alterações não commitadas em um arquivo
git restore arquivo.py

# Remover um arquivo do stage (sem perder as alterações)
git restore --staged arquivo.py

# Desfazer o último commit mantendo as alterações
git reset --soft HEAD~1

# Criar um novo commit que desfaz um commit anterior
git revert abc1234
```

### Padrão de mensagens de commit — Conventional Commits

Adotar um padrão torna o histórico legível e facilita a automação de changelogs.

```
tipo: descrição curta no imperativo

feat:      nova funcionalidade
fix:       correção de bug
docs:      alteração em documentação
style:     formatação, sem mudança de lógica
refactor:  refatoração sem nova feature ou fix
test:      adição ou correção de testes
chore:     tarefas de manutenção, dependências
```

Exemplos:

```bash
git commit -m "feat: adiciona autenticação com JWT"
git commit -m "fix: corrige cálculo de desconto no carrinho"
git commit -m "docs: atualiza instruções de instalação"
git commit -m "refactor: separa lógica de validação em módulo próprio"
```

---

## 10. Boas Práticas

### Perfil

- Mantenha o README **atualizado** — tecnologias desatualizadas passam imagem de abandono
- Use `<div align="center">` para centralizar elementos e deixar o perfil mais limpo visualmente
- Inclua **links funcionais** para LinkedIn, portfólio e projetos em destaque
- **Fixe até 6 repositórios** no topo do perfil em `Perfil → Customize your pins` — escolha seus melhores trabalhos

### Repositórios

- Todo repositório relevante deve ter um `README.md` explicando o projeto, como instalar e como usar
- Use **descrição** e **tópicos (tags)** em cada repositório para facilitar a descoberta por outros desenvolvedores
- Nunca versione arquivos `.env` ou qualquer arquivo com credenciais, tokens ou senhas — use `.gitignore`
- Crie **releases** em projetos com versões públicas

### Commits

- Faça commits **pequenos e frequentes** — um commit por alteração lógica, não um commit gigante no fim do dia
- Escreva mensagens **no imperativo** e em português ou inglês, de forma consistente
- Nunca faça `git add .` sem antes rodar `git status` para saber o que está sendo incluído

### Contribuições e visibilidade

- O gráfico de contribuições fica verde com commits, Pull Requests, issues abertas e code reviews
- Contribua com projetos open source — aparece no histórico público do seu perfil
- Comente issues e PRs — demonstra participação na comunidade

### GitHub Pages

O GitHub oferece hospedagem gratuita para sites estáticos:

1. Crie um repositório com nome `SEU_USERNAME.github.io`
2. Suba um `index.html` na branch `main`
3. Ative em `Settings → Pages → Source: Deploy from a branch → main`
4. Acesse em `https://SEU_USERNAME.github.io`

---

## Recursos

| Recurso | Link |
|---|---|
| Gerador visual de perfil | https://profile-readme-generator.com/pt-BR |
| Shields.io — badges | https://shields.io |
| Skill Icons | https://skillicons.dev |
| Capsule Render — banners | https://github.com/kyechan99/capsule-render |
| GitHub Readme Stats | https://github.com/anuraghazra/github-readme-stats |
| GitHub Profile Trophy | https://github.com/ryo-ma/github-profile-trophy |
| Gerador de .gitignore | https://gitignore.io |
| Conventional Commits | https://www.conventionalcommits.org/pt-br |
| SimpleIcons — logos para badges | https://simpleicons.org |

---

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:161b22,100:21262d&height=100&section=footer" width="100%"/>
  <sub>Guia criado para o minicurso de GitHub</sub>
</div>
