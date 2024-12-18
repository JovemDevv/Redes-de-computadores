
# Conhecendo o Linux

## Lista a seguir alguns exemplos dessa estrutura para Linux.

**/ (Raiz):** O diretório raiz que contém todos os outros arquivos e diretórios do sistema.

**/bin:** Contém arquivos executáveis essenciais para o funcionamento do sistema, como comandos básicos (ls, cp, mv).

**/boot:** Contém os arquivos necessários para inicializar o sistema, como o kernel e o gerenciador de inicialização.

**/dev:** Contém arquivos de dispositivo, representando dispositivos de hardware (discos, terminais, impressoras, etc.).

**/etc:** Contém arquivos de configuração do sistema e de aplicativos.

**/home:** Contém os diretórios pessoais dos usuários (por exemplo, /home/usuario).

**/lib:** Contém bibliotecas compartilhadas essenciais para os programas no diretório /bin e /sbin.

**/media:** Ponto de montagem para mídias removíveis, como CDs, DVDs, ou unidades USB.

**/mnt:** Diretório usado para montar sistemas de arquivos temporários.

**/opt:** Contém aplicativos de software adicionais, geralmente pacotes de software não padrão.

**/proc:** Sistema de arquivos virtual que contém informações sobre processos em execução e o estado do kernel.

**/root:** Diretório pessoal do superusuário (root).

**/run:** Contém informações sobre o sistema em tempo de execução, como arquivos de PID (identificadores de processo) e informações de rede.

**/sbin:** Contém programas essenciais para administração do sistema, geralmente usados pelo root.

**/srv:** Contém dados específicos de serviços oferecidos pelo sistema.

**/sys:** Sistema de arquivos virtual que expõe informações e configurações do kernel.

**/tmp:** Diretório para arquivos temporários que podem ser apagados ao reiniciar o sistema.

**/usr:** Contém aplicativos, bibliotecas e arquivos de documentação para uso dos usuários.

**/var:** Contém arquivos que variam durante a execução do sistema, como logs, caches, filas de impressão, etc.

## Comandos debian

Aqui está uma lista **completa de comandos do Linux**, focando apenas no Debian/Ubuntu, cobrindo uma ampla gama de operações que você pode precisar para administração, gerenciamento de pacotes, redes, arquivos e mais.

### **1. Gerenciamento de Pacotes (apt)**

- **Atualização e upgrade do sistema**:
  - `sudo apt update` – Atualiza a lista de pacotes disponíveis nos repositórios.
  - `sudo apt upgrade` – Atualiza todos os pacotes instalados para suas versões mais recentes.
  - `sudo apt full-upgrade` – Realiza a atualização completa do sistema, incluindo remoções e instalações de novos pacotes.
  - `sudo apt dist-upgrade` – Realiza a atualização do sistema, incluindo a instalação de novos pacotes e remoção dos desnecessários.
  - `sudo apt-get update` – (Alternativo ao `apt update`).
  - `sudo apt-get upgrade` – (Alternativo ao `apt upgrade`).
  
- **Instalar pacotes**:
  - `sudo apt install [pacote]` – Instala um pacote específico.
  - `sudo apt install [pacote1] [pacote2]` – Instala múltiplos pacotes.
  
- **Remover pacotes**:
  - `sudo apt remove [pacote]` – Remove um pacote, mas mantém seus arquivos de configuração.
  - `sudo apt purge [pacote]` – Remove um pacote e seus arquivos de configuração.
  - `sudo apt autoremove` – Remove pacotes não mais necessários.
  - `sudo apt-get remove --purge [pacote]` – (Alternativo ao `apt purge`).
  
- **Procurar pacotes**:
  - `apt search [pacote]` – Pesquisa por pacotes disponíveis nos repositórios.
  - `apt-cache search [pacote]` – (Alternativo ao `apt search`).
  
- **Exibir informações sobre pacotes**:
  - `apt show [pacote]` – Exibe detalhes sobre um pacote.
  - `apt-cache show [pacote]` – (Alternativo ao `apt show`).
  
- **Limpar cache de pacotes**:
  - `sudo apt clean` – Limpa o cache de pacotes local.
  - `sudo apt autoclean` – Remove pacotes do cache que não podem mais ser baixados.
  
- **Atualizar distribuição**:
  - `sudo do-release-upgrade` – Atualiza a versão do Ubuntu ou Debian para a próxima versão estável.

---

### **2. Gerenciamento de Usuários e Grupos**

- **Gerenciar usuários**:
  - `sudo useradd [nome]` – Cria um novo usuário.
  - `sudo useradd -m [nome]` – Cria um novo usuário com diretório home.
  - `sudo passwd [nome]` – Altera a senha de um usuário.
  - `sudo userdel [nome]` – Remove um usuário.
  - `sudo userdel -r [nome]` – Remove um usuário e seu diretório home.
  - `sudo usermod -aG [grupo] [usuário]` – Adiciona um usuário a um grupo.
  - `sudo usermod -l [novo_nome] [nome_atual]` – Renomeia um usuário.
  
- **Gerenciar grupos**:
  - `sudo groupadd [grupo]` – Cria um novo grupo.
  - `sudo groupdel [grupo]` – Remove um grupo.
  - `sudo gpasswd -a [usuário] [grupo]` – Adiciona um usuário a um grupo.
  
- **Verificar usuários e grupos**:
  - `whoami` – Exibe o nome do usuário atual.
  - `id [usuário]` – Exibe o ID do usuário e os grupos aos quais ele pertence.
  - `groups [usuário]` – Exibe os grupos de um usuário.
  - `getent passwd` – Exibe a lista de usuários.
  - `getent group` – Exibe a lista de grupos.
  
---

### **3. Gerenciamento de Arquivos e Diretórios**

- **Manipulação de arquivos**:
  - `cp [origem] [destino]` – Copia arquivos ou diretórios.
  - `cp -r [origem] [destino]` – Copia diretórios recursivamente.
  - `mv [origem] [destino]` – Move ou renomeia arquivos e diretórios.
  - `rm [arquivo]` – Remove um arquivo.
  - `rm -r [diretório]` – Remove um diretório e seu conteúdo.
  - `rm -rf [diretório]` – Remove um diretório forçadamente.
  - `touch [arquivo]` – Cria um arquivo vazio.
  
- **Ver conteúdo de arquivos**:
  - `cat [arquivo]` – Exibe o conteúdo de um arquivo.
  - `more [arquivo]` – Exibe o conteúdo de um arquivo uma página por vez.
  - `less [arquivo]` – Exibe o conteúdo de um arquivo com navegação interativa.
  - `head [arquivo]` – Exibe as primeiras 10 linhas de um arquivo.
  - `tail [arquivo]` – Exibe as últimas 10 linhas de um arquivo.
  - `nl [arquivo]` – Exibe o conteúdo de um arquivo numerado.
  
- **Procurar arquivos**:
  - `find [diretório] -name [nome_do_arquivo]` – Encontra arquivos por nome em um diretório.
  - `locate [nome_do_arquivo]` – Localiza rapidamente arquivos no sistema.
  - `which [comando]` – Exibe o caminho completo do comando executado.
  - `grep [termo] [arquivo]` – Busca por um termo dentro de um arquivo.
  - `grep -r [termo] [diretório]` – Busca recursivamente por um termo dentro de arquivos em um diretório.
  
- **Permissões de arquivos**:
  - `chmod [permissões] [arquivo]` – Modifica as permissões de um arquivo.
  - `chmod 755 [arquivo]` – Dá permissão de leitura, escrita e execução ao proprietário, e leitura e execução para outros.
  - `chown [usuário]:[grupo] [arquivo]` – Modifica o proprietário e grupo de um arquivo.
  - `chgrp [grupo] [arquivo]` – Modifica o grupo de um arquivo.
  
---

### **4. Gerenciamento de Processos**

- **Verificar processos em execução**:
  - `ps aux` – Exibe todos os processos em execução.
  - `top` – Exibe o uso de recursos do sistema em tempo real.
  - `htop` – Alternativa mais interativa ao `top` (precisa ser instalado).
  - `pgrep [processo]` – Exibe o PID de processos correspondentes.
  
- **Manipular processos**:
  - `kill [PID]` – Finaliza um processo pelo PID.
  - `kill -9 [PID]` – Força a finalização de um processo.
  - `pkill [nome_do_processo]` – Finaliza processos pelo nome.
  - `bg` – Coloca um processo em segundo plano.
  - `fg` – Traz um processo para o primeiro plano.
  - `jobs` – Lista os processos em segundo plano.
  
---

### **5. Gerenciamento de Sistema**

- **Verificar uso de disco**:
  - `df -h` – Exibe o uso de disco de forma legível.
  - `du -sh [diretório]` – Exibe o tamanho total de um diretório.
  
- **Verificar memória**:
  - `free -h` – Exibe a quantidade de memória livre e usada de forma legível.
  
- **Verificar tempo de atividade e logins**:
  - `uptime` – Exibe o tempo de atividade do sistema.
  - `who` – Exibe os usuários logados no sistema.
  - `w` – Exibe informações sobre os usuários logados e suas atividades.
  - `last` – Exibe informações sobre os últimos logins no sistema.
  
- **Reiniciar ou desligar o sistema**:
  - `sudo reboot` – Reinicia o sistema.
  - `sudo shutdown -h now` – Desliga o sistema imediatamente.
  - `sudo shutdown -r now` – Reinicia o sistema imediatamente.
  
- **Exibir informações do sistema**:
  - `uname -a` – Exibe informações sobre o sistema operacional e o kernel.
  - `hostname` – Exibe ou configura o nome do host do sistema.
  - `hostnamectl` – Exibe ou configura o nome do host de forma mais detalhada.
  - `lshw` – Exibe informações detalhadas sobre o hardware do sistema.
  - `lsblk` – Exibe informações sobre dispositivos de bloco (discos e partições).
  
---

### **6. Comandos de Rede**

- **Verificar conectividade de rede**:
  - `ping [endereço]` – Verifica a conectividade com um endereço.
  - `traceroute [endereço]` – Exibe o caminho que os pacotes percorrem até o destino.
  - `curl [URL]` – Realiza uma requisição HTTP para uma URL.
  - `wget [URL]` – Baixa um arquivo de uma URL.
  
- **Exibir informações sobre rede**:
  - `ifconfig` – Exibe informações sobre as interfaces de rede (em sistemas mais antigos).
  - `ip a` – Exibe informações sobre as interfaces de rede (mais moderno).
  - `ip link` – Exibe informações sobre as interfaces de rede.
  - `netstat` – Exibe informações sobre as conexões de rede.
  - `ss` – Substituto do `netstat` para exibir informações de rede.
  - `sudo ufw status` – Exibe o status do firewall UFW.
  - `sudo ufw enable` – Ativa o firewall UFW.
  - `sudo ufw allow [porta]` – Permite o tráfego de uma porta específica.
  
- **Conectar via SSH**:
  - `ssh [usuário]@[endereço]` – Conecta-se a um servidor remoto via SSH.
  - `scp [arquivo] [usuário]@[endereço]:[destino]` – Copia um arquivo para o servidor remoto via SCP.
  
---

### **7. Compressão e Arquivos Compactados**

- **Compactar arquivos**:
  - `tar -czvf [arquivo.tar.gz] [diretório]` – Compacta um diretório em um arquivo `.tar.gz`.
  - `gzip [arquivo]` – Compacta um arquivo para `.gz`.
  - `zip [arquivo.zip] [arquivo1] [arquivo2]` – Compacta arquivos em um arquivo `.zip`.
  
- **Descompactar arquivos**

:
  - `tar -xzvf [arquivo.tar.gz]` – Descompacta um arquivo `.tar.gz`.
  - `gunzip [arquivo.gz]` – Descompacta um arquivo `.gz`.
  - `unzip [arquivo.zip]` – Descompacta um arquivo `.zip`.

---

### **8. Comandos de Backup e Recuperação**

- **Criar backups**:
  - `rsync -av [origem] [destino]` – Realiza backup de arquivos e diretórios.
  - `cp -r [diretório_origem] [diretório_destino]` – Copia diretórios para backup.
  
- **Restaurar backups**:
  - `rsync -av [destino] [origem]` – Restaura arquivos a partir de um backup.



