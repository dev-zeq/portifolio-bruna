# 🚀 Guia Rápido: Comandos Git (Bez Clean & Bruna)

## 1. Configuração Inicial (Uma vez por computador)
git config --global user.name "zeqmiranda21"
git config --global user.email "zeqmiranda@gmail.com"
git config --global init.defaultBranch main

## 2. Iniciar um novo projeto (Na pasta do projeto)
git init
git remote add origin git@github.com:dev-zeq/NOME_DO_REPO.git
git branch -M main

## 3. Fluxo Diário (Sempre que alterar algo)
1. git status          (Confere o que mudou)
2. git add .           (Prepara os arquivos)
3. git commit -m "..." (Salva com descrição curta)
4. git push            (Envia para o GitHub)

## 4. Atualizar o que está na nuvem
git pull origin main

## 5. Quando tudo der errado (O "Pânico")
# ATENÇÃO: Isso apaga alterações locais não salvas!
git fetch origin
git reset --hard origin/main
git clean -fd

## 6. Branches
git branch -a          (Ver todas as ramificações)

📋 Guia de Sobrevivência Git (Dev-Zeq)
1. Sincronizando seu computador com o novo perfil
Se você trocou o nome de usuário no GitHub, atualize o endereço do repositório:

Bash
git remote set-url origin git@github.com:dev-zeq/NOME-DO-REPOSITORIO.git

2. Fluxo Padrão (O dia a dia)
Sempre que fizer uma alteração em um arquivo (como o teste.md):

Bash
# Adiciona o arquivo para ser monitorado
git add .

# Registra a mudança
git commit -m 'descrição curta e clara'

# Envia para a nuvem
git push origin main

3. Resolvendo erros de "Rejected" (Conflitos de Histórico)
Se o GitHub recusar o push porque tem arquivos lá que você não tem aqui, use esta sequência de segurança:

Bash
# 1. Traz as novidades do servidor e tenta alinhar
git pull origin main --rebase

# 2. Se tudo estiver certo, envia suas mudanças
git push -u origin main

4. O "Botão de Pânico" (Forçar o envio)
Use com cautela! Se você tem certeza de que o que está no seu computador é o que deve ficar no GitHub (e quer sobrescrever qualquer coisa que esteja lá):

Bash
git push -u origin main --force

5. Consultas Rápidas
Ver histórico: git log --oneline

Ver o que mudou: git status

Ver o link atual do servidor: git remote -v