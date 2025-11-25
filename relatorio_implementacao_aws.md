# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

Data: 25 de Novembro de 2025
Empresa: Abstergo Industries
Responsável: Manus (Agente de IA)

## Introdução
Este relatório técnico detalha o processo de implementação de três serviços estratégicos da Amazon Web Services (AWS) na empresa **Abstergo Industries**, com o objetivo primário de alcançar uma **diminuição imediata e sustentável dos custos** de infraestrutura em nuvem. A seleção dos serviços foi focada em ferramentas que proporcionam ganhos rápidos (quick wins) através da otimização de recursos e eliminação de desperdício, essenciais para o contexto de uma operação farmacêutica que busca eficiência operacional.

## Descrição do Projeto
O projeto de otimização de custos foi estruturado em três etapas distintas, cada uma focada na implementação de um serviço AWS que atua diretamente na redução de despesas operacionais (OpEx). A seguir, são detalhados os serviços escolhidos, seus focos e os casos de uso específicos para a Abstergo Industries.

| Etapa | Serviço AWS | Foco Principal | Benefício Imediato |
| :---: | :--- | :--- | :--- |
| 1 | AWS Compute Optimizer | Dimensionamento Correto (Right-Sizing) de Recursos de Computação | Redução de custos com instâncias superdimensionadas. |
| 2 | Amazon S3 Intelligent-Tiering | Otimização Automática de Custos de Armazenamento | Economia no armazenamento de dados de acesso infrequente. |
| 3 | AWS Trusted Advisor | Identificação e Eliminação de Recursos Ociosos | Corte de despesas com infraestrutura provisionada e não utilizada. |

### Etapa 1: Otimização de Recursos com AWS Compute Optimizer
- **Nome da ferramenta:** AWS Compute Optimizer
- **Foco da ferramenta:** Análise preditiva e recomendação de **dimensionamento correto (right-sizing)** para recursos de computação, incluindo instâncias Amazon EC2, volumes Amazon EBS, funções AWS Lambda e tarefas AWS Fargate. O serviço utiliza aprendizado de máquina para analisar o histórico de utilização e sugerir o tipo e tamanho de recurso mais econômico que atenda aos requisitos de desempenho.
- **Descrição de caso de uso:** A Abstergo Industries hospeda seu sistema de gestão de estoque e a plataforma de e-commerce em instâncias EC2. O Compute Optimizer foi implementado para analisar o histórico de métricas de CPU, memória e rede. O caso de uso consiste em identificar e migrar instâncias que operam consistentemente com baixa utilização (abaixo de 40% de CPU, por exemplo) para tipos de instância menores e mais adequados (ex: de `m5.large` para `t3.medium`). Esta ação resulta em uma **redução de custo imediata** na fatura de computação, eliminando o desperdício de capacidade não utilizada.

### Etapa 2: Gerenciamento de Armazenamento com Amazon S3 Intelligent-Tiering
- **Nome da ferramenta:** Amazon S3 Intelligent-Tiering
- **Foco da ferramenta:** Otimização automática e contínua dos custos de armazenamento de objetos no Amazon Simple Storage Service (S3). O serviço move automaticamente os dados entre as classes de acesso (Standard, Infrequent Access, Archive Instant Access) com base nos padrões de acesso, sem taxas de recuperação.
- **Descrição de caso de uso:** A operação farmacêutica gera um grande volume de dados, como logs de transações de PDV, backups de sistemas legados e imagens de produtos para o e-commerce. A maioria desses dados se torna de acesso infrequente após 30 dias. O S3 Intelligent-Tiering foi configurado no bucket principal. O serviço garante que os dados que não são acessados por 30 dias sejam movidos para a camada de acesso infrequente, que possui um custo de armazenamento significativamente menor. Isso proporciona uma **economia imediata e passiva** no custo mensal de armazenamento, sem a necessidade de políticas de ciclo de vida manuais ou complexas.

### Etapa 3: Identificação de Desperdício com AWS Trusted Advisor (Verificações de Otimização de Custo)
- **Nome da ferramenta:** AWS Trusted Advisor (Verificações de Otimização de Custo)
- **Foco da ferramenta:** Fornecer um conjunto de verificações de melhores práticas que abrangem cinco pilares (Otimização de Custo, Desempenho, Segurança, Tolerância a Falhas e Limites de Serviço). O foco principal neste projeto é a categoria **Otimização de Custo**, que identifica recursos ociosos ou subutilizados.
- **Descrição de caso de uso:** O Trusted Advisor foi ativado para realizar varreduras diárias na conta AWS da Abstergo Industries. O caso de uso consiste em agir imediatamente sobre as recomendações de otimização de custo, como:
    1.  Encerrar volumes Amazon EBS que não estão anexados a nenhuma instância.
    2.  Liberar endereços IP elásticos (EIPs) que não estão associados a uma instância em execução.
    3.  Excluir balanceadores de carga (Load Balancers) que não possuem instâncias registradas.
Ao eliminar esses recursos provisionados, mas não utilizados, a Abstergo Industries obtém uma **eliminação de custos desnecessários** de forma rápida e com baixo esforço operacional.

## Conclusão
A implementação dos serviços **AWS Compute Optimizer**, **Amazon S3 Intelligent-Tiering** e **AWS Trusted Advisor** na empresa Abstergo Industries estabelece uma base sólida para a governança de custos em nuvem. O resultado esperado é **a otimização proativa do uso de recursos de computação e armazenamento, a eliminação sistemática de desperdício de infraestrutura e a garantia de que os dados sejam armazenados na classe de custo mais eficiente**, o que aumentará a eficiência operacional e a produtividade da empresa. Recomenda-se a continuidade da utilização e monitoramento dessas ferramentas, integrando-as a uma cultura de FinOps para maximizar os benefícios a longo prazo.

## Anexos

- [Relatório de recomendações de right-sizing do AWS Compute Optimizer (Pré-implementação)]
- [Relatório de economia gerada pelo S3 Intelligent-Tiering (30 dias após a implementação)]
- [Lista de recursos ociosos encerrados com base nas recomendações do Trusted Advisor]
- [Link para o dashboard do AWS Cost Explorer, mostrando a curva de redução de custos]

Assinatura do Responsável pelo Projeto:

Manus (Agente de IA)
