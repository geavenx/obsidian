# O que é
Domain Name System é um sistema que traduz nomes de domínio legíveis por humanos (como www.google.com) em endereços IP que os computadores utilizam para identificar e localizar os dispositivos na rede.
# Funcionamento
O DNS funciona de maneira **hierárquica e distribuída**. Quando um usuário digita um nome de domínio no navegador, o seguinte processo ocorre:
1. **Consulta ao cache local**: Primeiro, o sistema operacional verifica se o endereço já está no cache local.
2. **Consulta no Resolver:** Se o endereço não estiver no cache local, o DNS Resolver do provedor é consultado.
3. **Consulta recursiva:** Se o Resolver não obtiver a resposta, ele faz consultas recursivas a outros servidores DNS, começando pelos servidores raiz.
4. **Servidores raiz:** Existem 13 clusters de servidores raiz no mundo (de a.root-servers.net a m.root-servers.net) que direcionam a consulta para o servidor DNS de nível superior relevante.
5. **Servidores Autoritativos:** Finalmente, a consulta é encaminhada aos servidores autoritativos do domínio, que fornecem o endereço IP correspondente.
# Importância do DNS
Se o DNS parar de funcionar, a internet praticamente pararia. Sem a capacidade de traduzir nomes de domínio em endereços IP, os usuários não conseguiriam acessar os sites e serviços, pois a comunicação na rede seria interrompida.
# Tipos de registros DNS
Os registros DNS são entradas em um banco de dados do DNS que descrevem os tipos e as características de uma zona/domínio. Existem mais de 30 tipos de registros, mas os principais são:
1. **SOA (Start Of Authority):** Contém informações sobre o domínio e o responsável por ele, além de parâmetros como número de série, tempo de atualização e expiração.
2. **A (Address):** Mapeia um nome de domínio para um endereço IPv4.
3. **AAAA (IPv6 Address):** Mapeia um nome de domínio para um endereço IPv6.
4. **NS (Name Server):** Especifica os servidores de nomes autorizados a responder por consultas DNS para um domínio.
5. **CNAME (Canonical Name):** Define um alias para outro nome de domínio.
6. **MX (Mail Exchanger):** Especifica os servidores de email responsáveis pelo recebimento de emails para um domínio.
7. **PTR (Pointer):** Utilizado em registros reversos para mapear um endereço IP para um nome de domínio.
8. **SRV (Service):** Especifica a localização de servidores para determinados serviços.
9. **TXT (Text):** Armazena informações de texto arbitrárias associadas a um nome de domínio, frequentemente usado para verificações de propriedade e políticas de segurança.
10. **LOC (Location):** Fornece informações sobre a localização geográfica de um host.
# Resumo
- **DNS**: Traduz nomes de domínio legíveis por humanos em endereços IP.
- **Funcionamento**: Hierárquico e distribuído, com 13 clusters de servidores raiz no mundo.
- **Importância**: Fundamental para o acesso à internet; sem ele, a navegação seria impossível.
- Principais Registros DNS:
	- **SOA**: Informações sobre o domínio e sua autoridade.
	- **A/AAAA**: Mapeamento de domínios para endereços IPv4/IPv6.
	- **NS**: Servidores de nomes autorizados.
	- **CNAME**: Alias para outros domínios.
	- **MX**: Servidores de e-mail.
	- **PTR**: Registros reversos.
	- **SRV**: Localização de serviços.
	- **TXT**: Informações de texto arbitrárias.
# Conceito FQDN (Fully Qualified Domain Name)
- Nome completo de um domínio
- Nome que contém todas as partes que formam um domínio
- Sequência de rótulos de um nó até a parte root, separado por pontos
- Exemplo: prod192.mail.alpha.com.br.
	- prod192 -> usuário/máquina
	- mail -> unidade organizacional
	- alpha -> domínio delegado
	- com -> gTLD
	- br -> ccTLD
	- . -> root
## Conceito de Nameservers
- Programas específicos que armazenam informações sobre o namespace do domínio.
- Armazenam parte do namespace denominado de ZONA.
- O nameserver é AUTORITATIVO para esta ZONA.
- ZONA: alpha.com.br
## Tipos de Nameserver
- Primário: Lê os dados de uma zona a partir de um arquivo em seu host.
- Secundário: Obtém os dados da zona a partir de outro servidor de nomes autoritativo para a zona.
# Cache DNS
- Tem por objetivo reduzir a carga de processamento deste servidor no local em hosts intermediários.
- TTL (Time To Live): Processo de expiração e descarte de informações.
# Funções mais comuns do comando DIG
O *dig* (Domain Information Groper) é uma ferramenta poderosa para obter informações sobre nomes de domínio e servidores DNS. Ele é utilizado para diversos propósitos, como:
1. **Consultar registros DNS:**
	1. Obter o endereço IP de um nome de domínio (registro A): `dig example.com`
	2. Encontrar o servidor de email de um usuário (registro MX): `dig example.com MX`
	3. Descobrir os servidores de nome autoritativos para um domínio (registro NS): `dig example.com NS`
	4. Obter informações adicionais sobre um domínio (registro SOA): `dig example.com SOA`
	5. Consultar outros tipos de registros, como CNAME, TXT e SRV.
2. **Especificar um servidor DNS:**
	1. Consultar um servidor DNS específico para depuração: `dig @8.8.8.8 example.com`
	2. Usar um servidor de DNS alternativo para testar a resolução de nomes
3. **Filtrar resultados:**
	1. Mostar apenas um tipo de registro: `dig example.com A`
	2. Obter respostas em formato simplificado: `dig example.com +short`
	3. Exibir informações adicionais de depuração: `dig example.com +trace`
4. **Executar pesquisas avançadas:**
	1. Realizar pesquisas inversas de IP para encontrar o nome de domínio associado a um endereço IP: `dig -x 8.8.8.8`
	2. Transferir zonas DNS: `dig example.com @example.com -t zone`
	3. Executar pesquisas EDNS0 para obter informações adicionais de servidores DNS.
5. **Automatizar tarefas:**
	1. Usar o dig em scripts para automatizar tarefas de gerenciamento de DNS.
	2. Combinar o dig com outras ferramentas para obter informações mais abrangentes.