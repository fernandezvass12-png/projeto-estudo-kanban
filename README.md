# Projeto de Estudo - Kanban

## Objetivo
Este repositório foi criado para aplicar na prática um fluxo de engenharia baseado em Kanban, utilizando GitHub Issues, GitHub Projects (Board), Pull Requests e automações de rastreabilidade.

## Estrutura do Quadro (Recomendação)
- Backlog
- Em Análise / Ready
- Desenvolvimento (In Progress)
- Revisão de Código / PR
- Validação / Testes (QA)
- Concluído (Done)

## WIP Limits (para equipe de 3 desenvolvedores — sugestão)
- Backlog: 5
- Em Análise / Ready: 3
- Desenvolvimento: 2
- Revisão de Código / PR: 2
- Validação / Testes: 2

## Política explícita de avanço (exemplo)
1. Um cartão só pode passar de Desenvolvimento para Revisão de Código / PR quando:
   - a implementação contempla os critérios de aceite;
   - a branch foi atualizada com a `main`;
   - há pelo menos um commit com mensagem semântica explicativa;
   - foi aberto um Pull Request apontando para `main`.
2. Um cartão só pode passar de Revisão para Validação quando:
   - o PR foi revisado e as alterações solicitadas foram resolvidas;
   - testes automatizados relevantes passaram (se aplicável).
3. Um cartão só é movido para Concluído quando:
   - o PR foi mergeado na `main`;
   - as entregas foram validadas em homologação (quando aplicável).

## Exemplo de Issue (copiar/colar)
Título: `feat: adicionar autenticação via JWT`

```md
### Descrição da Funcionalidade

Como cliente cadastrado, desejo realizar login utilizando e-mail e senha para acessar meu painel de compras.

### Critérios de Aceite (Definition of Done)

- [ ] Endpoint `/api/auth/login` implementado com método POST.
- [ ] Senhas validadas com hash seguro (bcrypt/argon2).
- [ ] Retorno de token JWT com expiração em 2 horas em caso de sucesso.
- [ ] Retorno de status HTTP 401 para credenciais inválidas.
- [ ] Cobertura mínima de testes unitários de 85%.
```

Metadados sugeridos: assignees, labels: `enhancement`, `priority: high`, project: `Quadro de Desenvolvimento - Sprint 1`, milestone: `v1.0.0-MVP`.

## Fluxo Git (exemplo rápido)
```bash
git checkout main
git pull origin main
git checkout -b feature/issue-3-autenticacao-jwt
# desenvolver
git add .
git commit -m "feat(auth): adiciona endpoint e geracao de token jwt"
git push origin feature/issue-3-autenticacao-jwt
```
Abra um Pull Request com na descrição: `Closes #<número-da-issue>` para fechamento automático.

## Entregáveis (instruções)
- Criar o Project board no GitHub: Repositório → Projects → New project → Template: Board → Nome: `Quadro de Desenvolvimento - Sprint 1`.
- Recriar as colunas e configurar Column limits conforme WIP limits acima.
- Converter os cartões manuais em Issues completas e vincular ao Project.

---

Arquivo gerado automaticamente pelo assistente. Para editar este README, abra um Pull Request ou edite diretamente no repositório.
