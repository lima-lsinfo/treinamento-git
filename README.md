# Comandos comuns do Git

| O que faz                  | Comando                                              |
|----------------------------|------------------------------------------------------|
| configurar usuário padrão | `git config --global user.name "user.name"` |
| configurar e-mail padrão | `git config --global user.email "user.name@email.com"` |
| alterar o editor padrão | `git config --global core.editor vim` |
| configurar editor padrão "Visual Studio Code" | `git config --global core.editor "code --wait"` |
| listar todas as configurações | `git config --list` |
| iniciar um repositório em um diretório (navegar até o diretório) | `git init` |
| status do repositório | `git status` |
| adicionar um arquivo a staged area | `git add nomedoarquivo` |
| criar um commit (gerar um snapshot) -m (para inserir comentario) | `git commit -m "Mensagem"` |
| adiciona todos arquivos commited e insere a mensagem | `git commit -am "Mensagem"` |
| envia arquivos faltantes | `git commit --amend` |
| lista log | `git log` |
| lista de log mais completa | `git log --decorate` |
| filtrar log por autor | `git log --autor="nomeautor"` |
| lista log em ordem alfabética (autor, quantidade de commmit) | `git shortlog` |
| log da quantidade de commits e quem efetuou | `git shortlog -sn` |
| log de forma gráfica o que esta acontecendo com os Branchs | `git log --graph` |
| buscar através da hash do commit | `git show colarhash` |
| lista as modificações antes de um commit | `git diff` |
| lista o nome dos arquivos onde foram feitas as modificações antes de um commit | `git diff --name-only` |
| desfazendo alterações (voltando a um estado anterior) sem estar em staged | `git checkout nomedoarquivo` |
| desfazendo alterações (arquivo em staged) | `git reset HEAD nomedoarquivo` |
| elimina o commit mas mantém o arquivo em staged pronto para  o commit | `git reset --soft informarhash` |
| elimina o commit e retorna os arquivos antes de entrar em staged | `git reset --mixed informarhash` |
| elimina todo o commit e as alterações feitas | `git reset -- hard informarhash` |
| copiar o endereço ssh ou https no github | `git clone colarendereço inserirnomedoclone` |
| criando um Branch | `git checkout -b nomedobranch` |
| selecionando branches | `git checkout nomedobranch` |
| deletando branches | `git branch -d nomedobranch` |
| git ignore | `git add .gitignore` |
| marcar uma modificação para "work in progress" | `git stash` |
| lista as modificações em "work in progress" | `git stash list` |
| limpa as modificações em "work in progress" | `git stash clear` |
| para remover do status de "work in progress" | `git stash apply` |
| criar alias para comandos | `git config --global alias.s status` |
| adicionar tags no versionamento (-a anotação, -m mensagem, 1.0.0=TAG) | `git tag -a 1.0.0 -m "Versão nova"` |
| subir as tags | `git push origin master --tags` |
| verificar as tags existentes | `git tag` |
| reverter um commit que deu algum problema | `git revert inserirnumerodocommit` |
| apagar as tags e branches de repositórios remotos | `git tag -d informartag` e `git push origin :tag ou branch`|
| rebase | `git rebase -i master` |
| reescreve a msg do commit| `git squash` |
| ignora a msg do commit | `git fixup` |
| gerando nova chave SSH | `ssh-keygen -t rsa -b 4096 -C "youremail@domain.com"` |

Apaga branches locais e baixa as branches remotas
`git branch -r | egrep -v -f /dev/fd/0  <(git branch -vv | grep origin) | xargs git branch -d` |

Git pull de todos diretórios:
`ls | xargs -I{} git -C {} pull`

---

# Git ignore

Criar arquivo e inserir as extensões ou arquivos que serão ignorados:

    Arquivos Específicos → arquivo1.txt
    Curingas → *.txt
    Diretórios → /files/keys/
    Expressões Regulares (Regex) → arquivo{1..5}.txt

---

# Criando novo repositório

    echo "# limacodes" >> README.md
    git init
    git add README.md
    git commit -m "first commit"

Adiciona o repositório do Github

    git remote add origin <repo_name>

Envia os arquivos do repositório local para o repositório remoto

    git push -u origin master
---
