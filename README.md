# Renda e Desigualdade no Planalto Médio (RS)

Salário médio, PIB per capita e concentração de renda em cinco cidades do Planalto Médio gaúcho, pra mostrar por que média sozinha não conta a história toda sobre riqueza de um município.

🔗 [henriquepain.com.br/renda-desigualdade-rs](https://henriquepain.com.br/renda-desigualdade-rs/) — página do projeto e mapa interativo

## O achado

O PIB per capita mais alto do grupo não é o de Passo Fundo, a cidade-polo da região. É o de **Marau** (R$ 82.844,93), puxado por indústria concentrada. Mas o salário médio mais alto e a renda mais concentrada são os de **Passo Fundo**: em 2022, a renda domiciliar per capita média de Passo Fundo (R$ 2.343) era **1,56 vezes** a mediana (R$ 1.500), a maior razão média/mediana do grupo. Já **Serafina Corrêa** e **Tapejara** têm a renda mais igualmente distribuída (razão de 1,31), mesmo com PIB per capita mais baixo.

Ou seja: PIB per capita alto não significa necessariamente salário melhor, e não significa nada sobre como essa riqueza é distribuída.

| Cidade | População (2026) | Salário médio (SM, 2023) | PIB per capita (R$, 2023) | Renda média per capita (2022) | Renda mediana per capita (2022) | Razão média/mediana | Gini (2010) |
|---|---|---|---|---|---|---|---|
| Passo Fundo | 214.815 | 2,6 | 68.227,53 | 2.343,36 | 1.500,00 | **1,56** | 0,52 |
| Carazinho | 63.671 | 2,5 | 60.594,24 | 2.049,08 | 1.423,00 | 1,44 | 0,51 |
| Marau | 46.750 | 2,4 | **82.844,93** | 2.256,96 | 1.650,00 | 1,37 | 0,44 |
| Tapejara | 25.257 | 2,2 | 76.169,60 | 1.867,41 | 1.425,00 | 1,31 | 0,44 |
| Serafina Corrêa | 17.407 | 2,3 | 58.281,73 | 2.126,45 | 1.625,00 | **1,31** | 0,36 |

## Por que isso importa

PIB per capita é uma média: soma tudo que o município produz e divide pela população. Um punhado de empresas grandes (ou, no limite, alguns bilionários) empurra essa média pra cima sem que o trabalhador médio veja um centavo a mais no salário. É exatamente o padrão que aparece aqui: Marau e Tapejara têm PIB per capita maior que o de Passo Fundo, mas salário médio menor.

A razão entre renda média e renda mediana ataca o mesmo problema por outro ângulo, agora olhando pra dentro do próprio domicílio: quando a média está bem acima da mediana, é sinal de que uma minoria puxa o valor médio pra cima enquanto a maioria ganha menos que ele. Quanto mais perto de 1,0, mais parecida é a renda entre os moradores. O Gini de 2010, mesmo defasado, aponta na mesma direção: Passo Fundo mais concentrado, Serafina Corrêa mais igualitária. Duas medidas independentes, doze anos de distância uma da outra, contando a mesma história.

## Fontes e metodologia

| Indicador | Fonte | Ano | Cobertura |
|---|---|---|---|
| Salário médio mensal (trabalhadores formais) | IBGE, Cadastro Central de Empresas | 2023 | Todos os municípios |
| PIB per capita | IBGE, Contas Regionais | 2023 | Todos os municípios |
| Renda domiciliar per capita, média e mediana | IBGE, Censo Demográfico 2022 (SIDRA, tabela [10295](https://sidra.ibge.gov.br/tabela/10295)) | 2022 | Todos os municípios |
| Índice de Gini | Atlas do Desenvolvimento Humano (PNUD, Ipea, FJP), Censo Demográfico | 2010 | Todos os municípios |
| População estimada | IBGE, SIDRA (tabela 6579) | 2026 | Todos os municípios |

Salário médio e PIB per capita foram coletados do painel [IBGE Cidades](https://cidades.ibge.gov.br/), que é a única fonte que cobre municípios pequenos (a tabela "oficial" de salário médio do SIDRA, tabela 3421, só existe pra municípios com 50 mil habitantes ou mais, o que excluiria 4 das 5 cidades deste projeto). Renda média e mediana vieram direto da API do SIDRA (resultados preliminares da amostra do Censo 2022, tema Trabalho e Rendimento). O Gini veio do [Atlas Brasil](https://www.atlasbrasil.org.br/perfil), que expõe o cálculo por município feito pelo Censo Demográfico.

## Limitação conhecida

O Índice de Gini municipal só existe calculado até o **Censo 2010**. O Censo 2022 já divulgou o Gini nacional e estadual (tabela SIDRA [10301](https://sidra.ibge.gov.br/tabela/10301)), mas esse recálculo em nível de município ainda não foi publicado (situação em setembro de 2026, quase 4 anos depois do Censo). Por isso este projeto usa a razão entre renda média e mediana (2022, nível de município) como proxy de concentração de renda mais atual, com o Gini de 2010 como referência histórica complementar, não como substituto um do outro.

A razão média/mediana é um proxy reconhecido, mas mais simples que o Gini: ele reage à cauda superior da distribuição (quem ganha muito), mas não descreve a forma inteira da curva de renda. Ainda assim, bateu na mesma direção do Gini de 2010 nas cinco cidades, o que é um bom sinal de que o padrão é real e não um artefato de um único indicador.

## Mapa interativo

`mapa.html` mostra as cinco cidades sobre o mapa do Rio Grande do Sul (contorno oficial de município via [API de malhas do IBGE](https://servicodados.ibge.gov.br/api/docs/malhas)), coloridas pela razão renda média/mediana. Passar o mouse sobre uma cidade abre um popup com todos os indicadores. Município sem dado no projeto aparece em cinza.

Pra abrir localmente: como o navegador bloqueia `fetch` de arquivo local por CORS, sirva a pasta com qualquer servidor estático (ex.: `npx serve .` ou `python -m http.server`) e acesse `mapa.html`. Publicado via GitHub Pages, funciona direto.

## Estrutura

```
mapa.html                    mapa interativo (Leaflet)
data/cidades.csv             dataset consolidado, uma linha por município
data/rs_municipios.geojson   contorno dos municípios do RS (IBGE, malhas territoriais)
```

## Próximos passos

- [x] ~~Aluguel/custo de imóvel por cidade via scraping~~: testado em OLX e VivaReal, sem inventário suficiente pra 3 das 5 cidades (Tapejara e Serafina Corrêa com 0 anúncios, Marau com 1). Mercado de aluguel em cidade pequena não é anunciado online nessa região, então essa via foi descartada.
- [x] ~~Visualização interativa~~: mapa com hover em `mapa.html`
- [ ] Indicadores de qualidade de vida que cobrem todo município (saneamento, mortalidade infantil, IDEB) como eixo complementar
- [ ] Mais cidades do Planalto Médio
- [ ] Atualizar quando o Gini do Censo 2022 for publicado por município

## Licença

Projeto de portfólio / uso educacional. Dados públicos, sempre com fonte creditada.
