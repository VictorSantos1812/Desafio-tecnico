# Desafio Técnico: Arquitetura Web Distribuída

## Contexto

Você precisa implementar uma solução de arquitetura web distribuída para uma empresa que está expandindo seus serviços. O objetivo é criar uma infraestrutura resiliente que possa suportar múltiplos servidores web compartilhando o mesmo conteúdo.

## Objetivo do Desafio

Implementar uma arquitetura web distribuída utilizando as seguintes tecnologias:

- **HAProxy** para balanceamento de carga
- **Nginx** como servidor web (múltiplas instâncias)
- **NFS** para compartilhamento de arquivos
- **Linux** como sistema operacional base

## Cenário de Negócio

A empresa possui um site estático que precisa estar disponível 24/7. Com o crescimento do tráfego, foi necessário implementar:

1. **Alta Disponibilidade**: O site não pode ficar indisponível
2. **Balanceamento de Carga**: Distribuir requisições entre múltiplos servidores
3. **Conteúdo Centralizado**: Todos os servidores devem servir o mesmo conteúdo
4. **Monitoramento**: Visibilidade sobre o status da infraestrutura

## Requisitos Técnicos

### Infraestrutura

Você deve criar 4 máquinas virtuais Linux com as seguintes especificações:

| Máquina | Função | IP | Recursos |
|---------|--------|----|---------| 
| vm1 | Balanceador | 192.168.1.10 | 1GB RAM, 1 CPU |
| vm2 | Servidor Web 1 | 192.168.1.11 | 1GB RAM, 1 CPU |
| vm3 | Servidor Web 2 | 192.168.1.12 | 1GB RAM, 1 CPU |
| vm4 | Servidor de Arquivos | 192.168.1.13 | 1GB RAM, 1 CPU |

### Arquitetura Esperada

```
[Cliente] → [Balanceador] → [Servidor Web 1] → [Servidor de Arquivos]
                    → [Servidor Web 2] → [Servidor de Arquivos]
```

## Tarefas a Serem Realizadas

### 1. Configuração do Servidor de Arquivos
- Implementar sistema de compartilhamento de arquivos em rede
- Configurar permissões adequadas para acesso remoto
- Garantir que o conteúdo seja acessível por todos os servidores web

### 2. Configuração dos Servidores Web
- Instalar e configurar servidores web
- Conectar os servidores ao sistema de arquivos compartilhado
- Garantir que todos servem o mesmo conteúdo
- Configurar logs para monitoramento

### 3. Configuração do Balanceador
- Implementar balanceamento de carga entre os servidores web
- Configurar algoritmo de distribuição de requisições
- Implementar health checks para monitoramento
- Configurar interface de monitoramento

### 4. Testes e Validação
- Verificar se o balanceamento está funcionando
- Testar cenários de falha (alta disponibilidade)
- Validar que o conteúdo é consistente entre servidores
- Documentar procedimentos de instalação e execução de testes neste repositório do Bitbucket através de Markdown

## Critérios de Sucesso

### Funcionalidade
- [ ] Cliente consegue acessar o site através do balanceador
- [ ] Requisições são distribuídas entre os servidores web
- [ ] Todos os servidores servem o mesmo conteúdo
- [ ] Sistema continua funcionando quando um servidor web falha

### Performance
- [ ] Balanceamento efetivo entre servidores
- [ ] Sem perda de requisições durante falhas

### Monitoramento
- [ ] Interface de monitoramento acessível
- [ ] Logs configurados e acessíveis
- [ ] Métricas de performance visíveis

## Entregáveis Esperados

### Documentação
1. **Relatório de Implementação**: Documentar todas as configurações realizadas
2. **Procedimentos de Troubleshooting**: Guia para resolver problemas comuns
3. **Testes Realizados**: Evidências de que todos os critérios foram atendidos

### Evidências Técnicas
1. **Screenshots** da interface de monitoramento
2. **Logs** demonstrando o funcionamento do balanceamento
3. **Testes de carga** mostrando distribuição entre servidores
4. **Testes de falha** demonstrando alta disponibilidade

## Restrições e Considerações

### Limitações Técnicas
- Não é permitido usar ferramentas de orquestração (Docker, Kubernetes)
- Implementação deve ser nativa no Linux
- Focar em soluções open-source

### Segurança
- Configurar permissões adequadas para compartilhamento de arquivos
- Implementar logs de segurança

### Performance
- Otimizar configurações para o ambiente disponível
- Monitorar uso de recursos

## Recursos de Aprendizado

### Documentação Oficial
- [HAProxy Documentation](http://www.haproxy.org/#docs)
- [Nginx Documentation](https://nginx.org/en/docs/)
- [NFS Ubuntu Guide](https://ubuntu.com/server/docs/service-nfs)

### Conceitos Importantes
- Load Balancing e algoritmos de distribuição
- Sistemas de arquivos em rede
- Alta disponibilidade e failover
- Monitoramento de infraestrutura

## Dicas Importantes

1. **Comece simples**: Implemente cada componente separadamente antes de integrar
2. **Teste constantemente**: Valide cada etapa antes de prosseguir
3. **Documente tudo**: Registre configurações e problemas encontrados
4. **Pense em falhas**: Como o sistema se comporta quando algo falha?
5. **Monitore recursos**: Acompanhe uso de CPU, memória e rede

### Suporte

Durante o desenvolvimento, você pode:

- Consultar documentação oficial das tecnologias
- Pesquisar soluções para problemas específicos
- Testar diferentes abordagens
- Documentar dúvidas e descobertas
