# Conceito
Um proxy é uma estrutura que atua como intermediário entre a rede interna e a internet. Quando um usuário acessa a internet por meio de um proxy, a solicitação passa pelo proxy antes de alcançar o destino final. O acesso é realizado através do endereço IP do servidor proxy, e não do IP do usuário.
# Funções
1. **Cache de Páginas Web:** Armazena em cache páginas web frequentemente acessadas para reduzir a carga de rede e melhorar a velocidade de acesso.
2. **Eliminação de acessos redundantes:** Evita múltiplas solicitações desnecessárias para os mesmos recursos.
3. **Centralização de Configurações:** Permite gerenciar de forma centralizada o acesso aos serviços externos.
4. **Reaproveitamento de conteúdo:** Utiliza parte do conteúdo em cache mesmo após a atualização de páginas web.
5. **Otimização da banda de link:** Reduz o consumo de banda ao otimizar as solicitações de dados.
# Vantagens
1. **Segurança:** Protege os clientes privados de serem expostos externamente, utilizando regras de NAT (Network Address Translation).
2. **Bloqueio de URLs suspeitas:** Permite bloquear URLs perigosas através de listas de liberação e negação.
3. **Filtragem de Conteúdo:** Aplica filtros para bloquear conteúdos suspeitos ou perigosos, controlando extensões de arquivos trafegados.
4. **Consistência do Conteúdo:** Garante a consistência do conteúdo retornado.
5. **Eliminação de Roteamento:** Remove a necessidade de roteamento na camada de transporte entre redes.
6. **Centralização:** Oferece um único ponto de acesso, controle e monitoração.
# Considerações
- **Bloqueios e perfis:** Manter as listas de bloqueio e URLs suspeitas atualizadas, além de criar perfis de acesso conforme as necessidades.
- **Monitoramento e Segurança:** Acesso aos logs de registro de atividades e sites visitados pode ser configurado, além de alertas para ataques em andamento.
# Desvantagens
1. **Ponto de falha único:** A centralização pode criar um ponto de falha único.
2. **Impacto durante manutenção:** As áreas podem ser impactadas durante a manutenção das regras.
3. **Compatibilidade de Software:** Os clientes devem ser capazes de trabalhar com a arquitetura de proxy.
4. **Proteção do Sistema Operacional:** O proxy não protege o sistema operacional base.
5. **Configurações padrão:** As configurações padrão são otimizadas para desempenho, não para segurança.
# Tipos de proxy
1. **Proxy transparente:** Utiliza um firewall para redirecionar automaticamente todo o tráfego de acesso à web para o proxy, eliminando a necessidade de configuração manual dos navegadores clientes.
2. **Proxy anônimo:** Não deixa vestígios, ocultando informações de identificação do computador de origem ao acessar a internet.
# Serviço Proxy - SQUID
O **squid** é um dos proxies mais utilizados na internet, conhecido por sua simplicidade e confiabilidade. Suporta HTTP, HTTPS e FTP, além de hierarquias de proxy e listas de controle de acesso (ACLs). É estável, seguro e de alta performance, disponível para diversos sistemas operacionais.
# ACL (Access Control List)
As ACLs são regras para navegação via proxy Squid, especificadas pro sintaxes como: `acl NOME_DA_ACL TIPO_DA_ACL parâmetro`
## Tipos de ACL
- **src (origem):** Trata o IP ou faixa de IP de onde o cliente acessa.
- **dst (destino):** Trata o IP de destino da navegação.
- **dstdomain (domínio de destino):** Trata o domínio de destino da navegação.
- **url_regex:** Trata uma determinada entrada na URL.
- **port (porta):** Tratga a porta de destino da navegação.
- **proxy_auth:** Trata o login com que o cliente se autentica no proxy.
## Critérios para avaliação de soluções/serviços para a rede corporativa
- Cases de sucesso
- Pré-requisitos necessários
- Processo de instalação
- Processo de migração
- Treinamento nivelamento do conhecimento
- Suporte
- SLA
- Plataforma de gerenciamento
- Esquema de atualização
- Integração com demais soluções
- Ferramentas de monitoramento
- Aumento do serviço/solução
- Rastreabilidade Auditoria
- Requisitos de segurança
- Tendências da solução /serviço
- Legislação (Compliance)
- ROI (Retorno sobre o investimento)