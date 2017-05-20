# Escola Superior de Agricultura “Luiz de Queiroz” 
# Programa de Pós graduação em Genética e Melhoramento de Plantas
## Biometria de Marcadores Genéticos

Alunos:
- Emanoel Martins
- Gabriel Gesteira
- Jackeline Borba
- Pedro Barbosa

## Mapa Genético - _Mimulus guttatus_

  Um mapa de população F2 proveniente do cruzamento entre Mimulus guttatus e M. nasutus foi construído por Fishman et. al e publicado na revista Genetics em 2001. Sabendo que mais locos foram genotipados após a construção deste mapa, o objetivo do nosso trabalho foi refazer o mapa para incluir as informações dos novos marcadores. Para isso utilizou-se conjunto de dados completo, contendo os marcadores antigos e os novos, e considerando as informações já disponíveis no artigo.  Os novos marcadores são mais informativos que os antigos, apresentando especialmente segregação 1:2:1 (codominantes), o que auxilia na construção de um mapa mais preciso pela abordagem multiponto. Para construir o mapa final utilizou-se o software Onemap e foram necessárias três etapas, que estão sintetizadas abaixo, juntamente com os respectivos códigos e funções.

## Primeira Tentativa

Os grupos de ligação foram formados considerando todos os marcadores e LOD sugerido, mantendo a frequência de recombinação 0,5. Seguindo esses critérios foram obtidos 10 grupos de ligação. Contudo, houve necessidade de manipular os grupos de ligação para coerência com as informações prévias divulgadas no artigo.

[**Clique aqui**](https://gabrielgesteira.github.io/Mapa-Mimulus/mapmimulus_1tentativa.html) para visualizar o script e os resultados obtidos com a análise.

## Segunda Tentativa

Ao visualizar os heatmaps podemos notar que os grupos 1, 3 e 4 apresentaram evidências para ser separados em outros grupos independentes. Os grupos 1 e 3 foram subdivididos em grupos menores, cada um originando 3 grupos. Para separar o grupo 1 utilizou-se LOD=6 e rf=0.25. Para separar o grupo 3 utilizou-se LOD=5.45 e rf=0.2. Entretanto, não foi possível separar o grupo 4,  mesmo reduzindo consideravelmente a frequência de recombinação. Para este grupo em particular optou-se por remover os marcadores que apresentaram distorções, como pode ser visto através do heatmap. 
Dessa forma, obtemos um total de 14 mapas, semelhante ao que foi obtido por Fishman et. al (2011). Após divisão destes grupos, eles foram reorganizados para que cada um deles estivesse em acordo com a sequência definida por Fischman, ou seja, G1novo=G1artigo, G2novo=G2artigo, e assim por diante. Então se verificou se os mesmos marcadores presentes em cada grupo formado estão no mesmo grupo do artigo, manipulando um a um quando necessário.

[**Clique aqui**](https://gabrielgesteira.github.io/Mapa-Mimulus/mapmimulus_2tentativa.html) para visualizar o script e os resultados obtidos com a análise.

## Terceira Tentativa

Após eliminar todos os marcadores incoerente, gerou-se o mapa final no Onemap e também com o auxílio do software Mapchart. Os marcadores em vermelho correspondem aos marcadores presentes tanto no mapa anterior quanto no mapa novo e os sublinhados são os codominantes.

[**Clique aqui**](https://gabrielgesteira.github.io/Mapa-Mimulus/mapmimulus_3tentativa.html) para visualizar o script e os resultados obtidos com a análise.

## Material e Métodos

Um mapa genético proveniente do cruzamento entre Mimulus guttatus e M. nasutus foi construído por Fishman et. al (2001) e atualizado com posterior informação de novos marcadores. O novo mapa de ligação foi construído com o auxílio do software Onemap versão em desenvolvimento (Margarido et. al) e RStudio versão 3.4. Um total de 287 indivíduos de uma população F2 e 418 marcadores foram utilizados para análise. Fishman et. al (2001) construiu o mapa inicial utilizando informação de 255 marcadores e o software MAPMAKER 3.0. Dentre os marcadores, 213 são codominantes e 205 dominantes. Para construção do mapa final foram necessárias algumas etapas de construção dos grupos de ligação, ordenamento dos marcadores dentro de cada grupo e posterior realocação para equivalência ao que foi publicado previamente. Dentro do pacote Onemap utilizou-se função de mapeamento “Kosambi” e funções compare, Rapid Chain Delineation e try embutidos na função order_seq(), juntamente com o algoritmo Ripple. No total, 19 marcadores foram descartados porque não apresentaram evidência de ligação, e o mapa final contém 14 grupos, semelhante ao publicado anteriormente. Este mapa foi construído com o auxílio do software MapChart.


## Material and Methods

A genetic linkage map of an interspecific crossing between Mimulus guttatus and M. nasutus was constructed by Fishman et. al (2001) and updated with posterior information of new markers. The new linkage map was built using the program Onemap® version in development (Margarido et. al) and Rstudio® version 3.4. A total of 287 genotyped individuals of an F2 population and 418 markers were analyzed. Fishman et. al (2001) had constructed the prior map with 255 markers and using the program MAPMAKER 3.0. Among these markers, 213 were codominants and 205 dominants. In order to build the final map several rounds of mapping, grouping and ordering within each linkage group were necessary, and relocation of markers to correspond with was published before. Within the Onemap package, the mapping function chose was Kosambi, and the functions compare, Rapid Chain Delineation and try, through the order_seq() command, which automate the process of mapping a sequence of markers, combining compare and try.seq functions. The algorithm Ripple was used to check for plausible alternative orders. A total of 29 markers were discarded and the final map has 14 linkage groups, as well as the map published before. This final map figure was built using the program MapChart ®.


## Referências

Fishman, L., A. J. Kelly, E. Morgan and J. H. Wilis, 2001 A genetic map in the Mimulus guttatus species complex reveals transmission ratio distortion due to heterospecific interactions. Genetics 159: 1701-1716.

Margarido, G. R. A., A. P. Souza and A. A. F. Garcia, 2007 OneMap: software for genetic mapping in outcrossing species. Hereditas 144: 78-79.

R Core Team (2014). R: A Language and Environment for Statistical Computing. R Foundation for Statistical Computing, Vienna, Austria. URL http://www.R-project.org/.

Voorrips, R.E., 2002. MapChart: Software for the graphical presentation of linkage maps and QTLs. The Journal of Heredity 93 (1): 77-78.
