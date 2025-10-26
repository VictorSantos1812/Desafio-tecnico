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
- Conectar os servidores ao sistema de
