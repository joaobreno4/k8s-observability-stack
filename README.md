# Kubernetes & SRE Observability Stack

Repositorio dedicado a implementacao de uma infraestrutura de monitoramento hibrida, integrando Docker e Kubernetes para garantir a observabilidade total de aplicacoes e infraestrutura.

## Arquitetura do Projeto
- Infraestrutura: Docker Compose sustentando o core persistente (Zabbix Server e MySQL).
- Orquestracao: Kubernetes (Minikube) gerenciando workloads de aplicacao e agentes de monitoramento.
- Stack de Observabilidade:
  - Zabbix 7.0: Monitoramento de infraestrutura via Agente Ativo.
  - Prometheus: Coleta de metricas de performance do cluster.
  - Grafana: Dashboards estrategicos para visualizacao de SLIs.

## Desafios Tecnicos Superados
- Zabbix Active Agent: Implementacao de monitoramento push para superar isolamento de rede entre o cluster K8s e o host Docker.
- Resource Management: Configuracao de limites de CPU e Memoria validados via testes de estresse.
- Dashboards as Code: Exportacao e versionamento de paineis JSON para portabilidade do monitoramento.

## Instrucoes de Uso
1. Inicie o servidor de monitoramento: cd zabbix-server && docker compose up -d
2. Aplique os manifestos do cluster: kubectl apply -f k8s/
3. Importe os dashboards da pasta /dashboards no Grafana.

---
João Breno | DevOps & SRE Intern @ Deal
