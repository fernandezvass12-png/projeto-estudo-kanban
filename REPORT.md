Relatório Acadêmico — Atividade Prática: Aplicação do Kanban e Integração GitHub

Aluno: 
Disciplina: 
Data: 

Resumo
Este relatório documenta a execução prática do quadro Kanban no GitHub Projects, a criação de Issues, a gestão do fluxo com limites de WIP, e a experimentação do ciclo Git/PR com rastreabilidade automática. As respostas às questões foram embasadas na literatura recomendada: Ahmad et al. (2014), Ikonen et al. (2011), Gousios et al. (2014) e Anderson (2010).

1. Introdução
O Kanban é uma abordagem derivada do pensamento Lean que busca limitar o trabalho em progresso, expor gargalos e melhorar o fluxo de valor. Nesta atividade, aplicou-se o método em um repositório de estudo, criando políticas explícitas, limites de WIP e automações via Pull Requests.

2. Materiais e Métodos
- Repositório GitHub: https://github.com/fernandezvass12-png/projeto-estudo-kanban
- Estrutura do quadro: Backlog, Em Análise / Ready, Desenvolvimento, Revisão de Código / PR, Validação / Testes, Concluído.
- WIP limits definidos para simular uma equipe de 3 desenvolvedores.

3. Respostas às Questões (análise crítica)

Questão 1 — Ahmad et al. (2014)
(a) Dois principais benefícios reportados pelas equipes ao adotarem Kanban:
   1. Redução do tempo de ciclo (lead time) e aumento da previsibilidade das entregas: a gestão visual e a limitação de WIP permitem identificar e mitigar impedimentos, reduzindo o tempo desde a solicitação até a entrega.
   2. Melhoria na visibilidade do fluxo e na qualidade do produto: com políticas explícitas e monitoramento contínuo, defeitos e retrabalho tendem a diminuir porque as equipes conseguem detectar padrões e pontos fracos no processo.

Esses resultados são consistentes com a revisão sistemática de Ahmad et al. (2014), que agrega evidências empíricas sobre ganhos em tempo de ciclo e visibilidade do fluxo.

(b) Como o WIP limita o context switching?
Limitar o trabalho em progresso reduz o número de itens ativos por desenvolvedor, o que diminui a necessidade de alternar entre tarefas distintas. Com menos itens simultâneos, cada desenvolvedor consegue manter foco mais prolongado numa tarefa, diminuindo custos cognitivos associados à troca de contexto (troca de memória de trabalho, reorientação de problemas e tempo de re-aquecimento). Em termos práticos, WIP limits forçam a equipe a concluir itens abertos ou a colaborar (swarming) para liberar capacidade antes de puxar novas tarefas, diminuindo preempção e overhead.

Questão 2 — Ikonen et al. (2011)
(a) Situação: coluna Revisão de Código / PR atingiu limite (4 itens) e há 3 itens prontos em Desenvolvimento.
O que os desenvolvedores devem fazer?
Resposta: Segundo princípios do Kanban, os desenvolvedores não devem iniciar novas tarefas que aumentem o WIP a montante; ao invés disso, devem trabalhar para reduzir o gargalo na coluna de Revisão. Isso inclui:
- Priorizar a finalização dos itens em progresso;
- Ajudar a revisar PRs ou resolver comentários;
- Estruturar pares de revisão ou swarming para liberar capacidade.
Começar novas tarefas do Backlog agravaria o gargalo e aumentaria o lead time total.

(b) O que caracteriza o swarming?
Swarming é uma técnica cooperativa onde múltiplos membros da equipe concentram esforços para concluir um ou poucos itens prioritários até a sua finalização. Caracteriza-se por:
- Alocação temporária de recursos para remover bloqueios;
- Comunicação intensiva e trabalho coordenado;
- Foco em completar itens ao invés de iniciar novos.
No cenário, swarming ocorreria quando desenvolvedores da coluna Desenvolvimento ajudam ativamente nas revisões e correções para reduzir o número de itens na coluna de Revisão.

Questão 3 — Gousios et al. (2014)
Por que a integração Git/PR com Issues/Projects melhora a confiabilidade na auditoria e controle de qualidade?
A integração técnica entre código e gestão de trabalho cria uma trilha auditável onde cada change-set, revisão e decisão fica atrelada a uma Issue e a um Pull Request. Benefícios:
- Vinculação automática entre código e requisito (traceability): commits e PRs referenciam issues com palavras-chave (e.g., `Closes #3`).
- Registro do histórico de revisão: comentários, aprovações e checks ficam preservados no PR.
- Automatização de fechamento e movimentação no Project board, reduzindo erro humano.
- Facilidade de auditoria e replicação de testes – todas as evidências estão no mesmo ecossistema.
Em contrapartida, usar ferramentas desconectadas (planilhas) aumenta o risco de divergência entre estado real do código e o controle de trabalho.

Questão 4 — Lead Time vs. Cycle Time
(a) Definições técnicas:
- Lead Time: tempo total desde a solicitação do cliente (ou entrada no backlog) até a entrega ao usuário final.
- Cycle Time: tempo efetivo gasto na execução do trabalho (desde que o time começa a trabalhar ativamente no item até sua conclusão).

(b) Pontos de início e fim no repositório/quadro do GitHub:
- Lead Time: inicia quando a Issue entra no Backlog (ou quando é criada e priorizada no quadro) e termina quando o cartão é movido para Concluído após validação e merge.
- Cycle Time: inicia quando a Issue é puxada para Desenvolvimento (In Progress) e termina quando o PR é mergeado e a funcionalidade validada — ou, de forma alternativa, quando o cartão sai da coluna Desenvolvimento e chega em Concluído, dependendo das políticas locais.

4. Conclusões
A integração do Kanban com as ferramentas nativas do GitHub permite uma prática sustentável de engenharia: limites de WIP controlam o fluxo, políticas explícitas reduzem ambiguidade e integração PR↔Issue melhora rastreabilidade e conformidade.

5. Referências
- Ahmad, M. O., Markkula, J., & Oivo, M. (2014). Kanban in software development: A systematic literature review. Information and Software Technology, 56(12), 1633–1654.
- Ikonen, M., Pirinen, E., Fagerholm, F., Kettunen, P., & Abrahamsson, P. (2011). On the Impact of Kanban on Software Project Adaptability: An Empirical Study. ESEM 2011.
- Gousios, G., Pinzger, M., & van Deursen, A. (2014). An exploratory study of the pull-based software development model. ICSE 2014.
- Anderson, D. J. (2010). Kanban: Successful Evolutionary Change for Your Technology Business. Blue Hole Press.

---

Arquivo gerado automaticamente como entregável do aluno.
