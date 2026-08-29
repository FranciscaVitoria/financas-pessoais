# Relatório de testes — Finanças Pastel

Data: 29/08/2026  
Build: 0.3 — UX/UI polish

## O que foi revisto nesta ronda

- Identidade visual alinhada com o mockup aprovado: fundo creme quente, cartões muito suaves e lilás claro `#f4eef5` em vez de roxo dominante.
- Hierarquia visual reforçada na Página Mês: cartão principal, métricas, insights, categorias, gráficos e movimentos com espaçamento e contraste mais consistentes.
- Barra inferior e botão `+` refinados para ecrã de iPhone, com alvos táteis mínimos de 44 px.
- Formulários e modais refinados para uso com uma mão: folha inferior, pega visual, cabeçalho sticky e inputs maiores.
- Estados ativos, foco, contraste, feedback tátil visual e `prefers-reduced-motion` revistos.
- Safe areas de iOS mantidas no topo e fundo.
- Manifest atualizado para PWA standalone, orientação portrait e ícones maskable.
- Service Worker atualizado para cache v3, de forma a não prender o utilizador na versão anterior depois de atualizar a app.

## Verificações técnicas executadas

- `app.js` validado com `node --check` sem erros de sintaxe.
- `manifest.webmanifest` validado como JSON.
- Integridade dos ficheiros essenciais verificada: HTML, CSS, JS, manifest, Service Worker e ícones 192/512.
- Estrutura CSS verificada com paridade de chavetas e presença da cor lilás aprovada `#f4eef5`.
- Fluxos funcionais da build 0.2 continuam preservados: movimentos, contas, transferências, reembolsos, recorrências, análise, PIN, regras, filtros, objetivos, backups e exportação.

## Teste em iPhone/Safari

O ambiente de desenvolvimento não disponibiliza um iPhone físico nem Safari/WebKit real. Por isso, não é correto afirmar que esta ronda foi validada num dispositivo físico. A build foi preparada especificamente para iOS/PWA (viewport-fit=cover, safe areas, standalone mode, apple-mobile-web-app metadata e touch targets), mas a validação final deve ser feita após alojamento HTTPS num iPhone real.

Checklist recomendado no iPhone:

1. Abrir o URL em Safari e escolher “Adicionar ao ecrã principal”.
2. Abrir a app pelo ícone e confirmar que não aparece a barra do Safari.
3. Registar 3–5 movimentos e fechar totalmente a app; reabrir e confirmar persistência.
4. Confirmar navegação entre Mês, Movimentos, Análise e Mais.
5. Abrir o `+`, testar teclado numérico, data, selects e “Mais opções”.
6. Testar scroll até ao fim da Página Mês sem a barra inferior tapar conteúdo.
7. Fazer uma transferência Principal → Revolut e confirmar acumulados.
8. Fazer um reembolso parcial e confirmar o valor líquido.
9. Testar PIN e bloqueio automático, se ativado.
10. Colocar o iPhone em modo avião depois de uma primeira visita e confirmar que a app abre offline.

## Limitação conhecida

Push notifications verdadeiramente agendadas com a app totalmente fechada continuam a exigir infraestrutura de push/backend. Os alertas locais atuais não substituem esse serviço.
