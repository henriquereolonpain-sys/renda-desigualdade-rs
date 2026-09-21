# Renda e Desigualdade no Rio Grande do Sul

PIB per capita e concentração de renda nos **497 municípios do Rio Grande do Sul** (cobertura completa do estado), pra mostrar por que média sozinha não conta a história toda sobre riqueza de um município.

🔗 [henriquepain.com.br/renda-desigualdade-rs](https://henriquepain.com.br/renda-desigualdade-rs/) — página do projeto e mapa interativo

## O achado

Entre as cidades grandes, a renda mais concentrada do estado é a de **Porto Alegre**: em 2022, a renda domiciliar per capita média da capital (R$ 3.203) era **1,88 vezes** a mediana (R$ 1.700). Mas olhando pros 497 municípios sem filtro de tamanho, o topo do ranking vira coisa de cidade pequena: **Rondinha** (razão 1,92, ~5 mil habitantes) e **Tiradentes do Sul** (1,91, ~5,2 mil habitantes) superam até a capital. Isso é compatível com efeito de amostra pequena, e não necessariamente com desigualdade maior: a razão vem de amostra do Censo e oscila mais em cidade pequena (detalhes na [Análise 3](https://henriquepain.com.br/renda-desigualdade-rs/analise.html#a3) e na seção de limitações). No outro extremo, **Novo Machado** (1,06) e **Mampituba** (1,08) dividem o posto de renda mais distribuída, ambos também municípios pequenos.

PIB per capita também não segue a lógica óbvia de "cidade grande = mais rica per capita": **Santa Cruz do Sul** (R$ 96.885) e **Guaíba** (R$ 93.821) superam a própria Porto Alegre (R$ 75.420), puxadas por indústria concentrada — o mesmo padrão que motivou este projeto lá no início, com Marau superando Passo Fundo. Um caso extremo é **Triunfo**, sede do polo petroquímico do estado: PIB per capita de R$ 266.268 (o segundo maior do RS, atrás só de Muitos Capões, com R$ 323.562 e cerca de 2,9 mil habitantes), mas renda mediana de apenas R$ 1.200 — a riqueza gerada ali não se traduz em renda mais alta pra maioria de quem mora na cidade. A [Análise 1](https://henriquepain.com.br/renda-desigualdade-rs/analise.html#a1) mede isso pros 497 municípios.

**Importante**: concentração de renda (a razão média/mediana) e nível de renda (quanto a pessoa típica ganha) são eixos diferentes, não a mesma coisa. Uma cidade pode ser pobre e desigual ao mesmo tempo — é o caso de **Pelotas**: renda mediana relativamente baixa (R$ 1.212) *e* razão de 1,62 (uma das mais altas entre as cidades grandes), ou seja, pouca renda *e* concentrada nas mãos de poucos. O extremo disso é **Redentora**, no noroeste do estado: renda mediana de apenas R$ 606, a mais baixa de todos os 497 municípios — menos da metade da renda domiciliar per capita de qualquer outra cidade grande da lista. Já cidades da Serra Gaúcha como Carlos Barbosa, Farroupilha e Bento Gonçalves aparecem com renda mediana alta *e* razão baixa — mais ricas *e* mais igualmente distribuídas, uma hipótese plausível é uma base industrial pulverizada em muitas empresas médias (móveis, vinho, metalmecânica) em vez de poucos grandes empregadores. Isso é hipótese: a [Análise 4](https://henriquepain.com.br/renda-desigualdade-rs/analise.html#a4) testa a parte "industrial" (fatia maior da indústria se associa a renda mediana mais alta e, com menos força, a razão menor), mas a parte "pulverizada" não dá pra testar com estes dados. O mapa interativo deixa esse cruzamento explícito com um alternador entre as duas visões.

## Análises

A página [analise.html](https://henriquepain.com.br/renda-desigualdade-rs/analise.html) responde cinco perguntas sobre os 497 municípios, com gráficos interativos e todos os números calculados na hora a partir dos CSVs deste repositório:

1. **PIB alto não garante renda alta.** Correlação de Spearman de 0,39 entre PIB per capita e renda mediana; em escala log-log o PIB explica só 14% da variação da renda. 26 municípios estão no quarto mais alto de PIB per capita e no quarto mais baixo de renda mediana (Muitos Capões, Triunfo e Candiota à frente).
2. **A Metade Sul é mais pobre, mas não mais desigual.** Sudoeste e Sudeste Rio-grandense (44 municípios) têm renda mediana 13% menor que o resto do estado (Mann-Whitney, p < 0,001), mas a razão média/mediana não difere de forma detectável (1,36 vs. 1,33; p = 0,47). Os dois municípios de menor renda do estado ficam no Noroeste.
3. **Cidade pequena oscila mais.** O desvio-padrão da razão é 62% maior abaixo de 10 mil habitantes que entre 10 e 50 mil (teste de permutação, p < 0,001). Mas a evidência de que cidade pequena domine os extremos é fraca: 14 dos 20 extremos têm menos de 6 mil habitantes, contra 10,6 esperados (p = 0,09). A página tem um filtro de população mínima pro ranking.
4. **A composição da economia explica parte da concentração.** Em relação a serviços, mais administração pública e mais indústria se associam a razão menor (regressão com erros-padrão robustos, R² = 0,20); a indústria é o setor mais associado a renda mediana alta (Spearman 0,41).
5. **Cidade industrial: mais emprego formal, salário quase igual.** Fatia da indústria e empregos formais por habitante andam juntos (Spearman 0,73). O quarto mais industrial dos municípios tem 29 empregos formais por 100 habitantes, contra 11 no quarto menos industrial, mas o salário médio formal é praticamente o mesmo (R$ 2.869 vs. R$ 2.848; p = 0,55). No modelo com todos os setores e o tamanho da cidade, o que acompanha a renda mediana é o emprego formal (+10 empregos por 100 habitantes, +6,9% de renda), e trocar serviços por indústria se associa a razão menor. As tabelas do IBGE só trazem tamanho de empresa por município até 2006, então a análise não separa uma fábrica grande de várias médias.

Tudo é associação entre municípios, não causa. Limites e método completos estão no fim da própria página.

### Os 497 municípios

| Cidade | População (2026) | PIB per capita (R$) | Renda média (2022) | Renda mediana (2022) | Razão média/mediana |
|---|---|---|---|---|---|
| Rondinha | 5.078 | 44.843,64 | 2.559,50 | 1.333,33 | 1,92 |
| Tiradentes do Sul | 5.188 | 31.413,84 | 2.310,17 | 1.212,00 | 1,91 |
| Porto Alegre | 1.388.791 | 75.420,47 | 3.203,31 | 1.700,00 | 1,88 |
| Nova Ramada | 2.198 | 93.265,24 | 3.024,38 | 1.616,00 | 1,87 |
| Água Santa | 4.003 | 104.606,05 | 2.262,10 | 1.212,00 | 1,87 |
| Muliterno | 1.754 | 40.575,83 | 2.360,89 | 1.308,00 | 1,80 |
| Augusto Pestana | 7.303 | 48.019,58 | 2.387,12 | 1.356,00 | 1,76 |
| Boa Vista do Cadeado | 2.269 | 118.991,19 | 2.133,19 | 1.212,00 | 1,76 |
| Ronda Alta | 9.969 | 40.406,86 | 2.330,21 | 1.350,00 | 1,73 |
| Gentil | 1.784 | 85.345,29 | 2.888,72 | 1.687,50 | 1,71 |
| Taquaruçu do Sul | 3.192 | 59.002,82 | 2.332,95 | 1.366,67 | 1,71 |
| Coqueiros do Sul | 2.248 | 61.958,63 | 2.555,61 | 1.500,00 | 1,70 |
| Quinze de Novembro | 4.003 | 43.190,36 | 2.866,59 | 1.684,00 | 1,70 |
| São Valério do Sul | 2.593 | 26.163,13 | 1.050,48 | 620,25 | 1,69 |
| Itaara | 5.712 | 53.250,53 | 2.136,25 | 1.273,33 | 1,68 |
| União da Serra | 1.183 | 54.364,33 | 2.893,51 | 1.725,00 | 1,68 |
| Ipiranga do Sul | 1.748 | 70.009,15 | 2.773,20 | 1.659,00 | 1,67 |
| Caiçara | 4.931 | 32.426,28 | 2.241,76 | 1.341,33 | 1,67 |
| Santa Cecília do Sul | 1.710 | 53.427,49 | 2.248,46 | 1.356,00 | 1,66 |
| Pinhal Grande | 3.861 | 129.758,61 | 2.173,71 | 1.312,00 | 1,66 |
| Aceguá | 4.251 | 89.941,19 | 1.644,79 | 1.000,00 | 1,64 |
| Sede Nova | 2.750 | 44.580,00 | 1.991,34 | 1.212,00 | 1,64 |
| Santa Maria | 282.397 | 38.711,54 | 2.365,64 | 1.450,00 | 1,63 |
| Nicolau Vergueiro | 1.982 | 51.373,86 | 2.530,73 | 1.556,00 | 1,63 |
| Gaurama | 5.778 | 60.404,29 | 2.655,63 | 1.633,33 | 1,63 |
| Ibirubá | 22.106 | 77.265,99 | 2.923,72 | 1.800,00 | 1,62 |
| Campina das Missões | 5.999 | 33.967,49 | 2.384,95 | 1.474,67 | 1,62 |
| Pelotas | 336.150 | 37.129,02 | 1.959,93 | 1.212,00 | 1,62 |
| Severiano de Almeida | 3.463 | 41.123,88 | 2.745,42 | 1.700,00 | 1,61 |
| Chiapetta | 3.991 | 66.576,80 | 1.954,81 | 1.212,00 | 1,61 |
| Quatro Irmãos | 1.577 | 86.571,34 | 1.947,15 | 1.212,00 | 1,61 |
| São José do Ouro | 6.978 | 61.083,12 | 2.185,37 | 1.375,00 | 1,59 |
| São João da Urtiga | 4.546 | 43.612,19 | 2.185,87 | 1.378,00 | 1,59 |
| Faxinalzinho | 2.572 | 44.183,51 | 1.922,21 | 1.212,00 | 1,59 |
| Camargo | 3.060 | 200.142,16 | 2.309,51 | 1.460,57 | 1,58 |
| Benjamin Constant do Sul | 2.118 | 23.600,57 | 1.631,91 | 1.033,33 | 1,58 |
| Vista Alegre | 2.710 | 50.621,77 | 2.168,24 | 1.375,00 | 1,58 |
| Alegria | 3.705 | 36.733,87 | 2.205,90 | 1.400,00 | 1,58 |
| Ajuricaba | 6.843 | 56.046,32 | 2.357,63 | 1.500,00 | 1,57 |
| Doutor Maurício Cardoso | 4.533 | 50.356,50 | 2.041,23 | 1.300,00 | 1,57 |
| São Luiz Gonzaga | 35.865 | 47.762,16 | 1.901,46 | 1.212,00 | 1,57 |
| Jóia | 7.294 | 47.421,72 | 1.881,40 | 1.200,00 | 1,57 |
| Ponte Preta | 1.602 | 48.887,02 | 2.431,26 | 1.553,00 | 1,57 |
| Santo Augusto | 14.196 | 51.313,75 | 1.895,92 | 1.212,00 | 1,56 |
| Passo Fundo | 214.815 | 68.227,53 | 2.343,36 | 1.500,00 | 1,56 |
| Santiago | 50.336 | 36.985,28 | 2.097,02 | 1.342,40 | 1,56 |
| Fortaleza dos Valos | 4.569 | 72.422,41 | 2.095,83 | 1.350,00 | 1,55 |
| Novo Hamburgo | 235.801 | 50.621,42 | 2.138,48 | 1.380,00 | 1,55 |
| Capão da Canoa | 66.237 | 39.074,25 | 1.932,27 | 1.250,00 | 1,55 |
| Jaguari | 10.771 | 30.539,13 | 1.871,31 | 1.212,00 | 1,54 |
| Tramandaí | 56.432 | 27.993,43 | 1.871,57 | 1.212,50 | 1,54 |
| Constantina | 10.631 | 44.391,40 | 2.063,36 | 1.339,33 | 1,54 |
| Ubiretama | 2.025 | 36.309,14 | 1.986,68 | 1.290,00 | 1,54 |
| Cruz Alta | 60.453 | 72.781,93 | 1.995,66 | 1.300,00 | 1,54 |
| Santo Ângelo | 79.146 | 42.703,59 | 2.046,80 | 1.333,33 | 1,54 |
| Campos Borges | 3.695 | 28.422,19 | 1.859,44 | 1.212,00 | 1,53 |
| Barra do Rio Azul | 1.721 | 45.654,27 | 2.481,84 | 1.625,00 | 1,53 |
| Xangri-lá | 16.949 | 53.968,02 | 2.134,14 | 1.400,00 | 1,52 |
| Tupanciretã | 20.324 | 62.746,21 | 1.606,74 | 1.056,00 | 1,52 |
| Ibiaçá | 4.617 | 64.708,90 | 1.840,85 | 1.212,00 | 1,52 |
| Ijuí | 87.849 | 69.497,02 | 2.280,37 | 1.503,00 | 1,52 |
| Itapuca | 1.963 | 47.825,27 | 2.035,46 | 1.350,00 | 1,51 |
| Santo Cristo | 15.667 | 48.931,90 | 2.116,06 | 1.404,00 | 1,51 |
| Cândido Godói | 6.419 | 58.423,74 | 2.260,55 | 1.500,00 | 1,51 |
| Santo Expedito do Sul | 2.395 | 44.065,55 | 2.108,68 | 1.400,00 | 1,51 |
| Dois Lajeados | 3.156 | 52.598,86 | 1.823,90 | 1.212,00 | 1,50 |
| Crissiumal | 13.116 | 38.171,70 | 1.902,99 | 1.266,67 | 1,50 |
| Gramado | 41.706 | 85.499,21 | 2.622,73 | 1.750,00 | 1,50 |
| Canoas | 359.845 | 81.053,50 | 2.066,82 | 1.380,00 | 1,50 |
| Condor | 6.538 | 71.977,97 | 1.895,81 | 1.266,67 | 1,50 |
| Alpestre | 7.235 | 41.861,64 | 2.094,44 | 1.400,00 | 1,50 |
| Mariano Moro | 1.884 | 37.995,22 | 2.243,73 | 1.500,00 | 1,50 |
| São Domingos do Sul | 2.806 | 46.530,29 | 2.785,62 | 1.866,67 | 1,49 |
| Independência | 6.557 | 67.653,81 | 1.910,25 | 1.284,00 | 1,49 |
| São Jerônimo | 21.412 | 33.265,37 | 1.635,38 | 1.100,00 | 1,49 |
| Humaitá | 4.772 | 45.687,55 | 1.799,56 | 1.212,00 | 1,48 |
| Anta Gorda | 6.080 | 54.812,01 | 2.682,97 | 1.808,00 | 1,48 |
| Barracão | 4.915 | 61.040,69 | 1.797,57 | 1.212,00 | 1,48 |
| Charrua | 2.800 | 44.873,93 | 1.739,81 | 1.175,00 | 1,48 |
| Frederico Westphalen | 33.726 | 53.144,04 | 2.257,68 | 1.525,00 | 1,48 |
| Paulo Bento | 2.188 | 109.030,16 | 2.959,51 | 2.000,00 | 1,48 |
| São Leopoldo | 225.738 | 52.011,24 | 1.922,89 | 1.300,00 | 1,48 |
| Três Passos | 26.304 | 46.686,13 | 1.970,49 | 1.333,33 | 1,48 |
| Lagoa Vermelha | 28.622 | 56.186,26 | 1.855,38 | 1.256,00 | 1,48 |
| Sant'Ana do Livramento | 87.330 | 35.996,95 | 1.600,16 | 1.084,80 | 1,48 |
| Silveira Martins | 2.056 | 35.118,68 | 2.041,91 | 1.387,33 | 1,47 |
| Derrubadas | 2.793 | 42.098,46 | 1.783,00 | 1.212,00 | 1,47 |
| Sobradinho | 14.512 | 36.055,68 | 1.838,82 | 1.250,00 | 1,47 |
| Espumoso | 15.478 | 55.662,10 | 1.984,00 | 1.349,00 | 1,47 |
| Roque Gonzales | 6.692 | 59.287,66 | 1.796,07 | 1.222,40 | 1,47 |
| Torres | 43.346 | 42.345,98 | 2.080,13 | 1.416,67 | 1,47 |
| Vista Gaúcha | 2.843 | 33.153,71 | 2.018,17 | 1.375,00 | 1,47 |
| Faxinal do Soturno | 6.846 | 43.606,92 | 1.987,81 | 1.355,50 | 1,47 |
| São Martinho da Serra | 2.908 | 72.630,67 | 1.776,57 | 1.212,00 | 1,47 |
| Imbé | 28.029 | 27.217,03 | 1.774,31 | 1.212,00 | 1,46 |
| Caseiros | 3.064 | 57.819,19 | 1.774,11 | 1.212,00 | 1,46 |
| Lajeado do Bugre | 2.661 | 24.589,63 | 1.182,61 | 808,00 | 1,46 |
| Eugênio de Castro | 2.683 | 83.809,91 | 1.771,70 | 1.212,00 | 1,46 |
| Santa Cruz do Sul | 138.273 | 96.885,28 | 2.192,33 | 1.500,00 | 1,46 |
| Uruguaiana | 120.818 | 32.408,70 | 1.566,17 | 1.073,14 | 1,46 |
| Osório | 49.000 | 43.713,27 | 2.065,29 | 1.416,00 | 1,46 |
| Canela | 50.717 | 38.640,28 | 2.181,94 | 1.500,00 | 1,45 |
| Ibirapuitã | 3.788 | 49.657,34 | 1.762,16 | 1.212,00 | 1,45 |
| São Gabriel | 60.090 | 44.648,46 | 1.526,68 | 1.051,00 | 1,45 |
| Coronel Barros | 2.896 | 49.398,48 | 2.178,56 | 1.500,00 | 1,45 |
| Erebango | 3.122 | 48.701,47 | 1.452,05 | 1.000,00 | 1,45 |
| Santa Bárbara do Sul | 8.268 | 105.897,56 | 1.887,18 | 1.300,00 | 1,45 |
| Cachoeira do Sul | 82.222 | 41.001,64 | 1.757,97 | 1.212,00 | 1,45 |
| Marcelino Ramos | 4.382 | 43.937,70 | 2.070,86 | 1.428,00 | 1,45 |
| Pinheirinho do Vale | 4.638 | 30.307,46 | 1.757,29 | 1.212,00 | 1,45 |
| Vila Maria | 4.515 | 87.176,08 | 2.679,60 | 1.849,33 | 1,45 |
| São João do Polêsine | 2.708 | 43.564,62 | 2.028,21 | 1.400,00 | 1,45 |
| Trindade do Sul | 7.785 | 51.834,43 | 2.079,23 | 1.436,67 | 1,45 |
| Vacaria | 66.147 | 55.956,17 | 1.790,15 | 1.237,33 | 1,45 |
| Bagé | 121.929 | 36.207,69 | 1.662,21 | 1.150,00 | 1,45 |
| São Lourenço do Sul | 43.278 | 39.733,72 | 1.750,71 | 1.212,00 | 1,44 |
| Vespasiano Corrêa | 1.851 | 56.373,85 | 3.279,07 | 2.271,67 | 1,44 |
| Engenho Velho | 1.315 | 38.591,63 | 1.746,89 | 1.212,00 | 1,44 |
| Capão do Cipó | 3.187 | 69.069,97 | 1.746,81 | 1.212,00 | 1,44 |
| Saldanha Marinho | 2.619 | 64.944,25 | 1.873,11 | 1.300,00 | 1,44 |
| Cerro Grande | 2.428 | 25.509,88 | 1.824,62 | 1.266,67 | 1,44 |
| Carazinho | 63.671 | 60.594,24 | 2.049,08 | 1.423,00 | 1,44 |
| São Paulo das Missões | 5.943 | 36.127,04 | 1.792,43 | 1.250,00 | 1,43 |
| Montenegro | 66.353 | 79.264,49 | 1.897,77 | 1.325,00 | 1,43 |
| Tenente Portela | 14.820 | 41.492,17 | 1.735,10 | 1.212,00 | 1,43 |
| São Vicente do Sul | 8.257 | 56.907,59 | 1.507,10 | 1.053,00 | 1,43 |
| Victor Graeff | 2.825 | 83.452,74 | 2.384,33 | 1.666,67 | 1,43 |
| São Pedro do Butiá | 3.142 | 44.393,70 | 2.153,13 | 1.506,00 | 1,43 |
| Catuípe | 8.834 | 48.112,52 | 1.787,11 | 1.250,00 | 1,43 |
| Alecrim | 6.219 | 24.717,64 | 1.732,26 | 1.212,00 | 1,43 |
| Nova Bréscia | 3.104 | 49.604,70 | 2.582,36 | 1.808,00 | 1,43 |
| Santo Antônio do Palma | 2.134 | 52.682,76 | 2.000,81 | 1.401,00 | 1,43 |
| Pouso Novo | 1.771 | 32.695,65 | 1.783,78 | 1.250,00 | 1,43 |
| Lavras do Sul | 7.290 | 50.733,20 | 1.521,74 | 1.066,67 | 1,43 |
| São Borja | 61.311 | 41.597,56 | 1.568,58 | 1.100,00 | 1,43 |
| Ivorá | 1.962 | 27.498,47 | 1.960,11 | 1.375,00 | 1,43 |
| São Valentim | 3.320 | 37.613,86 | 1.963,67 | 1.378,00 | 1,43 |
| Ibiraiaras | 6.827 | 55.690,49 | 2.287,25 | 1.606,00 | 1,42 |
| Ilópolis | 4.245 | 38.845,70 | 2.139,37 | 1.503,00 | 1,42 |
| Eldorado do Sul | 41.013 | 63.967,30 | 1.573,59 | 1.106,00 | 1,42 |
| Cerro Largo | 14.015 | 57.581,66 | 1.996,14 | 1.403,00 | 1,42 |
| Getúlio Vargas | 16.956 | 51.896,67 | 2.249,90 | 1.583,33 | 1,42 |
| Dom Pedrito | 38.080 | 60.088,55 | 1.515,04 | 1.066,67 | 1,42 |
| Rodeio Bonito | 6.831 | 44.085,79 | 1.960,07 | 1.380,00 | 1,42 |
| Coqueiro Baixo | 1.308 | 42.821,87 | 2.430,83 | 1.712,00 | 1,42 |
| Ciríaco | 4.208 | 55.468,16 | 1.730,43 | 1.220,00 | 1,42 |
| Selbach | 5.223 | 54.912,89 | 2.458,17 | 1.733,33 | 1,42 |
| Sananduva | 16.770 | 52.352,83 | 1.943,31 | 1.370,67 | 1,42 |
| Sarandi | 23.374 | 61.079,02 | 1.850,64 | 1.306,00 | 1,42 |
| Júlio de Castilhos | 18.545 | 70.470,85 | 1.699,46 | 1.200,00 | 1,42 |
| Nova Candelária | 3.138 | 71.985,98 | 2.547,55 | 1.800,00 | 1,42 |
| Lajeado | 96.883 | 69.209,53 | 2.490,87 | 1.760,00 | 1,42 |
| Rosário do Sul | 37.673 | 39.771,53 | 1.627,08 | 1.150,00 | 1,41 |
| Novo Xingu | 1.677 | 40.394,16 | 2.118,70 | 1.500,00 | 1,41 |
| Veranópolis | 24.554 | 97.557,10 | 2.257,23 | 1.600,00 | 1,41 |
| Hulha Negra | 6.102 | 37.505,74 | 1.219,72 | 866,67 | 1,41 |
| Esteio | 78.143 | 51.170,12 | 1.899,78 | 1.350,00 | 1,41 |
| Nova Palma | 5.676 | 54.061,31 | 1.829,37 | 1.300,00 | 1,41 |
| Guabiju | 1.441 | 74.728,66 | 1.705,26 | 1.212,00 | 1,41 |
| Liberato Salzano | 4.845 | 31.490,40 | 1.705,05 | 1.212,00 | 1,41 |
| Vista Alegre do Prata | 1.624 | 47.024,01 | 2.249,69 | 1.600,00 | 1,41 |
| Tuparendi | 8.535 | 43.937,43 | 2.155,38 | 1.533,33 | 1,41 |
| Redentora | 9.931 | 20.904,64 | 851,69 | 606,00 | 1,41 |
| Dilermando de Aguiar | 2.856 | 71.057,07 | 1.705,85 | 1.215,00 | 1,40 |
| Boa Vista do Buricá | 7.129 | 49.740,78 | 1.976,81 | 1.408,00 | 1,40 |
| Cruzaltense | 1.650 | 63.603,03 | 1.965,07 | 1.400,00 | 1,40 |
| Erechim | 109.610 | 77.521,27 | 2.385,71 | 1.700,00 | 1,40 |
| Pontão | 3.345 | 81.308,82 | 1.695,82 | 1.212,00 | 1,40 |
| Caxias do Sul | 479.604 | 78.941,38 | 2.330,62 | 1.666,67 | 1,40 |
| Guarani das Missões | 7.547 | 39.186,83 | 1.956,16 | 1.400,00 | 1,40 |
| Alegrete | 74.285 | 41.758,47 | 1.653,21 | 1.183,33 | 1,40 |
| Itaqui | 36.811 | 56.204,37 | 1.442,82 | 1.033,33 | 1,40 |
| Cachoeirinha | 141.506 | 54.992,89 | 1.884,12 | 1.350,00 | 1,40 |
| Caibaté | 4.795 | 37.625,03 | 1.856,95 | 1.333,33 | 1,39 |
| Rio Grande | 198.935 | 70.911,00 | 1.671,01 | 1.200,00 | 1,39 |
| Tapera | 10.824 | 53.967,94 | 2.018,36 | 1.450,00 | 1,39 |
| Maçambará | 4.485 | 82.043,03 | 1.297,03 | 933,33 | 1,39 |
| Capão Bonito do Sul | 1.769 | 126.100,06 | 1.683,27 | 1.212,00 | 1,39 |
| Soledade | 30.958 | 42.407,20 | 1.773,11 | 1.278,00 | 1,39 |
| Chapada | 9.751 | 61.845,25 | 1.849,22 | 1.333,33 | 1,39 |
| Bom Progresso | 2.132 | 34.518,29 | 1.621,07 | 1.170,67 | 1,38 |
| Pedro Osório | 7.631 | 31.767,13 | 1.254,09 | 906,00 | 1,38 |
| Ivoti | 23.567 | 65.298,00 | 2.380,00 | 1.720,67 | 1,38 |
| Santo Antônio das Missões | 10.485 | 41.327,90 | 1.526,41 | 1.104,00 | 1,38 |
| Três Arroios | 2.636 | 50.944,99 | 2.492,19 | 1.803,00 | 1,38 |
| Três de Maio | 25.466 | 59.886,99 | 2.038,20 | 1.474,67 | 1,38 |
| Tapes | 14.919 | 42.502,18 | 1.449,76 | 1.050,00 | 1,38 |
| Santa Margarida do Sul | 2.661 | 104.588,50 | 1.610,73 | 1.166,67 | 1,38 |
| Porto Lucena | 4.413 | 29.225,47 | 1.673,28 | 1.212,00 | 1,38 |
| Cacique Doble | 4.692 | 32.826,51 | 1.246,35 | 903,00 | 1,38 |
| Paim Filho | 3.685 | 44.184,80 | 1.670,92 | 1.212,00 | 1,38 |
| Viadutos | 4.847 | 39.451,83 | 1.777,55 | 1.290,00 | 1,38 |
| Pejuçara | 3.817 | 76.783,86 | 1.691,27 | 1.228,00 | 1,38 |
| Nova Roma do Sul | 3.545 | 58.300,14 | 2.294,79 | 1.666,67 | 1,38 |
| Guaíba | 95.946 | 93.821,37 | 1.668,25 | 1.212,00 | 1,38 |
| Nonoai | 14.074 | 38.324,14 | 1.582,13 | 1.150,00 | 1,38 |
| Campo Bom | 64.720 | 69.974,61 | 1.991,18 | 1.450,00 | 1,37 |
| Santa Vitória do Palmar | 31.965 | 62.278,71 | 1.518,77 | 1.106,00 | 1,37 |
| São Francisco de Assis | 17.934 | 33.041,65 | 1.663,89 | 1.212,00 | 1,37 |
| Segredo | 6.098 | 29.794,36 | 1.663,32 | 1.212,00 | 1,37 |
| Salvador das Missões | 2.955 | 54.910,32 | 1.696,82 | 1.237,33 | 1,37 |
| Dezesseis de Novembro | 2.540 | 20.240,94 | 1.659,75 | 1.212,00 | 1,37 |
| Taquara | 54.353 | 33.407,08 | 1.711,54 | 1.250,00 | 1,37 |
| Lagoa dos Três Cantos | 1.781 | 45.965,19 | 2.326,25 | 1.700,00 | 1,37 |
| Nova Boa Vista | 2.089 | 65.957,87 | 2.487,62 | 1.818,00 | 1,37 |
| Marau | 46.750 | 82.844,93 | 2.256,96 | 1.650,00 | 1,37 |
| Coxilha | 2.718 | 128.537,16 | 1.655,79 | 1.212,00 | 1,37 |
| Pantano Grande | 10.443 | 55.215,36 | 1.438,55 | 1.053,00 | 1,37 |
| Barra do Quaraí | 4.340 | 76.633,64 | 1.229,26 | 900,00 | 1,37 |
| Campinas do Sul | 5.388 | 54.728,10 | 1.877,21 | 1.375,00 | 1,37 |
| Agudo | 16.347 | 47.724,48 | 1.720,07 | 1.260,00 | 1,37 |
| Jacutinga | 3.398 | 55.529,43 | 1.979,26 | 1.450,00 | 1,37 |
| Boa Vista das Missões | 1.968 | 88.008,13 | 1.653,55 | 1.212,00 | 1,36 |
| São Valentim do Sul | 2.255 | 37.630,60 | 1.652,84 | 1.212,00 | 1,36 |
| Estância Velha | 49.500 | 46.650,42 | 1.975,46 | 1.450,00 | 1,36 |
| Garruchos | 2.724 | 49.463,66 | 1.367,69 | 1.004,00 | 1,36 |
| Canudos do Vale | 1.686 | 39.711,15 | 1.812,70 | 1.333,33 | 1,36 |
| Boqueirão do Leão | 6.202 | 32.092,87 | 1.647,73 | 1.212,00 | 1,36 |
| Rio dos Índios | 2.866 | 40.704,82 | 1.646,66 | 1.212,00 | 1,36 |
| Gravataí | 275.432 | 56.440,64 | 1.696,73 | 1.250,00 | 1,36 |
| Novo Cabrais | 3.633 | 36.246,63 | 1.644,07 | 1.212,00 | 1,36 |
| Montauri | 1.530 | 48.191,50 | 2.821,46 | 2.080,67 | 1,36 |
| Viamão | 231.994 | 23.902,27 | 1.489,82 | 1.100,00 | 1,35 |
| Quaraí | 23.995 | 30.008,63 | 1.391,76 | 1.028,57 | 1,35 |
| Casca | 9.698 | 90.322,64 | 2.626,19 | 1.941,33 | 1,35 |
| Bom Jesus | 11.429 | 51.920,82 | 1.183,20 | 875,00 | 1,35 |
| Bozano | 2.195 | 54.407,74 | 1.638,05 | 1.212,00 | 1,35 |
| Vila Flores | 3.741 | 100.697,41 | 1.903,28 | 1.409,00 | 1,35 |
| Pinheiro Machado | 11.394 | 31.410,92 | 1.416,97 | 1.050,00 | 1,35 |
| São José do Sul | 2.443 | 45.646,34 | 1.684,96 | 1.250,00 | 1,35 |
| Santa Rosa | 79.489 | 56.993,50 | 2.122,58 | 1.575,00 | 1,35 |
| Novo Tiradentes | 2.187 | 33.540,47 | 1.617,01 | 1.200,00 | 1,35 |
| Nova Alvorada | 3.229 | 62.540,11 | 2.575,70 | 1.912,00 | 1,35 |
| Giruá | 16.273 | 62.524,92 | 1.632,65 | 1.212,00 | 1,35 |
| Marques de Souza | 4.050 | 33.949,38 | 1.825,90 | 1.356,00 | 1,35 |
| Miraguaí | 4.501 | 44.567,21 | 1.413,56 | 1.050,00 | 1,35 |
| Tucunduva | 5.646 | 40.942,61 | 1.823,72 | 1.356,00 | 1,34 |
| Arroio do Padre | 2.650 | 36.434,34 | 1.613,45 | 1.200,00 | 1,34 |
| Nova Esperança do Sul | 4.976 | 39.637,86 | 1.628,39 | 1.212,00 | 1,34 |
| Barão de Cotegipe | 7.320 | 44.367,35 | 2.068,99 | 1.540,50 | 1,34 |
| Rio Pardo | 35.641 | 35.016,39 | 1.477,03 | 1.100,00 | 1,34 |
| Planalto | 10.625 | 30.661,46 | 1.342,22 | 1.000,00 | 1,34 |
| Encantado | 23.521 | 60.006,89 | 2.213,18 | 1.650,00 | 1,34 |
| Caçapava do Sul | 33.501 | 35.097,52 | 1.519,48 | 1.133,33 | 1,34 |
| Alto Alegre | 1.837 | 39.434,95 | 1.652,45 | 1.233,33 | 1,34 |
| Pareci Novo | 4.441 | 35.859,94 | 1.816,63 | 1.356,00 | 1,34 |
| Charqueadas | 36.110 | 51.437,83 | 1.785,15 | 1.333,33 | 1,34 |
| Capivari do Sul | 4.080 | 97.893,38 | 1.622,38 | 1.212,00 | 1,34 |
| Venâncio Aires | 70.842 | 66.106,74 | 1.739,54 | 1.300,00 | 1,34 |
| Camaquã | 63.961 | 49.321,88 | 1.605,16 | 1.200,00 | 1,34 |
| Nova Araçá | 5.098 | 93.129,66 | 2.136,64 | 1.600,00 | 1,34 |
| Iraí | 7.631 | 33.519,20 | 1.572,85 | 1.178,67 | 1,33 |
| Palmeira das Missões | 34.227 | 49.911,59 | 1.578,86 | 1.183,33 | 1,33 |
| Doutor Ricardo | 1.924 | 46.623,70 | 2.045,38 | 1.533,33 | 1,33 |
| Santo Antônio da Patrulha | 44.431 | 49.038,53 | 1.614,13 | 1.212,00 | 1,33 |
| Colorado | 3.316 | 60.005,13 | 2.130,43 | 1.600,00 | 1,33 |
| São Sepé | 21.551 | 49.162,87 | 1.613,74 | 1.212,00 | 1,33 |
| Almirante Tamandaré do Sul | 2.007 | 111.194,32 | 2.128,82 | 1.600,00 | 1,33 |
| Butiá | 19.421 | 29.199,37 | 1.374,61 | 1.033,33 | 1,33 |
| Tunas | 3.732 | 25.254,56 | 1.340,45 | 1.008,00 | 1,33 |
| Brochier | 5.083 | 26.021,05 | 1.992,92 | 1.500,00 | 1,33 |
| Ernestina | 3.097 | 52.771,71 | 1.833,01 | 1.380,00 | 1,33 |
| Barra Funda | 2.557 | 65.460,31 | 1.991,52 | 1.500,00 | 1,33 |
| Dom Feliciano | 13.279 | 31.491,75 | 1.327,63 | 1.000,00 | 1,33 |
| Forquetinha | 2.441 | 26.428,92 | 1.608,56 | 1.212,00 | 1,33 |
| Morrinhos do Sul | 3.133 | 32.955,00 | 1.608,45 | 1.212,00 | 1,33 |
| Chuvisca | 4.682 | 34.902,82 | 1.608,16 | 1.212,00 | 1,33 |
| São Pedro do Sul | 15.863 | 31.885,71 | 1.606,44 | 1.212,00 | 1,33 |
| Mato Castelhano | 2.611 | 49.215,63 | 1.605,58 | 1.212,00 | 1,32 |
| Bento Gonçalves | 127.980 | 70.812,61 | 2.516,92 | 1.900,00 | 1,32 |
| Esmeralda | 3.264 | 111.452,51 | 1.412,83 | 1.066,67 | 1,32 |
| Salto do Jacuí | 10.357 | 57.441,44 | 1.561,65 | 1.180,00 | 1,32 |
| São Sebastião do Caí | 24.898 | 45.126,84 | 1.718,35 | 1.300,00 | 1,32 |
| Passa Sete | 4.024 | 35.938,87 | 1.266,84 | 960,00 | 1,32 |
| Turuçu | 3.488 | 46.251,72 | 1.599,23 | 1.212,00 | 1,32 |
| São José dos Ausentes | 4.295 | 41.251,92 | 1.066,14 | 808,00 | 1,32 |
| Jaguarão | 27.396 | 37.772,01 | 1.581,33 | 1.200,00 | 1,32 |
| Balneário Pinhal | 15.413 | 21.614,81 | 1.475,90 | 1.120,00 | 1,32 |
| Entre Rios do Sul | 2.727 | 76.901,72 | 1.596,55 | 1.212,00 | 1,32 |
| Vicente Dutra | 4.741 | 31.188,36 | 1.497,70 | 1.137,33 | 1,32 |
| Muçum | 4.692 | 58.261,51 | 2.114,86 | 1.606,00 | 1,32 |
| Manoel Viana | 6.915 | 43.867,25 | 1.491,49 | 1.133,33 | 1,32 |
| Feliz | 13.994 | 48.347,93 | 2.300,06 | 1.750,00 | 1,31 |
| David Canabarro | 4.400 | 47.018,18 | 1.785,56 | 1.359,00 | 1,31 |
| Santana da Boa Vista | 7.128 | 33.337,40 | 1.182,47 | 900,00 | 1,31 |
| Coronel Bicaco | 6.214 | 63.903,28 | 1.313,41 | 1.000,00 | 1,31 |
| Arroio do Sal | 11.419 | 30.973,55 | 1.638,58 | 1.250,00 | 1,31 |
| Braga | 3.322 | 32.943,71 | 1.343,57 | 1.025,00 | 1,31 |
| Colinas | 2.474 | 36.539,21 | 2.243,77 | 1.712,00 | 1,31 |
| Igrejinha | 34.777 | 76.375,97 | 1.769,21 | 1.350,00 | 1,31 |
| Tapejara | 25.257 | 76.169,60 | 1.867,41 | 1.425,00 | 1,31 |
| São Francisco de Paula | 22.388 | 53.693,14 | 1.572,34 | 1.200,00 | 1,31 |
| Travesseiro | 2.192 | 39.269,16 | 1.637,11 | 1.251,00 | 1,31 |
| Serafina Corrêa | 17.407 | 58.281,73 | 2.126,45 | 1.625,00 | 1,31 |
| Santo Antônio do Planalto | 2.138 | 77.945,28 | 1.912,78 | 1.462,00 | 1,31 |
| São Martinho | 5.587 | 54.580,10 | 1.810,54 | 1.384,00 | 1,31 |
| Vanini | 2.047 | 39.923,79 | 1.773,91 | 1.356,00 | 1,31 |
| Sapiranga | 77.935 | 59.973,75 | 1.641,28 | 1.256,00 | 1,31 |
| Canguçu | 50.968 | 35.817,14 | 1.501,90 | 1.150,00 | 1,31 |
| Nova Prata | 26.638 | 58.535,78 | 2.089,33 | 1.600,00 | 1,31 |
| Taquari | 25.963 | 43.282,56 | 1.630,78 | 1.250,00 | 1,30 |
| Flores da Cunha | 32.015 | 104.210,15 | 2.303,59 | 1.766,67 | 1,30 |
| Glorinha | 7.851 | 75.833,52 | 1.564,64 | 1.200,00 | 1,30 |
| Quevedos | 2.553 | 61.203,68 | 1.417,51 | 1.087,50 | 1,30 |
| Barros Cassal | 9.424 | 29.125,00 | 1.364,70 | 1.050,00 | 1,30 |
| Estrela Velha | 3.115 | 46.641,73 | 1.666,27 | 1.284,00 | 1,30 |
| Porto Xavier | 10.127 | 22.719,66 | 1.572,31 | 1.212,00 | 1,30 |
| Arambaré | 4.215 | 55.416,84 | 1.556,44 | 1.200,00 | 1,30 |
| Barra do Ribeiro | 12.476 | 46.573,74 | 1.523,42 | 1.175,00 | 1,30 |
| Horizontina | 19.252 | 94.953,77 | 2.203,71 | 1.700,00 | 1,30 |
| Nova Petrópolis | 23.934 | 46.110,89 | 2.219,28 | 1.712,50 | 1,30 |
| Encruzilhada do Sul | 24.275 | 49.002,18 | 1.425,04 | 1.100,00 | 1,30 |
| Paraí | 7.362 | 66.321,11 | 2.303,16 | 1.778,00 | 1,30 |
| Cristal | 7.455 | 40.312,54 | 1.456,88 | 1.125,00 | 1,30 |
| Aratiba | 6.618 | 179.089,91 | 2.353,81 | 1.818,00 | 1,29 |
| Protásio Alves | 2.070 | 45.100,48 | 2.219,02 | 1.715,00 | 1,29 |
| Seberi | 12.325 | 67.139,63 | 1.567,87 | 1.212,00 | 1,29 |
| São José do Herval | 1.931 | 28.842,05 | 1.379,43 | 1.066,67 | 1,29 |
| General Câmara | 7.743 | 30.228,34 | 1.484,84 | 1.150,00 | 1,29 |
| Maximiliano de Almeida | 4.251 | 37.541,28 | 1.564,17 | 1.212,00 | 1,29 |
| Palmitinho | 8.042 | 32.992,41 | 1.562,57 | 1.212,00 | 1,29 |
| Arvorezinha | 10.547 | 38.366,55 | 1.561,86 | 1.212,00 | 1,29 |
| Dois Irmãos das Missões | 2.132 | 58.985,46 | 1.288,19 | 1.000,00 | 1,29 |
| Linha Nova | 1.721 | 44.249,85 | 1.864,49 | 1.450,00 | 1,29 |
| Sério | 2.089 | 33.666,35 | 1.799,08 | 1.400,00 | 1,29 |
| Fagundes Varela | 2.620 | 72.461,07 | 2.086,70 | 1.624,80 | 1,28 |
| Cacequi | 11.299 | 50.165,77 | 1.367,34 | 1.066,00 | 1,28 |
| São Nicolau | 5.243 | 34.092,89 | 1.350,34 | 1.053,00 | 1,28 |
| Entre-Ijuís | 9.368 | 51.125,53 | 1.554,23 | 1.212,00 | 1,28 |
| Mata | 4.782 | 36.387,70 | 1.543,63 | 1.204,00 | 1,28 |
| Roca Sales | 10.646 | 58.858,82 | 1.866,11 | 1.456,00 | 1,28 |
| Estação | 5.685 | 69.986,28 | 1.792,35 | 1.400,00 | 1,28 |
| Lagoão | 5.421 | 27.627,93 | 1.280,03 | 1.000,00 | 1,28 |
| Poço das Antas | 2.224 | 45.312,05 | 1.915,28 | 1.496,50 | 1,28 |
| Três Palmeiras | 4.829 | 34.355,15 | 1.177,01 | 920,00 | 1,28 |
| Capitão | 2.994 | 29.582,16 | 1.761,46 | 1.378,00 | 1,28 |
| Mormaço | 2.796 | 36.584,05 | 1.549,13 | 1.212,00 | 1,28 |
| Nova Santa Rita | 30.190 | 106.968,63 | 1.533,62 | 1.200,00 | 1,28 |
| Machadinho | 5.867 | 44.468,21 | 1.501,06 | 1.175,00 | 1,28 |
| Rolante | 21.753 | 43.718,48 | 1.643,72 | 1.287,33 | 1,28 |
| Garibaldi | 35.563 | 100.257,06 | 2.487,48 | 1.950,00 | 1,28 |
| Palmares do Sul | 13.190 | 56.092,12 | 1.325,77 | 1.040,00 | 1,27 |
| Porto Vera Cruz | 1.582 | 30.577,12 | 1.544,81 | 1.212,00 | 1,27 |
| Pedras Altas | 2.099 | 82.349,69 | 1.529,35 | 1.200,00 | 1,27 |
| Barão do Triunfo | 5.972 | 23.852,48 | 1.185,44 | 931,00 | 1,27 |
| Arroio Grande | 17.879 | 54.002,35 | 1.360,17 | 1.068,50 | 1,27 |
| Amaral Ferrador | 5.384 | 32.328,01 | 1.018,29 | 800,00 | 1,27 |
| Cidreira | 17.584 | 23.141,26 | 1.526,55 | 1.200,00 | 1,27 |
| Pinto Bandeira | 2.785 | 33.441,29 | 2.510,66 | 1.975,00 | 1,27 |
| Carlos Barbosa | 31.586 | 120.783,89 | 2.626,72 | 2.066,67 | 1,27 |
| Pirapó | 2.255 | 31.936,14 | 1.342,02 | 1.056,00 | 1,27 |
| Panambi | 45.103 | 88.934,57 | 2.086,21 | 1.642,40 | 1,27 |
| Vale do Sol | 10.069 | 37.788,16 | 1.538,70 | 1.212,00 | 1,27 |
| Floriano Peixoto | 1.690 | 45.802,37 | 1.586,03 | 1.250,00 | 1,27 |
| Bom Retiro do Sul | 12.587 | 40.496,15 | 1.774,79 | 1.400,00 | 1,27 |
| Tupandi | 5.172 | 116.829,85 | 1.897,87 | 1.500,25 | 1,27 |
| Bossoroca | 5.978 | 41.912,01 | 1.390,70 | 1.100,00 | 1,26 |
| Ibarama | 3.787 | 27.850,28 | 1.515,91 | 1.200,00 | 1,26 |
| Herval | 6.302 | 31.638,05 | 1.225,78 | 970,67 | 1,26 |
| Teutônia | 34.024 | 58.880,53 | 1.891,48 | 1.500,00 | 1,26 |
| Boa Vista do Sul | 2.815 | 47.926,11 | 2.314,50 | 1.837,33 | 1,26 |
| Dois Irmãos | 31.805 | 82.990,82 | 2.188,04 | 1.737,33 | 1,26 |
| Maratá | 2.521 | 41.311,78 | 2.028,04 | 1.612,00 | 1,26 |
| Progresso | 5.423 | 33.472,80 | 1.524,47 | 1.212,00 | 1,26 |
| Sapucaia do Sul | 136.573 | 34.629,16 | 1.571,59 | 1.250,00 | 1,26 |
| Putinga | 3.809 | 40.367,03 | 1.838,13 | 1.462,00 | 1,26 |
| Mato Leitão | 5.001 | 58.997,00 | 1.637,84 | 1.303,00 | 1,26 |
| Três Cachoeiras | 11.224 | 33.213,03 | 1.632,48 | 1.300,00 | 1,26 |
| Barão | 6.496 | 71.260,93 | 2.268,93 | 1.808,00 | 1,25 |
| Capão do Leão | 27.416 | 31.150,50 | 1.171,22 | 933,33 | 1,25 |
| Imigrante | 3.149 | 187.512,23 | 2.396,68 | 1.912,00 | 1,25 |
| Arroio do Tigre | 12.290 | 38.465,34 | 1.519,14 | 1.212,00 | 1,25 |
| Parobé | 53.569 | 32.215,39 | 1.535,37 | 1.225,00 | 1,25 |
| Morro Redondo | 6.168 | 24.842,09 | 1.503,22 | 1.200,00 | 1,25 |
| Não-Me-Toque | 18.335 | 161.001,36 | 2.175,25 | 1.737,33 | 1,25 |
| Sertão Santana | 5.989 | 57.533,98 | 1.517,50 | 1.212,00 | 1,25 |
| Portão | 35.274 | 51.501,87 | 1.627,56 | 1.300,00 | 1,25 |
| Estrela | 33.263 | 71.458,17 | 2.031,92 | 1.625,00 | 1,25 |
| Sentinela do Sul | 5.424 | 33.166,85 | 1.250,16 | 1.000,00 | 1,25 |
| Três Coroas | 24.428 | 42.822,70 | 1.619,03 | 1.296,00 | 1,25 |
| Vera Cruz | 27.671 | 40.719,02 | 1.596,06 | 1.278,00 | 1,25 |
| Antônio Prado | 13.332 | 69.490,17 | 2.153,43 | 1.725,00 | 1,25 |
| Jari | 3.412 | 62.026,67 | 1.331,59 | 1.066,67 | 1,25 |
| Candiota | 11.012 | 154.321,10 | 1.372,47 | 1.100,00 | 1,25 |
| Cambará do Sul | 6.490 | 42.424,04 | 1.511,60 | 1.212,00 | 1,25 |
| Harmonia | 5.535 | 55.454,56 | 2.119,47 | 1.700,00 | 1,25 |
| Jaboticaba | 3.847 | 27.752,27 | 1.329,75 | 1.066,67 | 1,25 |
| Maquiné | 7.593 | 30.126,17 | 1.494,90 | 1.200,00 | 1,25 |
| André da Rocha | 1.156 | 96.897,06 | 1.705,55 | 1.369,60 | 1,25 |
| Alvorada | 194.061 | 21.281,63 | 1.332,84 | 1.070,67 | 1,24 |
| Tabaí | 4.569 | 38.576,06 | 1.576,83 | 1.266,67 | 1,24 |
| Cerro Branco | 3.859 | 27.007,00 | 1.507,25 | 1.212,00 | 1,24 |
| Gramado Xavier | 3.350 | 37.098,51 | 1.202,09 | 966,67 | 1,24 |
| Santa Clara do Sul | 7.080 | 60.415,82 | 1.832,22 | 1.474,67 | 1,24 |
| Chuí | 6.409 | 81.504,13 | 1.448,23 | 1.166,67 | 1,24 |
| Arroio dos Ratos | 14.934 | 27.118,32 | 1.504,33 | 1.212,00 | 1,24 |
| Piratini | 17.770 | 41.888,63 | 1.240,96 | 1.000,00 | 1,24 |
| Nova Bassano | 9.867 | 77.537,04 | 2.046,80 | 1.650,00 | 1,24 |
| Guaporé | 26.168 | 48.323,79 | 2.065,92 | 1.666,67 | 1,24 |
| Mostardas | 12.347 | 40.037,34 | 1.246,83 | 1.006,00 | 1,24 |
| Terra de Areia | 10.575 | 32.394,33 | 1.502,13 | 1.212,00 | 1,24 |
| Lagoa Bonita do Sul | 2.283 | 36.891,81 | 1.502,05 | 1.212,00 | 1,24 |
| Riozinho | 4.574 | 36.242,24 | 1.519,68 | 1.226,67 | 1,24 |
| Ametista do Sul | 7.813 | 26.043,52 | 1.500,41 | 1.212,00 | 1,24 |
| Fazenda Vilanova | 4.405 | 33.091,03 | 1.500,24 | 1.212,00 | 1,24 |
| São Miguel das Missões | 7.193 | 71.900,74 | 1.484,86 | 1.200,00 | 1,24 |
| Arroio do Meio | 22.524 | 86.269,67 | 2.120,87 | 1.714,00 | 1,24 |
| Cerro Grande do Sul | 9.333 | 26.906,68 | 1.300,87 | 1.053,00 | 1,24 |
| Triunfo | 28.435 | 266.268,16 | 1.481,51 | 1.200,00 | 1,23 |
| São José do Norte | 26.248 | 48.516,61 | 1.183,51 | 958,86 | 1,23 |
| Picada Café | 5.473 | 71.889,64 | 2.056,94 | 1.666,67 | 1,23 |
| Cotiporã | 3.926 | 52.241,98 | 2.003,46 | 1.625,00 | 1,23 |
| Passo do Sobrado | 6.155 | 45.795,45 | 1.493,09 | 1.212,00 | 1,23 |
| Jaquirana | 3.751 | 27.142,10 | 1.058,77 | 860,00 | 1,23 |
| São José do Inhacorá | 2.466 | 86.819,55 | 1.809,63 | 1.470,67 | 1,23 |
| Cerrito | 5.909 | 22.197,66 | 1.229,98 | 1.000,00 | 1,23 |
| Erval Seco | 6.891 | 43.507,62 | 1.414,36 | 1.150,00 | 1,23 |
| Cruzeiro do Sul | 12.574 | 54.536,82 | 1.693,59 | 1.380,00 | 1,23 |
| Fontoura Xavier | 9.710 | 26.827,50 | 1.460,29 | 1.190,00 | 1,23 |
| Sertão | 5.630 | 69.185,44 | 1.226,99 | 1.000,00 | 1,23 |
| Herveiras | 2.604 | 33.962,75 | 1.484,10 | 1.210,00 | 1,23 |
| Restinga Sêca | 15.205 | 42.303,85 | 1.470,95 | 1.200,00 | 1,23 |
| Minas do Leão | 7.661 | 37.992,56 | 1.237,25 | 1.009,67 | 1,23 |
| Tio Hugo | 3.363 | 51.608,39 | 1.671,90 | 1.366,67 | 1,22 |
| Senador Salgado Filho | 2.725 | 34.272,66 | 1.464,59 | 1.200,00 | 1,22 |
| Unistalda | 2.047 | 34.703,47 | 1.306,67 | 1.070,67 | 1,22 |
| Pinhal da Serra | 2.300 | 108.267,83 | 1.382,28 | 1.133,33 | 1,22 |
| Carlos Gomes | 1.384 | 44.626,45 | 1.475,20 | 1.212,00 | 1,22 |
| Muitos Capões | 2.937 | 323.562,14 | 1.418,99 | 1.166,67 | 1,22 |
| Vila Nova do Sul | 3.932 | 55.314,85 | 1.344,10 | 1.106,00 | 1,22 |
| Monte Alegre dos Campos | 3.251 | 36.004,61 | 1.166,56 | 960,00 | 1,22 |
| Coronel Pilar | 1.637 | 35.524,13 | 2.882,39 | 2.380,00 | 1,21 |
| São Pedro das Missões | 1.790 | 40.732,40 | 1.178,39 | 974,67 | 1,21 |
| Farroupilha | 72.553 | 68.372,38 | 2.099,90 | 1.737,33 | 1,21 |
| Jacuizinho | 2.066 | 60.574,06 | 1.148,00 | 952,33 | 1,21 |
| Dona Francisca | 3.133 | 35.817,43 | 1.460,43 | 1.212,00 | 1,20 |
| Itatiba do Sul | 3.240 | 26.269,44 | 1.459,71 | 1.212,00 | 1,20 |
| Novo Barreiro | 4.375 | 27.500,11 | 1.322,87 | 1.100,00 | 1,20 |
| Ipê | 5.490 | 71.570,49 | 1.802,03 | 1.500,00 | 1,20 |
| Monte Belo do Sul | 2.608 | 48.625,77 | 1.921,88 | 1.600,00 | 1,20 |
| Campo Novo | 5.063 | 56.745,41 | 1.441,24 | 1.200,00 | 1,20 |
| Vila Lângaro | 2.121 | 73.206,51 | 1.454,41 | 1.212,00 | 1,20 |
| São Vendelino | 2.309 | 45.608,92 | 2.313,19 | 1.928,00 | 1,20 |
| Toropi | 2.594 | 31.728,60 | 1.452,65 | 1.212,00 | 1,20 |
| Formigueiro | 6.527 | 40.327,26 | 1.436,99 | 1.200,00 | 1,20 |
| Áurea | 3.458 | 51.404,28 | 1.517,58 | 1.268,00 | 1,20 |
| Santa Maria do Herval | 6.486 | 41.859,54 | 1.764,69 | 1.475,00 | 1,20 |
| Esperança do Sul | 3.293 | 30.776,19 | 1.449,92 | 1.212,00 | 1,20 |
| Sete de Setembro | 1.881 | 41.034,56 | 1.435,27 | 1.200,00 | 1,20 |
| Erval Grande | 5.027 | 32.160,73 | 1.448,46 | 1.212,00 | 1,20 |
| Paverama | 8.146 | 36.982,81 | 1.447,12 | 1.212,00 | 1,19 |
| Salvador do Sul | 7.184 | 55.071,83 | 1.967,63 | 1.650,00 | 1,19 |
| Westfália | 3.223 | 72.813,53 | 2.321,97 | 1.950,00 | 1,19 |
| Nova Hartz | 20.559 | 51.284,69 | 1.487,48 | 1.250,00 | 1,19 |
| São Pedro da Serra | 3.618 | 33.900,22 | 1.942,46 | 1.633,33 | 1,19 |
| Mariana Pimentel | 4.002 | 29.432,03 | 1.441,03 | 1.212,00 | 1,19 |
| Pinhal | 3.039 | 50.716,35 | 1.426,23 | 1.200,00 | 1,19 |
| São Jorge | 2.976 | 38.022,18 | 1.677,22 | 1.415,00 | 1,19 |
| Caraá | 7.555 | 20.936,33 | 1.436,47 | 1.212,00 | 1,19 |
| Santa Tereza | 1.529 | 35.148,46 | 2.366,65 | 2.000,00 | 1,18 |
| Bom Princípio | 13.665 | 69.595,24 | 2.002,51 | 1.693,00 | 1,18 |
| Barra do Guarita | 3.231 | 19.520,89 | 1.418,41 | 1.200,00 | 1,18 |
| Tupanci do Sul | 1.396 | 57.161,89 | 1.414,83 | 1.200,00 | 1,18 |
| Morro Reuter | 6.167 | 49.301,12 | 1.806,64 | 1.533,33 | 1,18 |
| Presidente Lucena | 3.166 | 117.414,40 | 1.581,99 | 1.350,00 | 1,17 |
| Capela de Santana | 11.424 | 27.656,43 | 1.406,12 | 1.200,00 | 1,17 |
| Cristal do Sul | 2.745 | 35.987,98 | 1.402,30 | 1.200,00 | 1,17 |
| Vitória das Missões | 3.316 | 26.860,98 | 1.414,14 | 1.212,00 | 1,17 |
| Rolador | 2.330 | 39.229,61 | 1.225,08 | 1.050,00 | 1,17 |
| Lindolfo Collor | 6.420 | 55.001,40 | 1.516,47 | 1.300,00 | 1,17 |
| Três Forquilhas | 2.813 | 28.153,93 | 1.413,66 | 1.212,00 | 1,17 |
| São José das Missões | 2.399 | 31.797,00 | 1.309,27 | 1.125,00 | 1,16 |
| Inhacorá | 2.047 | 37.320,96 | 1.245,23 | 1.070,67 | 1,16 |
| São Marcos | 21.549 | 69.087,06 | 1.695,70 | 1.462,00 | 1,16 |
| Boa Vista do Incra | 2.314 | 85.133,10 | 1.302,75 | 1.125,00 | 1,16 |
| Vale Real | 6.223 | 47.901,49 | 1.927,06 | 1.666,67 | 1,16 |
| Candelária | 29.775 | 41.466,90 | 1.375,38 | 1.200,00 | 1,15 |
| Alto Feliz | 3.145 | 64.601,27 | 1.814,97 | 1.586,67 | 1,14 |
| Campestre da Serra | 3.311 | 71.519,78 | 1.371,16 | 1.200,00 | 1,14 |
| Nova Pádua | 2.389 | 48.507,33 | 2.241,70 | 1.962,00 | 1,14 |
| São José do Hortêncio | 4.555 | 32.743,36 | 1.834,47 | 1.608,00 | 1,14 |
| Itacurubi | 3.038 | 37.637,26 | 1.298,07 | 1.141,33 | 1,14 |
| Centenário | 2.777 | 44.417,36 | 1.378,30 | 1.212,00 | 1,14 |
| Sagrada Família | 2.528 | 26.543,51 | 1.376,32 | 1.212,00 | 1,14 |
| Dom Pedro de Alcântara | 2.617 | 31.966,37 | 1.374,70 | 1.212,00 | 1,13 |
| Porto Mauá | 2.173 | 36.611,60 | 1.373,97 | 1.212,00 | 1,13 |
| Gramado dos Loureiros | 2.047 | 42.788,96 | 1.252,53 | 1.106,00 | 1,13 |
| Tavares | 5.319 | 25.554,43 | 1.361,72 | 1.204,00 | 1,13 |
| Relvado | 1.825 | 41.423,01 | 1.810,47 | 1.606,00 | 1,13 |
| Araricá | 8.831 | 36.570,60 | 1.362,38 | 1.212,00 | 1,12 |
| Mato Queimado | 1.833 | 33.632,30 | 1.352,71 | 1.204,00 | 1,12 |
| Paraíso do Sul | 6.620 | 34.748,34 | 1.115,75 | 1.000,00 | 1,12 |
| Itati | 2.696 | 38.383,90 | 1.327,12 | 1.200,00 | 1,11 |
| Sinimbu | 8.684 | 28.589,01 | 1.313,34 | 1.200,00 | 1,09 |
| Vale Verde | 3.213 | 48.820,42 | 1.263,82 | 1.166,67 | 1,08 |
| Mampituba | 3.203 | 31.601,62 | 1.297,67 | 1.200,00 | 1,08 |
| Novo Machado | 3.238 | 43.514,21 | 1.276,42 | 1.200,00 | 1,06 |

## Por que isso importa

PIB per capita é uma média: soma tudo que o município produz e divide pela população. Um punhado de empresas grandes (ou, no limite, alguns bilionários) empurra essa média pra cima sem que o trabalhador médio veja um centavo a mais no salário.

A razão entre renda média e renda mediana ataca o mesmo problema por outro ângulo, agora olhando pra dentro do próprio domicílio: quando a média está bem acima da mediana, é sinal de que uma minoria puxa o valor médio pra cima enquanto a maioria ganha menos que ele. Quanto mais perto de 1,0, mais parecida é a renda entre os moradores. Nas 4 cidades do Planalto Médio o Gini de 2010, mesmo defasado, apontou na mesma direção que essa razão calculada com dado de 2022, o que é um bom sinal de que o padrão é real e não um artefato de um único indicador.

## Fontes e metodologia

| Indicador | Fonte | Ano | Cobertura |
|---|---|---|---|
| População estimada | IBGE, SIDRA (tabela [6579](https://sidra.ibge.gov.br/tabela/6579)) | 2026 | Todos os municípios |
| PIB per capita | Calculado: PIB dos Municípios (SIDRA, tabela [5938](https://sidra.ibge.gov.br/tabela/5938)) ÷ população estimada | 2023 | Todos os municípios |
| Renda domiciliar per capita, média e mediana | IBGE, Censo Demográfico 2022 (SIDRA, tabela [10295](https://sidra.ibge.gov.br/tabela/10295)) | 2022 | Todos os municípios |
| Mesorregião e microrregião | IBGE, [API de localidades](https://servicodados.ibge.gov.br/api/v1/localidades/estados/43/municipios) (`data/regioes.csv`) | vigente | Todos os municípios |
| Valor adicionado bruto por setor (agropecuária, indústria, serviços, administração pública) | IBGE, PIB dos Municípios (SIDRA, tabela [5938](https://sidra.ibge.gov.br/tabela/5938), variáveis 498, 513, 517, 6575 e 525), via [API de agregados](https://servicodados.ibge.gov.br/api/v3/agregados) (`data/vab_setores.csv`) | soma 2019 a 2021 | Todos os municípios |
| Unidades locais, pessoal ocupado, empregados formais e salário médio mensal | IBGE, Cadastro Central de Empresas (SIDRA, tabela [9509](https://sidra.ibge.gov.br/tabela/9509)), via API de agregados (`data/cempre.csv`) | 2022 e 2023 | Todos os municípios |
| Salário médio mensal (trabalhadores formais) | IBGE Cidades, Cadastro Central de Empresas | 2023 | Só as 4 cidades originais do Planalto Médio |
| Índice de Gini | Atlas do Desenvolvimento Humano (PNUD, Ipea, FJP), Censo Demográfico | 2010 | Só as 4 cidades originais do Planalto Médio |

**Por que Gini e salário médio só aparecem pras 4 cidades originais no `cidades.csv`**: o Gini municipal do Atlas Brasil só existe por página individual (e o do Censo 2022 ainda não saiu por município). O salário médio dos trabalhadores formais, por outro lado, **existe em lote pros 497 municípios** no SIDRA (tabela [9509](https://sidra.ibge.gov.br/tabela/9509), 2022 a 2024). Uma versão anterior deste README dizia o contrário; estava errado. O salário médio dos 497 está agora em `data/cempre.csv` e é usado na Análise 5. PIB per capita e renda 2022 têm tabelas SIDRA que aceitam uma lista de códigos de município numa chamada só, por isso são a base do dataset completo.

**Composição setorial (`vab_setores.csv`)**: nessa tabela do IBGE a abertura do valor adicionado por setor só está publicada até 2021 (2022 e 2023 trazem só o PIB total). Por isso o projeto usa a soma de 2019 a 2021, que suaviza um ano atípico de safra em município pequeno. As quatro fatias somam o total em todos os 497 municípios (diferença máxima de 0,0015%, arredondamento). O endpoint `apisidra.ibge.gov.br` passou a responder com um desafio anti-bot durante este trabalho; os dados foram obtidos pela API de agregados do IBGE (`servicodados.ibge.gov.br`), que serve as mesmas tabelas.

**PIB per capita**: o SIDRA não publica um "PIB per capita por município" pronto — o valor exibido no IBGE Cidades é calculado internamente pelo IBGE dividindo o PIB total (tabela 5938) pela população do ano de referência. Este projeto reproduz esse cálculo usando a população estimada mais recente (2026) como denominador, o que gera uma pequena diferença frente ao número oficial do IBGE Cidades nas 4 cidades originais (por exemplo, Passo Fundo: R$ 68.227,53 oficial vs. ~R$ 65.494 recalculado) — por isso essas 4 cidades mantêm o valor oficial do IBGE Cidades na tabela, e as demais 493 usam o valor calculado (coluna `pib_per_capita_fonte` no CSV indica qual é qual).

## Limitação conhecida

O Índice de Gini municipal só existe calculado até o **Censo 2010**. O Censo 2022 já divulgou o Gini nacional e estadual (tabela SIDRA [10301](https://sidra.ibge.gov.br/tabela/10301)), mas esse recálculo em nível de município ainda não foi publicado (situação em setembro de 2026, quase 4 anos depois do Censo). Por isso este projeto usa a razão entre renda média e mediana (2022, nível de município) como proxy de concentração de renda mais atual e com cobertura completa, com o Gini de 2010 como referência histórica complementar nas 4 cidades onde ele foi levantado.

**Volatilidade em município pequeno**: a razão média/mediana vem de uma amostra do Censo, não de um censo completo de renda. Em município grande (Porto Alegre, Pelotas, Caxias do Sul), a amostra é grande o bastante pra a razão ser um retrato estável da distribuição de renda. Em município de poucos milhares de habitantes, a amostra é pequena, e poucos domicílios com renda atípica podem deslocar bastante o valor. Os dados são compatíveis com isso: o desvio-padrão da razão é 62% maior abaixo de 10 mil habitantes que entre 10 e 50 mil. Mas os dados sozinhos não separam ruído de amostra de diferenças reais entre economias pequenas, e a presença de cidades pequenas nos extremos do ranking (Rondinha, Tiradentes do Sul, Novo Machado, Mampituba) é só fracamente maior que o acaso sugeriria (14 dos 20 extremos têm menos de 6 mil habitantes, contra 10,6 esperados; p = 0,09). Pra comparações mais robustas, as cidades maiores são a referência mais confiável, e a [Análise 3](https://henriquepain.com.br/renda-desigualdade-rs/analise.html#a3) tem um filtro de população mínima pro ranking.

## Mapa interativo

`mapa.html` mostra os 497 municípios do Rio Grande do Sul (contorno oficial via [API de malhas do IBGE](https://servicodados.ibge.gov.br/api/docs/malhas)) — cobertura completa do estado. Sem tile de base (sem rios, estradas ou rótulos) — só os limites dos municípios sobre fundo escuro, com o contorno do estado destacado. Passar o mouse sobre uma cidade abre um popup com os indicadores disponíveis.

Um alternador na legenda troca entre duas visões: **concentração** (razão renda média/mediana) e **nível de renda** (renda mediana), pra deixar claro que são eixos independentes — uma cidade pode aparecer escura em um modo e clara no outro.

Pra abrir localmente: como o navegador bloqueia `fetch` de arquivo local por CORS, sirva a pasta com qualquer servidor estático (ex.: `npx serve .` ou `python -m http.server`) e acesse `mapa.html`. Publicado via GitHub Pages, funciona direto.

## Estrutura

```
index.html                   página do projeto (achado, tabela, fontes)
mapa.html                    mapa interativo (Leaflet)
analise.html                 quatro análises com gráficos (números calculados no navegador a partir dos CSVs)
data/cidades.csv             dataset consolidado, uma linha por município
data/regioes.csv             mesorregião, microrregião e região intermediária de cada município
data/vab_setores.csv         valor adicionado por setor (soma 2019 a 2021) e participação de cada setor
data/cempre.csv              empregos formais e salário médio por município (Cadastro Central de Empresas, 2022 e 2023)
data/rs_municipios.geojson   contorno dos municípios do RS (IBGE, malhas territoriais)
data/rs_estado.geojson       contorno do estado do RS (usado no efeito de foco do mapa)
```

## Próximos passos

- [x] ~~Aluguel/custo de imóvel por cidade via scraping~~: testado em OLX e VivaReal, sem inventário suficiente pra cidade pequena (0-1 anúncios). Mercado de aluguel em cidade pequena não é anunciado online nessa região, então essa via foi descartada.
- [x] ~~Visualização interativa~~: mapa com hover em `mapa.html`
- [x] ~~Expandir pra cobertura completa do RS~~: os 497 municípios do estado, sem exceção
- [x] ~~Deixar claro que concentração ≠ nível de renda~~: alternador de visão no mapa (razão vs. renda mediana)
- [x] ~~Análises além do mapa~~: PIB vs. renda, Metade Sul vs. resto, ruído em cidade pequena, composição setorial e emprego formal (`analise.html`)
- [ ] Tamanho dos estabelecimentos por município via RAIS, pra separar uma fábrica grande de muitas empresas médias
- [ ] Recortes regionais oficiais mais finos (COREDEs) pra comparar regiões do estado, hoje só as 7 mesorregiões do IBGE
- [ ] Separar ruído de amostra de diferença real na razão, se o IBGE publicar o erro amostral por município
- [ ] Indicadores de qualidade de vida que cobrem todo município (saneamento, mortalidade infantil, IDEB) como eixo complementar
- [ ] Atualizar quando o Gini do Censo 2022 for publicado por município

## Licença

Projeto de portfólio / uso educacional. Dados públicos, sempre com fonte creditada.
