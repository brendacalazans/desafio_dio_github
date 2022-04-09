# Minhas Anotações

- O que é o Git?
    
    É um sistema de controle de versão open source mais usado no mundo atualmente! Ele é usado para controlar o histórico de alterações de arquivos e principalmente de projetos de desenvolvimento de software.
    
- Qual a diferença entre CLI (*Command Line Interface)* e GUI (*Graphic User Interface*)?
    
    A interface gráfica do usuário permite que o usuário interaja com o sistema usando gráficos que incluem imagens, ícones etc.
    
    Já a interface de linha de comando permite que um usuário se comunique com o sistema por meio de comandos.
    
- O git é que tipo de programa?
    
    Ele é um programa de Command Line Interface.
    
- O que é um SHA1?
    
    A sigla SHA significa Secure Hash Algorith (algoritmo de hash seguro), é um conjunto de funções hash criptográficas projetadas pelas NSA (agência de segurança nacional dos EUA). Basicamente, ela gera dados encriptados de 40 dígitos de caracteres.
    
- Quais são os objetos fundamentais do git?
    
    - BLOBS
    
    - TREES
    
    - COMMITS
    
- O que são os blobs?
    
    Contém metadados como o tipo, o tamanho do arquivo, uma \0 e o conteúdo de um arquivo.
    
    Cada arquivo no **Git** é armazenado como um objeto **blob**, por exemplo, a partir do conteúdo do arquivo logo. png ele gera um hash que será armazenado em algum lugar endereçável.
    
- O que são as tree?
    
    Aponta para tipos de blob, que tem o sha1, o nome do arquivo, além de ter um sha1 da própria árvore. 
    
    É responsável por montar a estrutura dos arquivos, blobs ou outras árvores.
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d5e876c4a93e-48b1-9b6c-3fbdbb34741b/Untitled.png)
    
- O que são os commit?
    
    Aponta para uma árvore, um parente (último commit realizado antes dele), para o autor e para uma mensagem, além de ter a data e o horário que foi criado.
    
    Tem um sha1
    
    mensagem → o que quer dizer aqueles arquivos ou pastas.
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/75ada12c-08b9-44c0-ae0f-3e78901f5597/Untitled.png)
    
- Se você alterar um arquivo vai mudar o que?
    
    o sha1 do blob, que mudará o sha1 da tree, e que por sua vez irá alterar o sha1 do commit.
    
- Por que o git é um sistema distribuído e seguro?
    
    Todas as versões irão ficar gravadas no commit e as versões conectadas no sevidor serão seguras.
    
- O que é a chave SSH?
    
    É uma conexão entre duas máquinas encriptografada mais segura que não requer senha.
    
- Passos para autenticar a chave ssh
    1. Abrir GitBash
        
        ssh-keygen -t ed25519 -c email // comando para gerar chave
        
        1. Colocar o caminho
        2. Colocar a senha
        
        = Contéudo da chave salva na pasta
        
        cd /c/Users/usuário/ .ssh/   // comando para ir até a pasta
        
        ls    //comando para listar chaves pública e privada
        
        cat id_ed25519.pub   //comando para liberar o conteúdo da autenticação da chave pública 
        
        = Chave pública
        
    2. Adicionar chave no github
        1. Dar nome
        2. Colocar o = Chave pública
    3. Lidar com chaves
        
        eval $(ssh-agent -s)
        
        = Startar o projeto
        
        1. Entregar a nossa chave
        
        ssh-add id_ed25519    //comando para fazer com que a chave privada descriptografe as informações que chegam
        
         1. Colocar senha
        
        = Identidade adicionada
        
- Como clonar repositórios com a chave ssh?
    1. Entrar no repositório
    2. Clicar em Code > SSH
    3. Escrever no Git Bash
        
        git clone link
        
    4. Confirmar a conexão
- O que é token de acesso pessoal?
    
    É o acesso por usuário senha e token.
    
- Como gerar um token?
    1. Ir em settings no github > Developer settings > Personal acess tokens
    2. Colocar as informações do token
    3. Copiar o token e colocar em um arquivo seguro.
- Como clonar o repositório pelo token?
    1. Colocar o comando
        
        git clone https://github.com/....
        
    2. Logar com a conta do github
    3. Colocar o token
    
    = Autenticação concluída.
    
- Comandos básicos do git
    
    - git unit → inicia o repositório do git.
    
    - git config — global user. email “brendacalaza..” → configura o e-mail no git
    
    - git config —global [user.name](http://user.name) Brenda→ configura o nome no git add * → realiza a inclusão ou modificação do arquivo no diretório local.
    
    - git commit -m “commit inicial”→ criar um commit com o estado de um projeto  naquele momento.
    
    - git status → mostra os status dos arquivos.
    
    - echo > nomeArquivo → cria um arquivo
    
- Como exibir arquivos ocultos?
    
    ls -a
    
    a flag -a exibe arquivos ocultos
    
- O que significa arquivos tracked e untracked?
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/96b60918-ba60-49a4-a6fb-651c12a03b50/Untitled.png)
    
- Onde o git fica?
    
    No ambiente de desenvolvimento tem a área de trabalho, área de staged e o repositório local. Já no servidor, ele fiica no repositório remoto.
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c2aab6d0-9db8-4569-bbf5-77d8b039b505/Untitled.png)
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fe8ffd1f-c389-444d-90a8-38fda641c63b/Untitled.png)
    
    - git add move os arquivos do diretório de trabalho para área de staged
    
    - git commit move os arquivos da área de staged para o repositório local.
    
- Diferenças de git add
    
    - git add nomeArquivo → adiciona apenas o arquivo
    
    - git add * → adiciona arquivos novo e modificados do diretório atual
    
    - git add . → adiciona arquivos novos e modificados mas não os deletados
    
- Como verificar e alterar as configurações do git?
    
    - git config —list → mostra todas as configurações
    
    - git config —global —unset (configuração) → tira a configuração antiga
    
- Como colocar o diretório no github?
    
    - git remote add origin [https://github.com/brendacalazans/livro-receitas.git](https://github.com/brendacalazans/livro-receitas.git) → adiciona o diretório
    
    - git remote -v → mostra todos os diretórios que estão no github
    
    - git push origin master → manda todos os commits para o github.
    
- Como resolver um conflito de merge?
    
    1. utilizar o git pull origin master
    
    2. corrigir alterações
    
    3. utilizar o git push origin master para upar no site
    
- Como clonar um diretório?
    
    - git clone link
    
    - ls -a
    
    - git remote -v