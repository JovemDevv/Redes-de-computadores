# **Redes de Computadores**  
## **Modelo TCP/IP**

O **modelo TCP/IP** é fundamental para o funcionamento da Internet, gerenciando as transferências de dados entre dispositivos conectados à rede. Esse modelo é uma pilha de protocolos, composta por quatro camadas principais: **camada de aplicação**, **camada de transporte**, **camada de rede** e **camada de interface**.

### **Camadas do Modelo TCP/IP**

O modelo TCP/IP pode ser descrito em quatro camadas, cada uma com funções específicas:

1. **Camada de Interface (ou de Link de Dados)**: Responsável por como os dados são fisicamente transmitidos entre os dispositivos. Ela lida com a comunicação direta, seja via cabos (Ethernet) ou wireless (Wi-Fi), e garante que os dados sejam transmitidos corretamente entre os hosts.

2. **Camada de Rede (ou Camada de Internet)**: A camada de rede lida com o roteamento dos pacotes de dados pela rede. Ela determina o melhor caminho para os pacotes chegarem ao destino final. O **Protocolo de Internet (IP)** é o principal protocolo dessa camada, que lida com os endereços e a entrega de pacotes.

3. **Camada de Transporte**: A camada de transporte é responsável por garantir a entrega confiável e ordenada dos pacotes. É nesta camada que o **TCP (Protocolo de Controle de Transmissão)** divide os dados em pacotes e os envia com números de sequência. O **UDP (User Datagram Protocol)** também opera nesta camada, mas é menos confiável e mais rápido que o TCP.

4. **Camada de Aplicação**: A camada de aplicação é onde os dados são utilizados pelos aplicativos finais. Exemplos de protocolos dessa camada incluem **HTTP** (para navegação na web), **FTP** (para transferência de arquivos) e **SMTP** (para envio de e-mails).

### **Protocolo IP**

O **Protocolo de Internet (IP)** é responsável pelo endereçamento na Internet. Ele atribui um identificador único, o **endereço IP**, a cada dispositivo conectado à rede, permitindo que os dados sejam enviados de um ponto a outro. O IP é essencial para conectar redes e formar a base da internet. No entanto, o IP por si só não garante que os pacotes de dados cheguem corretamente e na ordem certa; para isso, é necessário outro protocolo, como o **TCP**, que garante a entrega confiável dos dados.

### **Protocolo TCP**

O **TCP** é um protocolo orientado à conexão, projetado para garantir a entrega correta e sem erros de dados entre os dispositivos. Ele lida com a divisão dos dados em pacotes e assegura que esses pacotes cheguem ao destino, na ordem correta e sem perdas. Caso algum pacote se perca durante a transmissão, o TCP solicita sua retransmissão.

#### **Estabelecimento de Conexão - Handshake de 3 vias**

O **handshake de 3 vias** é o processo usado pelo TCP para estabelecer uma conexão confiável entre o dispositivo de origem e o de destino:

1. **Passo 1**: O dispositivo de origem envia um pacote **SYN** (synchronize) ao servidor, indicando que deseja estabelecer uma conexão.
2. **Passo 2**: O servidor de destino responde com um pacote **SYN-ACK** (synchronize-acknowledge), confirmando a recepção do pedido e indicando que está pronto para estabelecer a comunicação.
3. **Passo 3**: O dispositivo de origem envia um pacote **ACK** (acknowledge) para confirmar a recepção do **SYN-ACK** e finalizar o processo de estabelecimento da conexão.

Após essa troca, a conexão é estabelecida e os dados podem ser transmitidos de forma confiável.

#### **Envio e Remontagem de Dados**

Os dados são divididos em **pacotes menores** e enviados através da rede. Durante a transmissão, esses pacotes podem passar por múltiplos **roteadores** ou **gateways** até chegar ao destino. O TCP garante que os pacotes cheguem na ordem correta, utilizando números de sequência para cada pacote. Caso algum pacote se perca ou chegue fora de ordem, o TCP solicita que ele seja retransmitido.

Quando os pacotes chegam ao destino, o TCP os **remonta** na ordem correta, reconstruindo a mensagem original, seja ela um e-mail, uma página da web ou outro tipo de dado.

### **Funções dos Protocolos TCP e IP**

- **IP (Protocolo de Internet)**: O IP é responsável por transformar pacotes de dados em **datagramas** que contêm os endereços IP de origem e destino. Ele realiza o roteamento dos pacotes, encaminhando-os pela rede até o destino final.
- **TCP (Protocolo de Controle de Transmissão)**: O TCP divide os dados em pacotes, garante que eles cheguem corretamente e na ordem correta e reenvia pacotes perdidos.

### **Processo de Comunicação no TCP/IP**

1. **SYN (Synchronize)**: Sinaliza o início de uma comunicação TCP. O dispositivo de origem envia um pacote SYN para indicar que quer estabelecer uma conexão.
2. **ACK (Acknowledge)**: Serve para confirmar que um pacote foi recebido corretamente. Após o dispositivo de origem enviar um SYN, o servidor confirma com um SYN-ACK.
3. **SYN-ACK (Synchronize-Acknowledge)**: Pacote combinado enviado pelo servidor para confirmar a solicitação de conexão e sinalizar que está pronto para a comunicação.
4. **Pacote de Dados (Data Packet)**: Após o handshake, os pacotes de dados reais são transmitidos. Cada pacote contém uma parte da informação que está sendo enviada.
5. **Roteadores/Gateways**: São dispositivos intermediários responsáveis por encaminhar os pacotes pela rede até o destino.
6. **Remontagem de Pacotes**: Quando os pacotes chegam ao destino, o TCP usa os números de sequência para remontá-los na ordem correta e garantir a entrega da mensagem original.

### **Portas TCP**

As portas TCP são números utilizados para identificar processos específicos em um dispositivo de rede. Cada serviço de rede opera em uma porta específica. Por exemplo:
- **Porta 20**: Transferência de dados via FTP
- **Porta 21**: Controle de comando FTP
- **Porta 22**: SSH (Secure Shell)
- **Porta 25**: SMTP (envio de e-mails)
- **Porta 53**: DNS (resolução de nomes de domínio)
- **Porta 80**: HTTP (navegação web)
- **Porta 443**: HTTPS (HTTP seguro)

As portas ajudam a identificar o serviço ou aplicativo que está utilizando a rede para comunicação.

### **Diferença entre IP e Endereço IP**

O **IP** (Protocolo de Internet) refere-se às regras e padrões que permitem a comunicação entre dispositivos através de uma rede. O **endereço IP**, por sua vez, é um identificador único atribuído a cada dispositivo em uma rede, permitindo que ele seja encontrado e se comunique com outros dispositivos.

---

Além dos protocolos TCP e IP, o modelo TCP/IP envolve outros protocolos importantes:

### **Protocolos de Aplicação Comuns**

1. **HTTP (Hypertext Transfer Protocol)**: Utilizado para transferir **páginas web** e outros recursos da internet, operando na **camada de aplicação**.
2. **HTTPS (Hypertext Transfer Protocol Secure)**: Versão segura do **HTTP**, criptografando a comunicação entre o navegador e o servidor para garantir a segurança.
3. **FTP (File Transfer Protocol)**: Usado para **transferir arquivos** entre dispositivos em uma rede.
4. **SMTP (Simple Mail Transfer Protocol)**: Usado para o envio de **e-mails**.
5. **TLS/SSL (Transport Layer Security / Secure Sockets Layer)**: Protocolos de segurança usados para criptografar a comunicação entre dois dispositivos.
6. **ICMP (Internet Control Message Protocol)**: Usado para enviar mensagens de **controle** e **erro** dentro da rede, como no diagnóstico com o comando **ping**.
7. **UDP (User Datagram Protocol)**: Protocolo mais rápido e menos confiável que o TCP, ideal para aplicações em tempo real como **streaming de vídeo** e **chamadas VoIP**.

### **Resumo dos Protocolos e suas Funções:**
- **TCP**: Garantia de entrega confiável e ordenada dos pacotes de dados.
- **IP**: Endereçamento e roteamento de pacotes.
- **HTTP/HTTPS**: Transferência de páginas web e comunicação segura.
- **FTP**: Transferência de arquivos.
- **SMTP**: Envio de e-mails.
- **TLS/SSL**: Criptografia e segurança de dados.
- **ICMP**: Diagnóstico de rede e mensagens de controle.
- **UDP**: Transferência de dados sem garantia de entrega, ideal para streaming em tempo real.

Assim, o modelo TCP/IP envolve uma série de protocolos que garantem a entrega de dados, segurança e comunicação de diferentes tipos de serviços na rede. Cada um desses protocolos tem um papel crucial no processo de envio e recebimento de dados pela Internet, oferecendo funcionalidades específicas dependendo da aplicação.


## FTP

O **FTP (File Transfer Protocol)**, em português "Protocolo de Transferência de Arquivos", é um protocolo de rede amplamente utilizado para a transferência de arquivos entre computadores através de uma rede TCP/IP, como a Internet. Surgido em 1971, é um dos meios mais antigos de transferir dados entre computadores. Sua principal função é permitir que desenvolvedores de sites e usuários realizem upload e download de arquivos de maneira conveniente e segura, especialmente quando há a necessidade de transferir grandes volumes de dados. O FTP utiliza o modelo cliente/servidor, onde o cliente solicita o acesso aos dados e o servidor os armazena.

### Como Funciona o FTP?

O **FTP** funciona estabelecendo duas conexões para comunicação entre os computadores. A primeira é chamada de **canal de comando**, responsável pelo envio de instruções e respostas entre o cliente e o servidor. A segunda é o **canal de dados**, usado para a transferência de arquivos. Para acessar o servidor FTP, os usuários precisam fornecer credenciais de autenticação, embora alguns servidores públicos permitam acesso sem a necessidade dessas credenciais, em um modo chamado de **FTP anônimo**.

Existem dois modos principais de conexão no FTP: o **modo ativo** e o **modo passivo**. No modo ativo, o cliente solicita a criação de uma conexão e o servidor a estabelece, o que pode ser bloqueado por firewalls. No modo passivo, o cliente estabelece tanto o canal de comando quanto o de dados, com o servidor apenas ouvindo as conexões. O modo passivo é mais utilizado quando há bloqueios de firewall que impedem a conexão ativa.

### Tipos de FTP

Existem três variações principais do FTP:

- **FTP Simples**: É o FTP tradicional, sem criptografia, e utiliza a porta 21.
- **FTPS**: FTP seguro, que utiliza criptografia SSL/TLS para proteger a transferência de dados.
- **FTPES**: Similar ao FTPS, mas com a criptografia sendo explicitamente ativada no momento da comunicação.

### Vantagens do FTP

O FTP permite a transferência simultânea de múltiplos arquivos, o que facilita e acelera o processo, especialmente quando há grandes quantidades de dados a serem transferidos. Além disso, ele é muito útil para empresas e indivíduos que precisam enviar grandes arquivos, como centenas de gigabytes, de forma eficiente.

### Desafios de Segurança do FTP

Um dos principais desafios do FTP é sua **falta de segurança**. O FTP tradicional não criptografa os dados durante a transferência, o que o torna vulnerável a ataques, como **sniffing** (interceptação de dados), **força bruta** e **falsificação**. Como o FTP transmite senhas em texto simples, sem criptografia, elas podem ser facilmente descobertas por criminosos. Embora o **FTPS** e o **FTPES** ofereçam segurança adicional com criptografia, o FTP ainda é considerado vulnerável e inadequado para transferir dados sensíveis sem proteção adicional.

### FTP vs. SFTP

O **SFTP** (Protocolo de Transferência de Arquivos Secure Shell) oferece uma camada de segurança adicional, utilizando criptografia para proteger a transferência de dados. Além disso, o SFTP usa apenas um único canal para a transferência de dados, ao contrário do FTP, que usa dois canais. O SFTP é mais seguro, pois as transferências são feitas de forma criptografada, enquanto o FTP tradicional transmite dados sem criptografia.

### FTP vs. HTTP

Embora o FTP e o **HTTP** (Protocolo de Transferência de Hipertexto) sejam protocolos de camada de aplicação usados para transferência de dados, o HTTP é mais eficiente em muitos casos devido à sua capacidade de suportar múltiplas sessões simultâneas e não exigir autenticação de cliente. O FTP, por outro lado, exige autenticação e é mais limitado no número de sessões que pode suportar.

### FTP vs. MFT

A **Transferência de Arquivos Gerenciada** (MFT) surgiu como uma alternativa ao FTP, trazendo maior segurança e conformidade com regulamentos. O FTP, apesar de ser eficaz, não foi projetado para lidar com as ameaças cibernéticas modernas, tornando-o vulnerável a ataques. O MFT, por sua vez, oferece funcionalidades de gerenciamento de transferências, criptografia de ponta a ponta e recursos de segurança adicionais, sendo recomendado para ambientes corporativos que lidam com dados sensíveis.

### Como Usar o FTP

O FTP pode ser utilizado de diferentes maneiras:

1. **Por meio de um navegador web**: Não é necessário instalar software adicional para acessar servidores FTP em navegadores modernos.
2. **Cliente FTP com interface gráfica**: Aplicações de terceiros com interface gráfica tornam a experiência de uso mais amigável.
3. **Linha de comando FTP**: Todos os principais sistemas operacionais oferecem clientes FTP de linha de comando para usuários avançados.

### Como Alterar Portas do FTP

Por padrão, o FTP utiliza a porta 21. No entanto, é possível configurar outras portas, seja diretamente nas configurações do servidor ou ao modificar o endereço de acesso no formato `ftp://meudominio.com:porta/`.

### Conclusão

O **FTP** é uma ferramenta fundamental para transferência de arquivos, especialmente quando se trata de grandes volumes de dados. No entanto, devido à sua falta de segurança, alternativas como **SFTP** e **MFT** oferecem soluções mais seguras para ambientes corporativos e para a transferência de dados sensíveis. Ao ser usado corretamente e com as devidas precauções de segurança, o FTP continua sendo uma opção eficaz para muitas operações de rede.
