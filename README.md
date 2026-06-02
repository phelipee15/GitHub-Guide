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

<!-- 6. Footer animado -->
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

## 5. Template Base

Copie, substitua os campos marcados e personalize à vontade. Este é um ponto de partida limpo e funcional — sem dependências externas que possam quebrar.

```markdown
<!-- Banner -->
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a2a6c,50:3e5abb,100:2b4aad&height=200&section=header&text=SEU_NOME&fontSize=48&fontColor=ffffff&fontAlignY=38&desc=Developer+%7C+Área+1+%7C+Área+2&descAlignY=58&descSize=18&animation=fadeIn" width="100%"/>
</div>

<!-- Redes sociais -->
<div align="center">
  <a href="https://linkedin.com/in/SEU_PERFIL">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
  </a>
  <a href="mailto:SEU_EMAIL@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail"/>
  </a>
  <a href="https://github.com/SEU_USERNAME">
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
  </a>
  <a href="https://discord.com/users/SEU_ID_DISCORD">
    <img src="https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Discord"/>
  </a>
</div>

<br/>

## Sobre mim

Escreva aqui uma apresentação direta: quem você é, onde estuda ou trabalha, no que está focado agora e o que te interessa na área de tecnologia.

## Tecnologias e Ferramentas

<div align="center">
  <img src="https://skillicons.dev/icons?i=python,js,nodejs,git,vscode"/>
</div>

## Projetos em destaque

| Projeto | Descrição | Tecnologias |
|---|---|---|
| [nome-do-projeto](https://github.com/SEU_USERNAME/nome-do-projeto) | Breve descrição do que ele faz | Python, SQLite |
| [outro-projeto](https://github.com/SEU_USERNAME/outro-projeto) | Breve descrição do que ele faz | Node.js, API REST |

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

Uma branch é uma linha de desenvolvimento independente. Ela permite que você trabalhe em uma funcionalidade ou correção sem afetar o código principal — e sem afetar o trabalho dos outros membros do time.

```
main ──●──────────────────────●── (produção, sempre estável)
        \                    /
         ●──●──●  feature/login  (seu trabalho isolado)
```

```bash
# Listar todas as branches locais
git branch

# Listar branches locais e remotas
git branch -a

# Criar uma nova branch
git branch minha-feature

# Criar e já entrar na branch (forma mais usada)
git checkout -b minha-feature

# Mudar para uma branch existente
git checkout main

# Renomear a branch atual
git branch -m novo-nome

# Deletar uma branch local (após o merge)
git branch -d minha-feature

# Forçar deleção (mesmo sem merge — cuidado)
git branch -D minha-feature
```

**Convenção de nomes para branches:**

| Prefixo | Uso | Exemplo |
|---|---|---|
| `feature/` | Nova funcionalidade | `feature/tela-login` |
| `fix/` | Correção de bug | `fix/calculo-desconto` |
| `docs/` | Documentação | `docs/atualiza-readme` |
| `refactor/` | Refatoração | `refactor/modulo-auth` |
| `hotfix/` | Correção urgente em produção | `hotfix/falha-pagamento` |

> Nunca desenvolva diretamente na branch `main`. Ela deve sempre refletir o código estável e funcional.

---

### Merge — Unindo branches

O merge integra o histórico de uma branch em outra. É o passo final depois que uma funcionalidade está pronta e testada.

```bash
# 1. Volte para a branch que vai RECEBER as alterações
git checkout main

# 2. Atualize ela com o que está no GitHub
git pull origin main

# 3. Faça o merge da sua feature
git merge feature/tela-login

# 4. Envie o resultado para o GitHub
git push origin main
```

**O que acontece internamente:**

```
Antes do merge:

main     ──●──●──●
                  \
feature            ●──●──●


Depois do merge:

main     ──●──●──●──────────────●  (merge commit)
                  \            /
feature            ●──●──●────
```

---

### Conflitos de merge — O que são e como resolver

Um conflito acontece quando duas pessoas editaram **o mesmo trecho do mesmo arquivo** em branches diferentes. O Git não sabe qual versão manter e pede que você decida.

**Situação típica que gera conflito:**

```
João editou a linha 15 do arquivo app.py na branch feature/login
Maria editou a mesma linha 15 do mesmo arquivo na branch feature/cadastro
Quando alguém faz merge, o Git encontra duas versões incompatíveis
```

**Como o conflito aparece no arquivo:**

```python
<<<<<<< HEAD  (versão atual — branch que está recebendo o merge)
def saudacao():
    return "Olá, usuário!"
=======
def saudacao():
    return "Bem-vindo ao sistema!"
>>>>>>> feature/cadastro  (versão que está chegando pelo merge)
```

**Como resolver:**

1. Abra o arquivo com conflito no VS Code — ele destaca os conflitos visualmente
2. Escolha qual versão manter, ou escreva uma terceira versão combinando as duas
3. Remova **todas** as marcações (`<<<<<<<`, `=======`, `>>>>>>>`)
4. Salve o arquivo
5. Faça o commit do resultado:

```bash
git add app.py
git commit -m "fix: resolve conflito de merge na função saudacao"
```

**No VS Code**, ao abrir um arquivo com conflito, aparecem botões acima de cada bloco:

- **Accept Current Change** — mantém a versão da sua branch
- **Accept Incoming Change** — mantém a versão que está chegando
- **Accept Both Changes** — inclui as duas versões, uma após a outra
- **Compare Changes** — abre uma view lado a lado para comparar

---

### Como evitar sobrescrever o código de outra pessoa

Este é o erro mais comum em times. Seguir este fluxo protege você e sua equipe:

**Regra 1 — Sempre atualize sua branch antes de fazer merge**

```bash
# Antes de fazer merge de qualquer coisa, traga o que há de novo na main
git checkout main
git pull origin main

# Agora volte para a sua feature e aplique as mudanças da main nela
git checkout feature/minha-feature
git merge main
# Se houver conflitos, resolva agora — antes de mexer no código do time
```

**Regra 2 — Use `git pull` antes de qualquer `git push`**

```bash
# Sempre puxe antes de enviar
git pull origin main
git push origin main
```

Se você tentar fazer push sem antes puxar as atualizações, o Git vai rejeitar e pedir que você resolva as diferenças localmente primeiro — o que é o comportamento correto.

**Regra 3 — Nunca faça `git push --force` na branch principal**

O `--force` sobrescreve o histórico remoto sem aviso. Se alguém tiver commits que você não tem localmente, eles somem permanentemente.

```bash
# NÃO FAÇA isso em branches compartilhadas
git push --force origin main  # destrói o trabalho de outras pessoas

# Se precisar corrigir sua própria branch de feature (somente sua)
git push --force origin feature/minha-feature  # aceitável com cuidado
```

**Regra 4 — Comunique antes de mexer em arquivos críticos**

Arquivos como `package.json`, `requirements.txt`, arquivos de configuração e de banco de dados são alterados com frequência por todos. Se alguém do time for alterar esses arquivos, avisar antes evita a maioria dos conflitos.

---

### Fluxo seguro para trabalho em equipe

```bash
# 1. Sempre comece atualizando a main
git checkout main
git pull origin main

# 2. Crie uma branch para sua tarefa
git checkout -b feature/nome-da-tarefa

# 3. Desenvolva e faça commits frequentes
git add .
git commit -m "feat: descrição do que foi feito"

# 4. Antes de fazer merge, atualize sua branch com a main
git merge main
# Resolva conflitos se houver

# 5. Envie sua branch para o GitHub
git push origin feature/nome-da-tarefa

# 6. Abra um Pull Request no GitHub para revisão
# (Settings → Pull Requests → New Pull Request)

# 7. Após aprovação e merge, delete a branch
git branch -d feature/nome-da-tarefa
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

### Stash — Guardando trabalho inacabado

O stash funciona como uma gaveta temporária. Você guarda as alterações que ainda não quer commitar, limpa o ambiente de trabalho, faz o que precisa em outra branch e depois recupera tudo de onde parou.

**Cenário típico:** você está desenvolvendo uma feature no meio, quando chega uma correção urgente de bug que precisa ser feita agora na `main`. Você não pode fazer commit de um código incompleto — é aí que o stash entra.

```bash
# Guardar todas as alterações atuais no stash
git stash

# Guardar com uma descrição (recomendado)
git stash push -m "feature login: formulário pela metade"

# Listar tudo que está guardado no stash
git stash list
# Saída: stash@{0}: feature login: formulário pela metade
#        stash@{1}: WIP on main: ajuste de layout

# Recuperar o stash mais recente (mantém no stash)
git stash apply

# Recuperar um stash específico pelo índice
git stash apply stash@{1}

# Recuperar o mais recente E remover do stash
git stash pop

# Remover um stash específico sem aplicar
git stash drop stash@{0}

# Limpar todo o stash
git stash clear
```

**Fluxo completo com stash:**

```bash
# 1. Você está na feature/login com código inacabado
git stash push -m "login: validação do formulário incompleta"

# 2. Troca para a main e corrige o bug urgente
git checkout main
git checkout -b fix/bug-urgente
# ... faz a correção ...
git commit -m "fix: corrige falha no cálculo de frete"
git push origin fix/bug-urgente

# 3. Volta para a feature e recupera o trabalho
git checkout feature/login
git stash pop
# Código volta exatamente como estava
```

> O stash salva apenas arquivos rastreados pelo Git. Arquivos novos que ainda não passaram por `git add` não entram no stash por padrão. Use `git stash push -u` para incluí-los.

---

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

## 10. Fork

Um fork cria uma cópia completa de um repositório de **outra pessoa** na sua conta do GitHub. Diferente do clone (que só baixa localmente), o fork existe no GitHub e mantém uma ligação com o repositório original.

```
Repositório original       Seu fork (cópia na sua conta)
github.com/outro/projeto → github.com/SEU_USERNAME/projeto
```

**Quando usar fork:**

- Contribuir com um projeto open source que você não tem permissão de editar diretamente
- Usar um projeto alheio como base para o seu próprio, mantendo o histórico de origem
- Experimentar mudanças no código de outra pessoa sem afetar o original

**Como fazer um fork:**

1. Acesse o repositório que deseja no GitHub
2. Clique no botão **"Fork"** no canto superior direito
3. Escolha sua conta como destino
4. O GitHub cria uma cópia em `github.com/SEU_USERNAME/nome-do-repo`

**Clonando seu fork localmente:**

```bash
# Clone o SEU fork (não o original)
git clone https://github.com/SEU_USERNAME/nome-do-repo.git
cd nome-do-repo

# Adicione o repositório original como remote "upstream"
# Isso permite receber atualizações do projeto original
git remote add upstream https://github.com/outro-usuario/nome-do-repo.git

# Verificar os remotes configurados
git remote -v
# origin    https://github.com/SEU_USERNAME/nome-do-repo.git  (seu fork)
# upstream  https://github.com/outro-usuario/nome-do-repo.git (original)
```

**Mantendo o fork atualizado com o original:**

```bash
# Buscar as atualizações do repositório original
git fetch upstream

# Aplicar na sua main local
git checkout main
git merge upstream/main

# Enviar para o seu fork no GitHub
git push origin main
```

---

## 11. Issues e Pull Requests

Issues e Pull Requests são os dois pilares da colaboração no GitHub. Eles transformam um repositório em um espaço de trabalho organizado, onde cada tarefa tem rastreamento e cada mudança de código passa por revisão.

```
Issue   →  "existe um problema ou uma ideia"  (discussão)
PR      →  "aqui está a solução em código"     (revisão + merge)
```

---

### Issues — Rastreando tarefas e bugs

Uma **Issue** é um registro público (ou privado) de qualquer coisa que precisa ser feita ou discutida no projeto: um bug encontrado, uma feature sugerida, uma dúvida, uma melhoria de documentação.

**Como criar uma Issue:**

1. Acesse o repositório no GitHub
2. Clique na aba **"Issues"**
3. Clique em **"New issue"**
4. Preencha o título e a descrição
5. Opcionalmente configure os campos à direita:
   - **Assignees** — quem vai resolver
   - **Labels** — categoria da issue
   - **Milestone** — versão ou sprint a que pertence
   - **Projects** — vincula a um quadro Kanban
6. Clique em **"Submit new issue"**

**Anatomia de uma boa Issue:**

```markdown
## Descrição
Explique claramente o problema ou a funcionalidade desejada.

## Como reproduzir (para bugs)
1. Acesse a tela X
2. Clique em Y
3. Observe o erro Z

## Comportamento esperado
Descreva o que deveria acontecer.

## Comportamento atual
Descreva o que acontece de fato.

## Ambiente
- OS: Ubuntu 22.04
- Node.js: v20.10
- Versão do projeto: 1.3.2
```

---

### Labels — Organizando por categoria

As labels são etiquetas coloridas que classificam as issues e PRs. O GitHub já cria algumas por padrão, e você pode criar as suas.

**Labels padrão do GitHub:**

| Label | Cor | Uso |
|---|---|---|
| `bug` | Vermelho | Algo não está funcionando |
| `enhancement` | Azul | Nova funcionalidade ou melhoria |
| `documentation` | Azul escuro | Melhorias na documentação |
| `good first issue` | Verde | Boa para quem está começando a contribuir |
| `help wanted` | Verde | Precisa de ajuda extra |
| `question` | Rosa | Dúvida ou pedido de informação |
| `wontfix` | Branco | Não será corrigido/implementado |
| `duplicate` | Cinza | Já existe outra issue igual |
| `invalid` | Amarelo | Issue não é válida |

**Criando labels personalizadas:**

1. Acesse `Issues → Labels → New label`
2. Digite o nome, escolha a cor e salve
3. Aplique em qualquer issue ou PR pelo painel lateral

**Exemplo de conjunto de labels para um projeto:**

```
priority: high    → vermelho escuro
priority: medium  → laranja
priority: low     → amarelo
type: bug         → vermelho
type: feature     → azul
type: docs        → azul escuro
status: in review → roxo
status: blocked   → preto
```

---

### Milestones — Agrupando por versão ou sprint

Uma **Milestone** agrupa issues e PRs em torno de um objetivo, versão ou data. Ao associar itens a uma milestone, o GitHub mostra automaticamente o progresso percentual.

**Como criar:**

1. Acesse `Issues → Milestones → New milestone`
2. Dê um título (ex: `v1.0.0` ou `Sprint 3`)
3. Adicione uma descrição e, opcionalmente, uma data de entrega
4. Salve e comece a associar issues a ela pelo painel lateral

---

### Referenciando Issues em commits e PRs

O GitHub entende referências a issues em mensagens de commit e no corpo de PRs. Você pode fechar uma issue automaticamente ao fazer merge de um PR.

**Palavras-chave que fecham a issue automaticamente no merge:**

```bash
# Nos commits
git commit -m "fix: corrige validação do formulário — closes #42"
git commit -m "feat: adiciona autenticação — fixes #17, resolves #18"

# No corpo do Pull Request
"Closes #42"
"Fixes #17"
"Resolves #55"
```

**Apenas referenciar sem fechar:**

```bash
git commit -m "refactor: simplifica lógica de login (relacionado a #30)"
# Cria um link para a issue sem fechá-la
```

---

### Pull Requests — Propondo e revisando código

Um **Pull Request** (PR) é uma proposta formal para integrar as alterações de uma branch em outra. Antes do merge, o código fica disponível para revisão, discussão e aprovação.

```
feature/login ──●──●──●
                        \
                         ─── PR aberto ──→ revisão ──→ merge ──→ main
```

**Como abrir um Pull Request:**

1. Faça push da sua branch para o GitHub
2. O GitHub exibe automaticamente o banner **"Compare & pull request"** — clique nele
   - Ou acesse a aba **"Pull requests"** → **"New pull request"**
3. Selecione a branch de origem (sua feature) e a branch de destino (geralmente `main`)
4. Preencha o título e a descrição do PR
5. Configure os campos laterais:
   - **Reviewers** — quem vai revisar o código
   - **Assignees** — quem é responsável pelo PR
   - **Labels** — categorize o PR
   - **Milestone** — vincule a uma versão
6. Clique em **"Create pull request"**

**Modelo de descrição de PR:**

```markdown
## O que foi feito
Descrição clara e objetiva das mudanças implementadas.

## Como testar
1. Clone a branch `feature/nome`
2. Execute `npm install`
3. Acesse a rota `/login` e teste o formulário

## Checklist
- [ ] Código testado localmente
- [ ] Sem conflitos com a main
- [ ] Documentação atualizada (se necessário)
- [ ] Sem `console.log` ou código de debug esquecido

## Issues relacionadas
Closes #42
```

---

### Revisando um Pull Request

Quando você é adicionado como **Reviewer**, o GitHub notifica você por e-mail. Para revisar:

1. Acesse o PR e vá na aba **"Files changed"**
2. Leia o diff (as linhas em vermelho foram removidas, as verdes foram adicionadas)
3. Para comentar em uma linha específica, passe o mouse sobre ela e clique no `+`
4. Adicione sugestões de mudança diretamente no código:

````markdown
```suggestion
return res.status(400).json({ error: "Campo obrigatório" });
```
````

5. Ao terminar, clique em **"Review changes"** e escolha:
   - **Comment** — deixa comentários sem aprovar nem bloquear
   - **Approve** — aprova o PR para merge
   - **Request changes** — solicita alterações antes do merge

---

### Tipos de merge no GitHub

Ao clicar em **"Merge pull request"**, o GitHub oferece três estratégias:

| Tipo | O que faz | Quando usar |
|---|---|---|
| **Merge commit** | Cria um commit de merge preservando todo o histórico da branch | Projetos que valorizam histórico completo |
| **Squash and merge** | Junta todos os commits da branch em um único commit na main | Manter a main com histórico limpo e linear |
| **Rebase and merge** | Reaplica os commits da branch um a um na main, sem commit de merge | Times que preferem histórico linear sem merge commits |

> A estratégia mais comum em projetos de equipe é o **Squash and merge** — mantém a main limpa enquanto a branch de feature pode ter quantos commits intermediários forem necessários.

---

### Draft Pull Requests

Um **Draft PR** sinaliza que o trabalho ainda está em andamento e que o PR **não está pronto para revisão**. É útil para visibilidade antecipada e para pedir feedback informal sem iniciar o processo formal de aprovação.

**Como criar:**

1. Ao abrir o PR, clique na seta ao lado de **"Create pull request"**
2. Selecione **"Create draft pull request"**

Quando estiver pronto, clique em **"Ready for review"** para converter em PR normal.

---

### Fluxo completo com Issues e PRs

```
1. Alguém abre uma Issue descrevendo o bug ou a feature
   └─ Issue #42: "Formulário de login não valida e-mail"

2. Um dev é atribuído e cria uma branch a partir da main
   └─ git checkout -b fix/validacao-email

3. Desenvolve, commita com referência à issue
   └─ git commit -m "fix: valida formato de e-mail — closes #42"

4. Faz push e abre um Pull Request
   └─ PR: "fix: validação de e-mail no formulário de login"
   └─ Closes #42

5. Reviewer aprova ou solicita ajustes

6. Merge é feito → Issue #42 é fechada automaticamente

7. Branch é deletada
```

---

## 12. Boas Práticas

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
- Adicione um arquivo `LICENSE` — sem ele, ninguém tem permissão legal para usar seu código. Para projetos abertos, as mais comuns são MIT, Apache 2.0 e GPL 3.0
- Use **GitHub Projects** (quadros Kanban) para organizar tarefas em repositórios colaborativos — fica integrado diretamente com Issues e PRs

### Commits

- Faça commits **pequenos e frequentes** — um commit por alteração lógica, não um commit gigante no fim do dia
- Escreva mensagens **no imperativo** e em português ou inglês, de forma consistente
- Nunca faça `git add .` sem antes rodar `git status` para saber o que está sendo incluído
- Use **`git commit --amend`** para corrigir a mensagem ou adicionar arquivos esquecidos no último commit **antes** de fazer push — nunca depois

### Issues

- **Sempre abra uma Issue antes de começar a trabalhar** em algo novo — isso evita duplicação de esforço em times
- Use **labels e milestones** desde o início do projeto; organizar retroativamente é muito mais trabalhoso
- Feche issues via commits e PRs usando as palavras-chave (`closes`, `fixes`, `resolves`) — mantém o rastreamento automático e o histórico conectado
- Se uma issue for muito grande, quebre em issues menores e use **task lists** dentro dela:

```markdown
## Tarefas
- [x] Criar estrutura do banco de dados
- [ ] Implementar endpoint de autenticação
- [ ] Escrever testes unitários
- [ ] Atualizar documentação
```

### Pull Requests

- **Nunca faça PR direto para a main** sem revisão em projetos colaborativos — use branch protection rules (`Settings → Branches → Add rule`)
- PRs devem ser **pequenos e focados** — um PR por funcionalidade ou correção. PRs com 50+ arquivos alterados são difíceis de revisar e propensos a passar bugs despercebidos
- Responda **todos os comentários** de review antes de solicitar uma nova rodada de revisão — mesmo que seja apenas um "feito" ou "discordei, aqui está o motivo"
- Use **Draft PRs** para trabalho em andamento que precisa de visibilidade antecipada, mas ainda não está pronto para revisão formal
- Configure **branch protection** na main para exigir pelo menos uma aprovação antes do merge — isso evita merges acidentais e mantém a qualidade do código

### Contribuições e visibilidade

- O gráfico de contribuições fica verde com commits, Pull Requests, issues abertas e code reviews
- Contribua com projetos open source — aparece no histórico público do seu perfil
- Comente issues e PRs — demonstra participação na comunidade
- **Participe de discussões** em issues de projetos que você usa — reportar bugs bem documentados e sugerir features com argumentação técnica são formas de contribuir mesmo sem escrever código

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
| Escolher uma licença | https://choosealicense.com |

---

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:161b22,100:21262d&height=100&section=footer" width="100%"/>
  <sub>Guia criado para o minicurso de GitHub</sub>
</div>
