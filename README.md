# Finanças Pastel — PWA

Aplicação pessoal de finanças em português, local-first e pensada para iPhone.

## Build atual

**0.3 — UX/UI polish**

A interface usa a identidade aprovada: fundo creme quente, cartões pastel, lilás claro `#f4eef5`, menta, pêssego, rosa suave e azul-bebé, sem roxo escuro dominante.

## Como testar no computador

A PWA deve ser servida por HTTP/HTTPS; abrir `index.html` diretamente pode impedir Service Worker e outras APIs.

Na pasta do projeto:

```bash
python3 -m http.server 8080
```

Depois abrir `http://localhost:8080`.

## Como instalar no iPhone

Para instalar como PWA, a app precisa de estar alojada num endereço **HTTPS**. Depois:

1. Abrir o endereço no **Safari** do iPhone.
2. Tocar em **Partilhar**.
3. Escolher **Adicionar ao ecrã principal**.
4. Abrir **Finanças** pelo novo ícone.

Os dados são guardados localmente no dispositivo através de IndexedDB. Usa **Mais → Backups e exportação** regularmente para guardar uma cópia fora da app.

## Funcionalidades principais

- Página Mês como ecrã inicial, com mês atual/passado/futuro adaptativo.
- Objetivo mensal de poupança, orçamento e alertas.
- Despesas por categoria, expansíveis até aos movimentos.
- Registo manual de despesas, receitas e transferências.
- Reembolsos ligados à despesa original, totais ou parciais.
- Conta Principal, Revolut e outras contas, com acumulado interno desde €0.
- Recorrências integradas nos movimentos.
- Loja/Empresa, tags, subcategoria, nota e split em “Mais opções”.
- Pesquisa global e filtros avançados.
- Análise por categorias, contas, comerciantes, dia da semana e fim de semana.
- Resumo mensal automático.
- Regras automáticas e sugestões pelo histórico.
- PIN opcional, desligado por defeito.
- Backup/restauro e exportação CSV.
- Funcionamento offline após a primeira visita bem-sucedida.

## Nota sobre notificações

A build consegue usar notificações locais quando a PWA está ativa e tem permissão. Push agendado com a app totalmente fechada exige um backend/serviço push e não está incluído nesta versão.
