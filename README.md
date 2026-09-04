# Machine do Bigorna 2.0 Ultra

**Abrir agora:** https://abner-machado.github.io/machine-bigorna/

Painel de finanças que roda em um arquivo só. Sem servidor, sem instalação, sem internet, sem conta.
Você abre o `index.html` e ele funciona — no computador, no celular ou no tablet.

Os seus números não saem do seu aparelho. Não existe envio para lugar nenhum: o painel lê o CSV
direto na memória do navegador e some quando você fecha a aba.

## O que ele mostra

O painel tem dez abas, todas alimentadas pelo mesmo CSV.

| Aba | O que responde |
|---|---|
| Visão geral | Saldo, receita, despesa, sobra do mês, melhor e pior mês, para onde o dinheiro sai |
| Painel do dono | Receita, margens, caixa, queima e pista, comparados com o mês, o trimestre, a meta e o ano passado |
| Resultado (DRE) | Receita, custo, lucro bruto, despesas, lucro operacional, impostos e lucro líquido |
| Fluxo de caixa | Saldo inicial, entradas, saídas por bloco, saldo final e previsão de três meses |
| Pista de decolagem | Queima bruta e líquida, meses de pista, data de caixa zero, receita de equilíbrio e três cenários |
| Orçamento vs real | Orçado, real, variação, quanto resta e previsão de fechamento por categoria |
| Alertas | Gasto fora do padrão, queda de receita, custo crescendo, melhor e pior mês, risco de caixa |
| Patrimônio | Bens, dívidas, patrimônio líquido, relação dívida sobre bens e quanto sobra por mês |
| Lançamentos | Tabela com busca e filtros de período, categoria, conta e tipo |
| Meus dados | Onde você cola ou abre o seu CSV |

## Como abrir

Escolha o jeito mais fácil para o seu aparelho.

### Pelo navegador, sem baixar nada

Abra https://abner-machado.github.io/machine-bigorna/ — funciona em qualquer celular ou computador.
Depois de abrir uma vez, ele continua funcionando mesmo sem internet, porque o arquivo fica no cache.

### No computador (Windows, Mac ou Linux)

1. Baixe o arquivo `index.html` (botão verde **Code**, depois **Download ZIP**).
2. Descompacte.
3. Dê dois cliques no `index.html`.

Pronto. Nenhum programa a instalar.

### No celular Android

1. Baixe o `index.html` pelo navegador.
2. Abra o aplicativo **Arquivos**, vá em **Downloads** e toque no arquivo.
3. Escolha abrir com o Chrome.

Para virar ícone na tela inicial: abra https://abner-machado.github.io/machine-bigorna/, toque nos três
pontinhos do Chrome e escolha **Adicionar à tela inicial**.

### No iPhone ou iPad

O iPhone não abre arquivo HTML solto direto do navegador. Faça assim:

1. Abra https://abner-machado.github.io/machine-bigorna/ no Safari.
2. Toque no botão de compartilhar, o quadradinho com a seta para cima.
3. Escolha **Adicionar à Tela de Início**.

Ele passa a abrir como se fosse um aplicativo, em tela cheia.

## Como colocar os seus números

Vá na aba **Meus dados**. Você pode colar o CSV na caixa ou abrir um arquivo do aparelho.

O cabeçalho esperado é este:

```csv
DATE,DESCRIPTION,CATEGORY,INCOME,EXPENSE,ACCOUNT,BALANCE
2026-09-01,Projeto do cliente X,Serviços,14200,,Conta PJ,32600
2026-09-03,Conta de luz,Energia,,510,Conta PJ,32090
```

Os nomes em português também funcionam: `DATA, DESCRICAO, CATEGORIA, ENTRADA, SAIDA, CONTA, SALDO`.

Detalhes que evitam dor de cabeça:

- Separador pode ser vírgula ou ponto e vírgula.
- Data aceita `2026-09-01` ou `01/09/2026`.
- Valor aceita `1.234,56` ou `1234.56`.
- A coluna de saldo é opcional. Se faltar, o painel recalcula sozinho.
- Cada linha é uma entrada **ou** uma saída, nunca as duas.

O painel já abre com dados de exemplo de uma micro-empresa de serviço, para você ver tudo
funcionando antes de colocar os seus. O botão **Restaurar exemplo** traz esses dados de volta
a qualquer momento.

## Como mudar as categorias e o orçamento

As duas listas ficam no começo do bloco de código do `index.html`, marcadas com comentário:

- `MAPA` diz em qual bloco do DRE cada categoria entra: receita, custo, operacional, imposto,
  dívida, investimento ou outras. Categoria desconhecida cai em operacional.
- `ORCAMENTO` guarda quanto você planeja gastar por mês em cada categoria.

Abra o arquivo em qualquer editor de texto, troque os nomes e os valores, salve.

## Feito para máquina fraca

Foi escrito pensando em computador simples e celular antigo:

- Nenhuma biblioteca externa. Sem React, sem Chart.js, sem jQuery. Os gráficos são SVG escrito à mão.
- Só a aba aberta é desenhada. As outras esperam você clicar.
- A busca espera 180 milissegundos antes de recalcular, para não travar enquanto você digita.
- A tabela de lançamentos desenha 250 linhas por vez, com botão para mostrar mais.
- Um arquivo de cerca de 100 KB, que é menos que uma foto.

## Exportar

O botão **Baixar CSV** salva os lançamentos do recorte que estiver filtrado.
O botão **Imprimir / PDF** usa a impressão do próprio navegador — escolha "Salvar como PDF".

---

## Autor

**Abner Machado**

- GitHub: https://github.com/Abner-Machado
- X: https://x.com/Fezrix
- Instagram: https://www.instagram.com/abner_hiller/
- YouTube (Fezrix): https://www.youtube.com/@Fezrix
- YouTube (Abner Machado): https://www.youtube.com/@Uabnermachado

## Licença

MIT. Use, altere e distribua à vontade, mantendo o aviso de licença.
