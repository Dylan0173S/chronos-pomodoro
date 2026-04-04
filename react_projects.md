# Guia de Configuração: React + Vite + TypeScript (SWC)

Este guia consolida os passos para preparar o ambiente de desenvolvimento e
criar projetos React modernos utilizando o **SWC** (Speedy Web Compiler) para
máxima performance.

---

## Pré-requisitos (Instalação)

Antes de iniciar, certifique-se de ter as ferramentas instaladas:

- **VS Code:** [Download](https://code.visualstudio.com/)
- **Node.js (LTS):** [Download](https://nodejs.org/)
- **Git:** [Download](https://gitforwindows.org/)

---

### Verificação de Versão

No terminal (**PowerShell** ou **CMD**), execute:

> No powershell:

node -v; npm -v; git --version

> No CMD:

node -v && npm -v && git --version

---

## Como resolver o erro do NPM

[Permissões do PowerShell (Administrador)] Set-ExecutionPolicy RemoteSigned

> Scripts locais rodam; scripts da internet exigem assinatura.

### Reset das políticas de scripts

[Permissões do PowerShell (Administrador)] Set-ExecutionPolicy Restricted

> Nenhum script funciona. Padrão do Windows Client.

---

## Padronização e Qualidade de Código

- Pasta .vscode/settings.json

  > https://github.com/luizomf/chronos-pomodoro/blob/ebd471c37c06895e41a77785949734659f3e5638/.vscode/settings.json

- Arquivo .prettierrc.json (Raiz do projeto)

  > https://github.com/luizomf/chronos-pomodoro/blob/ebd471c37c06895e41a77785949734659f3e5638/.prettierrc.json

---

## Criando projeto Vite

> Abrir o powershell ou cmd como administrador:

Cria o projeto já configurado com TypeScript e SWC:

-npm create vite@latest meu-projeto -- --template react-swc-ts

OU Método Manual (Menu Interativo):

- npm create vite@latest
- apertar (y)
- Definir nome do projeto
- Selecionar React
- Selecionar TypeScript + SWC

## Migração Manual para SWC

> Caso o projeto já tenha sido criado com o plugin padrão do React (Babel), siga
> estes passos para migrar:

- Selecionar apenas TypeScript
- Depois trocar os pacotes (no powershell ou cmd):

**Troca de pacotes**

PowerShell: npm uninstall @vitejs/plugin-react ; npm install -D
@vitejs/plugin-react-swc

CMD: npm uninstall @vitejs/plugin-react && npm install -D
@vitejs/plugin-react-swc

- Verificar se o package.json tem "@vitejs/plugin-react-swc": "^x.x.x"
- Depois atualizar o arquivo de configuração (vite.config.ts): import react from
  '@vitejs/plugin-react-swc' // Adicionamos o -swc aqui

---

## Inicialização Final

> Siga a sequência para rodar o projeto pela primeira vez:

- Entrar na pasta: cd meu-projeto
- Instalar dependências: npm install
- Iniciar servidor local: npm run dev

---

### Dica de Wildcard (Extra)

Para projetos que lidam com muitos dados ou listas (como dicionários ou
inventários), considere instalar o pacote **Zustand** para gerenciamento de
estado. Ele é extremamente leve, funciona muito bem com TypeScript e evita a
complexidade do Redux.

---

## Configuração do GIT

- No terminal execute e clique enter em tudo: ssh-keygen.exe
- Depois copie o local da chave e execute: cat (cole o local da chave)
- Em seguida configurar no git hub (https://github.com/settings/ssh/new)

### Comandos GIT

- git --version (Verifica a instalação)
- git init (Inicializa o repositório local)
- git branch -m main (Define o nome da branch principal como "main")
- git config user.name "Nome de Usuário"
- git config user.email "email@email.com"
- git config core.eol lf
- git config core.autocrlf input
- git add . (Adiciona todos os arquivos ao index)
- git commit -m "mensagem de commit" (Salva o estado atual (checkpoint))

- git reset --hard (Limpa tudo. Ele volta o estado da pasta exatamente para como
  estava no último commit, descartando qualquer código novo)
- git reset --soft (Move o ponteiro de volta, mas mantém o código que você
  escreveu intacto na sua pasta (como se você tivesse acabado de dar um git add
  mas ainda não tivesse commitado))

- git remote add origin link://repositório.no.github.com (Vincula seu PC ao
  servidor (GitHub))
- git push origin main -u (Sobe os arquivos e define o "main" como padrão)

- git config --list --local
- git status (Mostra o estado atual dos arquivos)
