# Função
O protocolo **SMB** permite o compartilhamento de arquivos, impressoras, portas seriais e outras operações de comunicação entre computadores em um rede local. ele opera no modo cliente-servidor, facilitando a interações entre diferentes dispositivos e sistemas operacionais dentro de uma rede.
# Serviço SAMBA
## Função
O SAMBA é uma implementação de open-source do protocolo SMB. Ele permite a integração e a comunicação entre sistemas operacionais diferentes, como Linux e Windows, utilizando os "server daemons" SMBD e NMBD para gerenciar a comunicação e os serviços.
## Características
- **Integração Linux/Windows:** Permite que sistemas Linux e Windows compartilhem recursos como arquivos e impressoras.
- **Perfis Móveis:** Pode ser configurado para suportar perfis móveis, permitindo que os usuários acessem suas configurações e arquivos de qualquer computador na rede.
- **Serviço de Arquivos e Impressão:** Pode atuar como um servidor de arquivos, impressão e até como controlador de domínio.
- **Configuração Centralizada:** Todas as configurações são centralizadas no arquivo smb.conf
## Componentes
- **smbd:** Servidor SAMBA principal que gerencia os compartilhamentos de arquivos e impressoras.
- **nmbd:** Servidor de nomes NetBIOS que gerencia a resolução de nomes NetBIOS para endereços IP.
- **smbclient:** Cliente SMB para sistemas UNIX, permitindo acesso a recursos SMB de outros servidores.
- **smbpassword:** Utilizado para alterar senhas de usuários no SAMBA.
- **smbprint:** Cliente para envio de trabalhos de impressão para sistemas UNIX.
- **smbstatus:** Exibe o status atual das conexões SMB no host.
## Comandos SAMBA
- Adicionar usuários ao banco de dados do SAMBA: `adduser -a "usuario"`
- Inserir um usuário no grupo: `gpasswd -a usuario users`
- Excluir usuário do grupo: `gpasswd -d usuario users`
- Criar senha para o usuário: `smbpasswd -a usuario`
## Portas de conexão
- **Porta 139/TCP, UDP:** NetBIOS Session Service, utilizada para sessões NetBIOS.
- **Porta 445/UDP:** Microsoft-DS SMB, utilizada para o protocolo SMB direto.
