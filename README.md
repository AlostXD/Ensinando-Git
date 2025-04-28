# Ensinando-Git

Guia prático para aprender os comandos básicos do Git, com foco em produção.

---

## 1. Inicializando um Repositório

### `git init`

- Transforma um diretório em um repositório Git.
- Deve ser executado apenas uma vez no diretório do projeto.
- Cria um repositório vazio e exibe uma mensagem de confirmação.

**Nota:** Se o diretório já for um repositório Git, o comando apenas o reconhece novamente, mantendo o histórico de mudanças intacto.

---

## 2. Adicionando Arquivos ao Controle de Versão

### `git add`

- Adiciona arquivos modificados ao índice para serem preparados para o commit.
- Sintaxe:
    ```bash
    git add .
    ```
    ou
    ```bash
    git add <nome-do-arquivo>
    ```

---

## 3. Registrando Alterações

### `git commit`

- Registra as alterações locais feitas no projeto.
- Sintaxe:
    ```bash
    git commit -m "mensagem do commit"
    ```
    - O `-m` permite adicionar uma mensagem diretamente na linha de comando.

#### Configuração Inicial (se necessário):

Configure o nome e o e-mail globais antes do primeiro commit:

```bash
git config --global user.email "seuEmailDoGithub@email.com"
git config --global user.name "SeuNomeDoGithub"
```

---

## 4. Conectando ao Repositório Remoto

### `git remote add`

- Estabelece a conexão entre o repositório local e o remoto.
- Sintaxe:
    ```bash
    git remote add origin <URL>
    ```

#### Comandos úteis:

- **Listar repositórios remotos:**
    ```bash
    git remote -v
    ```
- **Alterar a URL do repositório remoto:**
    ```bash
    git remote set-url origin <nova_url>
    ```
- **Remover um repositório remoto:**
    ```bash
    git remote remove origin
    ```

---

## 5. Enviando Alterações

### `git push`

- Envia as alterações para o repositório remoto.
- Sintaxe:
    ```bash
    git push -u origin main
    ```
    - O `-u` associa a branch local com a branch remota, facilitando futuros comandos `git push` e `git pull`.

---

## 6. Atualizando o Repositório Local

### `git pull`

- Atualiza o repositório local com as alterações do repositório remoto.
- Sintaxe:
    ```bash
    git pull origin main
    ```
    - Certifique-se de estar na branch correta antes de executar o comando.

---

## 7. Clonando Repositórios

### `git clone`

- Cria uma cópia local de um repositório remoto.
- Sintaxe:
    ```bash
    git clone <URL>
    ```

#### Exemplos:

- Clonar com HTTPS:
    ```bash
    git clone https://github.com/seu-usuario/seu-repositorio.git
    ```
- Clonar com SSH:
    ```bash
    git clone git@github.com:seu-usuario/seu-repositorio.git
    ```
- Clonar em um diretório específico:
    ```bash
    git clone <URL> <nome-do-diretorio>
    ```

---

## 8. Trabalhando com Branches

### `git branch -M`

- Renomeia a branch principal para `main`.
- Sintaxe:
    ```bash
    git branch -M main
    ```

---

## 9. Visualizando o Histórico de Commits

### `git log`

- Exibe o histórico de commits do repositório.
- Sintaxe:
    ```bash
    git log
    ```
    - Use `git log --oneline` para uma visualização mais compacta.

---

## 10. Configurando Chave SSH

A chave SSH permite autenticar sua máquina com o GitHub sem inserir credenciais repetidamente.

### Gerando uma Chave SSH

1. Execute o comando:
     ```bash
     ssh-keygen -t ed25519 -C "seuEmailDoGithub@email.com"
     ```
     - Caso sua máquina não suporte `ed25519`, use:
         ```bash
         ssh-keygen -t rsa -b 4096 -C "seuEmailDoGithub@email.com"
         ```

2. Escolha o local para salvar a chave (pressione `Enter` para o padrão).
3. Defina uma senha (opcional).

A chave será salva no diretório padrão, geralmente em `~/.ssh/`.

### Adicionando a Chave ao Agente SSH

1. Inicie o agente SSH:
     ```bash
     eval "$(ssh-agent -s)"
     ```
2. Adicione a chave ao agente:
     ```bash
     ssh-add ~/.ssh/id_ed25519
     ```

### Registrando a Chave no GitHub

1. Copie a chave pública:
     ```bash
     cat ~/.ssh/id_ed25519.pub
     ```
2. Acesse [Configurações de SSH no GitHub](https://github.com/settings/keys).
3. Clique em **New SSH Key**, cole a chave e salve.

---

Este guia cobre os comandos essenciais para começar a usar o Git em produção. Explore e pratique para dominar o controle de versão!
