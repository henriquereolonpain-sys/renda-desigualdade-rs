# Renda e Desigualdade no Planalto Médio (RS)

Salário médio, PIB per capita e Índice de Gini em cinco cidades do Planalto Médio gaúcho, pra mostrar por que média sozinha não conta a história toda sobre riqueza de um município.

## O achado

O PIB per capita mais alto do grupo não é o de Passo Fundo, a cidade-polo da região. É o de **Marau** (R$ 82.844,93), puxado por indústria concentrada. Mas o salário médio mais alto e a renda mais concentrada (maior Gini) são os de **Passo Fundo**. Já **Serafina Corrêa**, com o menor PIB per capita do grupo, tem de longe a distribuição de renda mais igualitária (Gini 0,36, quase 30% menor que o de Passo Fundo).

Ou seja: PIB per capita alto não significa necessariamente salário melhor, e não significa nada sobre como essa riqueza é distribuída.

| Cidade | População (2026) | Salário médio (SM, 2023) | PIB per capita (R$, 2023) | Gini (2010) |
|---|---|---|---|---|
| Passo Fundo | 214.815 | 2,6 | 68.227,53 | **0,52** |
| Carazinho | 63.671 | 2,5 | 60.594,24 | 0,51 |
| Marau | 46.750 | 2,4 | **82.844,93** | 0,44 |
| Tapejara | 25.257 | 2,2 | 76.169,60 | 0,44 |
| Serafina Corrêa | 17.407 | 2,3 | 58.281,73 | **0,36** |

## Por que isso importa

PIB per capita é uma média: soma tudo que o município produz e divide pela população. Um punhado de empresas grandes (ou, no limite, alguns bilionários) empurra essa média pra cima sem que o trabalhador médio veja um centavo a mais no salário. É exatamente o padrão que aparece aqui: Marau e Tapejara têm PIB per capita maior que o de Passo Fundo, mas salário médio menor.

O Gini resolve parte desse problema porque mede concentração, não volume. Um Gini baixo como o de Serafina Corrêa (0,36) sugere uma economia onde a renda circula de forma mais parecida entre os moradores, mesmo que o bolo total seja menor.

## Fontes e metodologia

| Indicador | Fonte | Ano | Cobertura |
|---|---|---|---|
| Salário médio mensal (trabalhadores formais) | IBGE, Cadastro Central de Empresas | 2023 | Todos os municípios |
| PIB per capita | IBGE, Contas Regionais | 2023 | Todos os municípios |
| Índice de Gini | Atlas do Desenvolvimento Humano (PNUD, Ipea, FJP), Censo Demográfico | 2010 | Todos os municípios |
| População estimada | IBGE, SIDRA (tabela 6579) | 2026 | Todos os municípios |

Salário médio e PIB per capita foram coletados do painel [IBGE Cidades](https://cidades.ibge.gov.br/), que é a única fonte que cobre municípios pequenos (a tabela "oficial" de salário médio do SIDRA, tabela 3421, só existe pra municípios com 50 mil habitantes ou mais, o que excluiria 4 das 5 cidades deste projeto). O Gini veio do [Atlas Brasil](https://www.atlasbrasil.org.br/perfil), que expõe o cálculo por município feito pelo Censo Demográfico.

## Limitação conhecida

O Índice de Gini municipal só existe calculado até o **Censo 2010**. O Censo 2022 já coletou dado de renda, mas esse recálculo em nível de município ainda não foi publicado (situação em setembro de 2026, quase 4 anos depois do Censo). Ou seja: é o melhor dado público que existe hoje, mas está defasado em até 16 anos, e cidades pequenas podem ter mudado bastante nesse intervalo. Salário médio e PIB per capita, por outro lado, são de 2023, bem mais recentes.

Esse projeto assume que a defasagem afeta as cinco cidades de forma parecida (todas passaram por dinâmicas econômicas regionais similares), o que é uma simplificação, não uma certeza.

## Estrutura

```
data/cidades.csv    dataset consolidado, uma linha por município
```

## Próximos passos

- [ ] Aluguel/custo de imóvel por cidade (via scraping, não existe API pública pra município pequeno)
- [ ] Mais cidades do Planalto Médio
- [ ] Série histórica quando o Gini do Censo 2022 for publicado por município
- [ ] Visualização interativa (dashboard)

## Licença

Projeto de portfólio / uso educacional. Dados públicos, sempre com fonte creditada.
