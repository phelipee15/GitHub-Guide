<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:161b22,100:21262d&height=180&section=header&text=Guia%20GitHub&fontSize=44&fontColor=ffffff&fontAlignY=38&desc=Do%20repositório%20ao%20perfil%20profissional&descAlignY=58&descSize=16&animation=fadeIn" width="100%"/>

</div>

---

## Índice

1. [O que é Git e GitHub](#1-o-que-é-git-e-github)
2. [Criando seu primeiro repositório](#2-criando-seu-primeiro-repositório)
3. [Criando seu perfil](#3-criando-seu-perfil)
4. [Ferramentas](#4-ferramentas)
5. [Template Base](#5-template-base)
6. [Instalando o Git](#6-instalando-o-git)
7. [Configurando o Git](#7-configurando-o-git)
8. [Integrando com VS Code](#8-integrando-com-vs-code)
9. [Comandos Git](#9-comandos-git)
10. [Fork](#10-fork)
11. [Issues e Pull Requests](#11-issues-e-pull-requests)
12. [Boas Práticas](#12-boas-práticas)

---

## 1. O que é Git e GitHub

**Git** é um sistema de controle de versão distribuído. Ele rastreia o histórico de alterações do seu código, permite voltar a versões anteriores, trabalhar em equipe sem conflitos e criar ramificações independentes do projeto — tudo isso localmente, no seu computador.

**GitHub** é uma plataforma online que hospeda repositórios Git na nuvem. Além de armazenar código, funciona como portfólio público, rede social para desenvolvedores e ferramenta de colaboração em projetos.

> 💡 **Analogia:** o Git é o histórico de versões de um documento. O GitHub é o Google Drive onde você salva e compartilha esse documento com o mundo.

```
Git    →  ferramenta instalada na sua máquina (controle de versão local)
GitHub →  plataforma na nuvem que armazena e compartilha repositórios Git
```

### Como os dois se conectam

```
┌─────────────────────────────────────────────────────────────┐
│                     SEU COMPUTADOR                          │
│                                                             │
│  📁 Arquivos  ──git add──►  📦 Staging  ──git commit──►  🗂 Repo local  │
│                                                             │
└──────────────────────────────┬──────────────────────────────┘
                               │  git push
                               ▼
                    ┌─────────────────┐
                    │    ☁️ GitHub    │
                    │  (repositório   │
                    │    remoto)      │
                    └─────────────────┘
                               │  git pull
                               ▼
                    recebe atualizações
```

### Conceitos fundamentais

| Conceito | O que é | Analogia |
|---|---|---|
| **Repositório** | Pasta rastreada pelo Git com todo o histórico | Pasta do projeto com memória |
| **Commit** | Registro de uma alteração com mensagem | "Salvar" com descrição do que mudou |
| **Branch** | Ramificação independente do projeto | Rascunho separado do documento original |
| **Merge** | Unificação de duas branches | Copiar as mudanças do rascunho para o original |
| **Clone** | Cópia local de um repositório remoto | Baixar o projeto completo |
| **Push / Pull** | Enviar / receber alterações | Upload / Download das mudanças |

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

> 💡 Gere um `.gitignore` automático para sua linguagem em: https://gitignore.io

---

## 3. Criando seu perfil

### O repositório especial de perfil

O GitHub tem um recurso especial: se você criar um repositório com o **mesmo nome do seu username**, o `README.md` desse repositório é exibido diretamente na sua página de perfil público.

**Como criar:**

1. Clique em **"New repository"**
2. No campo de nome, digite exatamente o seu username (ex: `phelipee15`)
3. O GitHub reconhece automaticamente e exibe a mensagem: *"You found a secret!"*
4. Marque como **Public** e ative **"Add a README file"**
5. Clique em **"Create repository"**

### Estrutura recomendada para o README de perfil

```markdown
<!-- 1. Banner animado no topo -->

<!-- 2. Badges de redes sociais (LinkedIn, GitHub, Discord, etc.) -->

<!-- 3. Bloco "Sobre mim" com suas informações em destaque -->

<!-- 4. Tecnologias e ferramentas que você usa -->

<!-- 5. Projetos em destaque (links para repos) -->

<!-- 6. Footer animado -->
```

---

## 4. Ferramentas

### Gerador visual de perfil

> **https://profile-readme-generator.com/pt-BR**

Interface visual sem precisar escrever código. Você arrasta blocos, preenche os campos e o site gera o Markdown pronto.

---

### Capsule Render — Banners animados

Gera banners animados para o topo e rodapé do README.

```markdown
![Banner](https://capsule-render.vercel.app/api?type=waving&color=0:1a2a6c,100:2b4aad&height=200&section=header&text=Seu+Nome&fontSize=48&fontColor=ffffff&animation=fadeIn)
```

| Parâmetro | Descrição | Valores |
|---|---|---|
| `type` | Estilo do banner | `waving`, `rect`, `soft`, `egg`, `cylinder` |
| `color` | Cor ou gradiente | `#1a2a6c` ou `0:1a2a6c,100:ff6b6b` |
| `text` | Texto exibido | `Seu+Nome` (use `+` no lugar de espaço) |
| `animation` | Animação | `fadeIn`, `twinkling`, `blinking`, `scaleIn` |
| `section` | Posição | `header` ou `footer` |

---

### Shields.io — Badges personalizáveis

```markdown
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
```

Estrutura de uma badge:

```
https://img.shields.io/badge/LABEL-COLOR?style=STYLE&logo=LOGO&logoColor=white
```

---

### Skill Icons — Ícones de tecnologia

```markdown
![Skills](https://skillicons.dev/icons?i=python,js,lua,nodejs,c,git,vscode,sqlite)
```

---

### GitHub Readme Stats — Cards de estatísticas

```markdown
![Stats](https://github-readme-stats.vercel.app/api?username=SEU_USERNAME&show_icons=true&theme=tokyonight)
![Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=SEU_USERNAME&layout=compact&theme=tokyonight)
```

Temas: `dark`, `radical`, `tokyonight`, `dracula`, `gruvbox`, `cobalt`, `synthwave`

---

### Animação da cobrinha

Crie o arquivo `.github/workflows/snake.yml` no repositório de perfil:

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

Depois use no README:

```markdown
![Snake](https://raw.githubusercontent.com/SEU_USERNAME/SEU_USERNAME/snake-output/snake.svg)
```

---

## 5. Template Base

```markdown
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a2a6c,50:3e5abb,100:2b4aad&height=200&section=header&text=SEU_NOME&fontSize=48&fontColor=ffffff&fontAlignY=38&desc=Developer+%7C+Área+1+%7C+Área+2&descAlignY=58&descSize=18&animation=fadeIn" width="100%"/>
</div>

<div align="center">
  <a href="https://linkedin.com/in/SEU_PERFIL">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/>
  </a>
  <a href="mailto:SEU_EMAIL@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white"/>
  </a>
</div>

<br/>

## Sobre mim

Escreva aqui uma apresentação direta: quem você é, onde estuda ou trabalha, no que está focado agora.

## Tecnologias e Ferramentas

<div align="center">
  <img src="https://skillicons.dev/icons?i=python,js,nodejs,git,vscode"/>
</div>

## Projetos em destaque

| Projeto | Descrição | Tecnologias |
|---|---|---|
| [nome-do-projeto](https://github.com/SEU_USERNAME/nome-do-projeto) | Breve descrição | Python, SQLite |

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a2a6c,50:3e5abb,100:2b4aad&height=100&section=footer" width="100%"/>
</div>
```

---

## 6. Instalando o Git

### Windows

1. Acesse: https://git-scm.com/download/win
2. Baixe o instalador e execute
3. Na etapa **"Choosing the default editor"**, selecione **Visual Studio Code**
4. Conclua a instalação

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
brew install git
```

---

## 7. Configurando o Git

Após instalar, configure seu nome e e-mail. Use o **mesmo e-mail da conta GitHub** para os commits aparecerem no gráfico de contribuições.

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"
git config --global core.editor "code --wait"

# Verificar todas as configurações
git config --list
```

---

## 8. Integrando com VS Code

O VS Code possui suporte nativo ao Git sem necessidade de extensões.

- Ícone de ramificação na barra lateral esquerda → `Ctrl+Shift+G`
- Terminal integrado → `` Ctrl+` ``

| Ação | Como fazer |
|---|---|
| Ver arquivos modificados | Listados automaticamente na aba Source Control |
| Fazer stage de arquivos | Clicar no `+` ao lado do arquivo |
| Criar um commit | Escrever a mensagem e pressionar `Ctrl+Enter` |
| Publicar no GitHub | Botão **"Publish Branch"** |
| Sincronizar alterações | Botão **"Sync Changes"** |

**Extensões recomendadas:** GitLens, Git Graph, GitHub Pull Requests

---

## 9. Comandos Git

### O fluxo do dia a dia

```
┌──────────────┐     git add      ┌──────────────┐    git commit    ┌──────────────┐    git push    ┌──────────────┐
│  Seus        │ ───────────────► │   Staging    │ ───────────────► │  Repo local  │ ─────────────► │   GitHub     │
│  arquivos    │                  │  (preparado) │                  │  (commitado) │                │  (remoto)    │
└──────────────┘                  └──────────────┘                  └──────────────┘                └──────────────┘
                                                                                                            │
                                                                           git pull ◄───────────────────────┘
```

### Iniciando um projeto

```bash
git init                                     # repositório do zero
git clone https://github.com/user/repo.git  # clonar existente
```

### Fluxo básico diário

```bash
git status                          # ver o que mudou
git add .                           # preparar todos os arquivos
git add src/main.py                 # preparar arquivo específico
git commit -m "feat: adiciona tela de login"
git push origin main                # enviar para o GitHub
git pull origin main                # receber atualizações
```

### Branches

Uma branch é uma linha de desenvolvimento independente. Você trabalha nela sem afetar o código principal.

```
Antes da branch:

main  ──●──●──●

Depois de criar e trabalhar na branch:

main  ──●──●──●────────────────────●  (merge commit)
                \                 /
feature/login    ●──●──●──●──────
```

```bash
git checkout -b minha-feature       # criar e entrar na branch
git checkout main                   # voltar para a main
git branch                          # listar branches
git branch -d minha-feature         # deletar branch local (após merge)
```

**Convenção de nomes:**

| Prefixo | Uso | Exemplo |
|---|---|---|
| `feature/` | Nova funcionalidade | `feature/tela-login` |
| `fix/` | Correção de bug | `fix/calculo-desconto` |
| `docs/` | Documentação | `docs/atualiza-readme` |
| `hotfix/` | Correção urgente em produção | `hotfix/falha-pagamento` |

> ⚠️ **Nunca desenvolva diretamente na `main`.** Ela deve sempre refletir o código estável.

### Merge — Unindo branches

```bash
git checkout main          # 1. entre na branch que vai RECEBER
git pull origin main       # 2. atualize com o GitHub
git merge feature/login    # 3. faça o merge
git push origin main       # 4. envie o resultado
```

### Conflitos de merge

Um conflito acontece quando duas pessoas editaram o **mesmo trecho do mesmo arquivo** em branches diferentes. O Git não sabe qual versão manter e pede que você decida.

```
Situação típica:

João editou a linha 15 de app.py na branch feature/login
Maria editou a mesma linha 15 na branch feature/cadastro
                      ↓
              CONFLITO ao fazer merge
```

Como o conflito aparece no arquivo:

```python
<<<<<<< HEAD          ← sua versão atual
def saudacao():
    return "Olá, usuário!"
=======               ← separador
def saudacao():
    return "Bem-vindo ao sistema!"
>>>>>>> feature/cadastro  ← versão chegando
```

**Como resolver:**

1. Abra o arquivo no VS Code — ele destaca os conflitos com botões acima de cada bloco
2. Escolha qual versão manter (ou escreva uma terceira combinando as duas)
3. Remova **todas** as marcações (`<<<<<<<`, `=======`, `>>>>>>>`)
4. Salve e commite:

```bash
git add app.py
git commit -m "fix: resolve conflito de merge na função saudacao"
```

No VS Code aparecem os botões: **Accept Current Change**, **Accept Incoming Change**, **Accept Both Changes**.

### Fluxo seguro para trabalho em equipe

```
┌─────────────────────────────────────────────────────────┐
│  SEMPRE comece assim antes de qualquer coisa:           │
│                                                         │
│  git checkout main                                      │
│  git pull origin main                                   │
└─────────────────────────────────────────────────────────┘
         │
         ▼
  git checkout -b feature/nome-da-tarefa
         │
         ▼
  Desenvolva e commite com frequência
  git add . && git commit -m "feat: ..."
         │
         ▼
  Antes do merge: traga mudanças da main
  git merge main   ← resolve conflitos aqui, não depois
         │
         ▼
  git push origin feature/nome-da-tarefa
         │
         ▼
  Abra um Pull Request no GitHub para revisão
```

> ⚠️ **Nunca use `git push --force` em branches compartilhadas.** Isso sobrescreve o histórico remoto e pode apagar o trabalho de outras pessoas permanentemente.

### Histórico e inspeção

```bash
git log --oneline                   # histórico resumido
git log --oneline --graph --all     # histórico com gráfico de branches
git diff arquivo.py                 # ver o que mudou antes de commitar
git show abc1234                    # detalhes de um commit específico
```

### Desfazendo alterações

```bash
git restore arquivo.py              # descartar mudanças não commitadas
git restore --staged arquivo.py     # remover do stage
git reset --soft HEAD~1             # desfazer o último commit (mantém mudanças)
git revert abc1234                  # criar commit que desfaz outro
```

### Stash — Guardando trabalho inacabado

O stash funciona como uma gaveta temporária. Guarda o que você estava fazendo para poder trocar de branch e depois recupera tudo de onde parou.

```
Situação:  você está no meio de uma feature quando chega um bug urgente
                                ↓
          Você NÃO pode commitar código incompleto
                                ↓
                Use git stash!
```

```bash
git stash push -m "feature login: formulário pela metade"
git stash list                      # ver o que está guardado
git stash pop                       # recuperar o mais recente e remover do stash
git stash apply stash@{1}           # recuperar um específico (mantém no stash)
git stash drop stash@{0}            # remover sem aplicar
git stash clear                     # limpar tudo
```

**Fluxo completo:**

```bash
# 1. Guarda o trabalho inacabado
git stash push -m "login: validação incompleta"

# 2. Corrige o bug urgente em outra branch
git checkout main
git checkout -b fix/bug-urgente
# ... faz a correção e commita ...
git push origin fix/bug-urgente

# 3. Volta para a feature e recupera
git checkout feature/login
git stash pop   ← código volta exatamente como estava
```

### Padrão de mensagens de commit — Conventional Commits

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

```bash
git commit -m "feat: adiciona autenticação com JWT"
git commit -m "fix: corrige cálculo de desconto no carrinho"
git commit -m "docs: atualiza instruções de instalação"
git commit -m "refactor: separa lógica de validação em módulo próprio"
```

---

## 10. Fork

Um fork cria uma cópia completa de um repositório de **outra pessoa** na sua conta do GitHub.

```
Repositório original            Seu fork
github.com/outro/projeto   →   github.com/SEU_USERNAME/projeto
        │                               │
        │                               │  você pode modificar
        │                               │  sem afetar o original
        └───── Pull Request ────────────┘
               (proposta de contribuição)
```

**Quando usar:** contribuir com projetos open source que você não tem permissão de editar diretamente.

```bash
# Clone o SEU fork (não o original)
git clone https://github.com/SEU_USERNAME/nome-do-repo.git
cd nome-do-repo

# Adicione o repositório original como remote "upstream"
git remote add upstream https://github.com/outro-usuario/nome-do-repo.git

# Manter o fork atualizado com o original:
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

---

## 11. Issues e Pull Requests

```
Issue   →  "existe um problema ou uma ideia"  (discussão)
PR      →  "aqui está a solução em código"     (revisão + merge)
```

### Fluxo completo com Issues e PRs

```
1. Issue aberta: "Formulário de login não valida e-mail" (#42)
         │
         ▼
2. Dev cria branch: fix/validacao-email
         │
         ▼
3. Commit referenciando a issue:
   git commit -m "fix: valida formato de e-mail — closes #42"
         │
         ▼
4. Push + Pull Request aberto no GitHub
         │
         ▼
5. Reviewer aprova ou solicita ajustes
         │
         ▼
6. Merge → Issue #42 fechada automaticamente
         │
         ▼
7. Branch deletada
```

### Anatomia de uma boa Issue

```markdown
## Descrição
Explique claramente o problema ou a funcionalidade desejada.

## Como reproduzir (para bugs)
1. Acesse a tela X
2. Clique em Y
3. Observe o erro Z

## Comportamento esperado
O que deveria acontecer.

## Ambiente
- OS: Ubuntu 22.04 / Node.js: v20.10
```

### Labels — Organizando por categoria

| Label | Uso |
|---|---|
| `bug` | Algo não está funcionando |
| `enhancement` | Nova funcionalidade ou melhoria |
| `good first issue` | Boa para quem está começando a contribuir |
| `help wanted` | Precisa de ajuda extra |
| `documentation` | Melhorias na documentação |

### Referenciando Issues em commits

```bash
git commit -m "fix: corrige validação — closes #42"
git commit -m "feat: autenticação — fixes #17, resolves #18"
# "relacionado a" sem fechar:
git commit -m "refactor: simplifica login (relacionado a #30)"
```

### Como abrir um Pull Request

1. Faça push da sua branch
2. O GitHub exibe o banner **"Compare & pull request"** — clique nele
3. Selecione branch de origem (sua feature) e destino (`main`)
4. Preencha título e descrição
5. Adicione reviewers, labels e milestone
6. Clique em **"Create pull request"**

### Modelo de descrição de PR

```markdown
## O que foi feito
Descrição clara das mudanças implementadas.

## Como testar
1. Clone a branch `feature/nome`
2. Execute `npm install`
3. Acesse a rota `/login` e teste

## Checklist
- [ ] Código testado localmente
- [ ] Sem conflitos com a main
- [ ] Documentação atualizada (se necessário)
- [ ] Sem `console.log` ou código de debug esquecido

## Issues relacionadas
Closes #42
```

### Tipos de merge no GitHub

```
Merge commit      →  preserva todo o histórico da branch
Squash and merge  →  junta todos os commits em um só (main mais limpa) ← mais comum
Rebase and merge  →  reaplica commits sem criar merge commit
```

### Draft Pull Requests

Um **Draft PR** sinaliza que o trabalho ainda está em andamento. Clique na seta ao lado de **"Create pull request"** → **"Create draft pull request"**. Quando estiver pronto, clique em **"Ready for review"**.

---

## 12. Boas Práticas

### Perfil

- Mantenha o README **atualizado** — tecnologias desatualizadas passam imagem de abandono
- Inclua **links funcionais** para LinkedIn, portfólio e projetos em destaque
- **Fixe até 6 repositórios** no topo do perfil em `Perfil → Customize your pins`

### Repositórios

- Todo repositório relevante deve ter um `README.md` explicando o projeto
- Use **descrição e tópicos (tags)** em cada repositório
- Nunca versione arquivos `.env` ou credenciais — use `.gitignore`
- Adicione um arquivo `LICENSE` — sem ele ninguém tem permissão legal para usar seu código

### Commits

- Faça commits **pequenos e frequentes** — um por alteração lógica
- Sempre rode `git status` antes de `git add .`
- Use `git commit --amend` para corrigir a última mensagem **antes** de fazer push

### Issues e Pull Requests

- **Sempre abra uma Issue antes de começar** a trabalhar em algo novo — evita duplicação
- PRs devem ser **pequenos e focados** — um por funcionalidade
- Use **branch protection rules** na main para exigir pelo menos uma aprovação antes do merge

### GitHub Pages — hospedagem gratuita

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
| SimpleIcons — logos | https://simpleicons.org |
| Escolher uma licença | https://choosealicense.com |

---

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:161b22,100:21262d&height=100&section=footer" width="100%"/>
  <sub>Guia criado para o minicurso de GitHub</sub>
</div>
