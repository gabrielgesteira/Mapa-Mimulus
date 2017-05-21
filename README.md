## Escola Superior de Agricultura “Luiz de Queiroz” 
### Programa de Pós graduação em Genética e Melhoramento de Plantas
### Disciplina: Biometria de Marcadores Genéticos

**Alunos:**
- Emanoel Martins
- Gabriel Gesteira
- Jackeline Borba
- Pedro Barbosa

## Mapa Genético - _Mimulus sp._

Um mapa de população F2 proveniente do cruzamento entre _Mimulus guttatus_ e _Mimulus nasutus_ foi construído por Fishman _et. al_ e publicado na revista _Genetics_ em 2001. Sabendo que mais locos foram genotipados após a construção deste mapa, o objetivo do nosso trabalho foi refazer o mapa para incluir as informações dos novos marcadores. Para isso utilizou-se o conjunto de dados completo, contendo os marcadores antigos e os novos, e considerando as informações já disponíveis no artigo.  Os novos marcadores são mais informativos que os antigos, apresentando especialmente a segregação 1:2:1 (codominantes), o que auxilia na construção de um mapa mais preciso pela abordagem multiponto. Para construir o mapa final utilizou-se o software _Onemap_, sendo necessárias três etapas durante a construção que estão sintetizadas abaixo, juntamente com os respectivos códigos e funções.

## Primeira Tentativa

Os grupos de ligação foram formados considerando todos os marcadores e o LOD sugerido, mantendo a frequência de recombinação 0,5. Seguindo esses critérios foram obtidos 10 grupos de ligação. Contudo, houve necessidade de manipular os grupos de ligação para coerência com as informações prévias divulgadas no artigo.

[**Clique aqui**](https://gabrielgesteira.github.io/Mapa-Mimulus/mapmimulus_1tentativa.html) para visualizar o script e os resultados obtidos com a análise.

## Segunda Tentativa

Ao visualizar os _heatmaps_ podemos notar que os grupos 1, 3 e 4 apresentaram evidências de que deveriam ser separados em outros grupos, independentes. Os grupos 1 e 3 foram subdivididos em grupos menores, cada um originando 3 grupos. Para separar o grupo 1 utilizou-se LOD=6 e rf=0.25. Para separar o grupo 3 utilizou-se LOD=5.45 e rf=0.2. Entretanto, não foi possível separar o grupo 4,  mesmo reduzindo consideravelmente a frequência de recombinação. Para este grupo em particular optou-se por remover os marcadores que apresentaram distorções, como pode ser visto através do _heatmap_. 
Dessa forma, obtivemos um total de 14 mapas, semelhante ao que foi obtido por Fishman _et. al_ (2011). Após a divisão destes grupos, eles foram reorganizados para que cada um deles estivesse de acordo com a sequência definida por Fishman, ou seja, G1novo=G1artigo, G2novo=G2artigo, e assim por diante. Então, verificamos se os marcadores presentes em cada grupo formado estavam no mesmo grupo apresentado no artigo, manipulando um a um quando necessário.

[**Clique aqui**](https://gabrielgesteira.github.io/Mapa-Mimulus/mapmimulus_2tentativa.html) para visualizar o script e os resultados obtidos com a análise.

## Terceira Tentativa

Após eliminar todos os marcadores incoerentes, gerou-se o mapa final no _Onemap_ (com o auxílio do software _Mapchart_). Os marcadores que estão em vermelho correspondem aos marcadores presentes tanto no mapa anterior quanto no mapa novo, e os marcadores que estão sublinhados são os codominantes.

[**Clique aqui**](https://gabrielgesteira.github.io/Mapa-Mimulus/mapmimulus_3tentativa.html) para visualizar o script e os resultados obtidos com a análise.

Abaixo está a lista com os _heatmaps_ dos 14 grupos de ligação formados (clique sobre os nomes para visualizá-los):
![Grupo de ligação 1](https://gabrielgesteira.github.io/Mapa-Mimulus/images/heat1.tiff)  
![Grupo de ligação 2](https://gabrielgesteira.github.io/Mapa-Mimulus/images/heat2.tiff)  
![Grupo de ligação 3](https://gabrielgesteira.github.io/Mapa-Mimulus/images/heat3.tiff)  
![Grupo de ligação 4](https://gabrielgesteira.github.io/Mapa-Mimulus/images/heat4.tiff)  
![Grupo de ligação 5](https://gabrielgesteira.github.io/Mapa-Mimulus/images/heat5.tiff)  
![Grupo de ligação 6](https://gabrielgesteira.github.io/Mapa-Mimulus/images/heat6.tiff)  
![Grupo de ligação 7](https://gabrielgesteira.github.io/Mapa-Mimulus/images/heat7.tiff)  
![Grupo de ligação 8](https://gabrielgesteira.github.io/Mapa-Mimulus/images/heat8.tiff)  
![Grupo de ligação 9](https://gabrielgesteira.github.io/Mapa-Mimulus/images/heat9.tiff)  
![Grupo de ligação 10](https://gabrielgesteira.github.io/Mapa-Mimulus/images/heat10.tiff)  
![Grupo de ligação 11](https://gabrielgesteira.github.io/Mapa-Mimulus/images/heat11.tiff)  
![Grupo de ligação 12](https://gabrielgesteira.github.io/Mapa-Mimulus/images/heat12.tiff)  
![Grupo de ligação 13](https://gabrielgesteira.github.io/Mapa-Mimulus/images/heat13.tiff)  
![heat14.tiff](https://gabrielgesteira.github.io/Mapa-Mimulus/images)

Para visualizar o mapa final gerado, [clique aqui**](https://gabrielgesteira.github.io/Mapa-Mimulus/images/mapa_mimulus.pdf).

## Material e Métodos

Um mapa genético proveniente do cruzamento entre _Mimulus guttatus_ e _M. nasutus_ foi construído por Fishman _et al._ (2001) e atualizado com posterior informação de novos marcadores. O novo mapa de ligação foi construído com o auxílio do software _Onemap_ (versão em desenvolvimento - Margarido _et al._) e _RStudio_ versão 3.4. Um total de 287 indivíduos de uma população $F_2$ e 418 marcadores foram utilizados na análise. Fishman _et al._ (2001) construiu o mapa inicial utilizando informação de 255 marcadores e o software _MAPMAKER_ 3.0. Dentre os marcadores, 213 são codominantes e 205 dominantes. Para construção do mapa final foram necessárias algumas etapas de construção dos grupos de ligação, ordenamento dos marcadores dentro de cada grupo e posterior realocação para equivalência ao que foi publicado previamente. Dentro do pacote _Onemap_ utilizou-se função de mapeamento “Kosambi” e as funções _compare_, _Rapid Chain Delineation_ e _try_ embutidas na função "order_seq()", juntamente com o algoritmo _Ripple_. No total, 19 marcadores foram descartados porque não apresentaram evidências de ligação, e o mapa final gerou 14 grupos, semelhante ao publicado anteriormente. Este mapa foi construído com o auxílio do software _MapChart_.

## Material and Methods

A genetic linkage map of an interspecific crossing between Mimulus guttatus and M. nasutus was constructed by Fishman et. al (2001) and updated with posterior information of new markers. The new linkage map was built using the program Onemap® version in development (Margarido et. al) and Rstudio® version 3.4. A total of 287 genotyped individuals of an F2 population and 418 markers were analyzed. Fishman et. al (2001) had constructed the prior map with 255 markers and using the program MAPMAKER 3.0. Among these markers, 213 were codominants and 205 dominants. In order to build the final map several rounds of mapping, grouping and ordering within each linkage group were necessary, and relocation of markers to correspond with was published before. Within the Onemap package, the mapping function chose was Kosambi, and the functions compare, Rapid Chain Delineation and try, through the order_seq() command, which automate the process of mapping a sequence of markers, combining compare and try.seq functions. The algorithm Ripple was used to check for plausible alternative orders. A total of 29 markers were discarded and the final map has 14 linkage groups, as well as the map published before. This final map figure was built using the program MapChart®.


## Referências

Fishman, L., A. J. Kelly, E. Morgan and J. H. Wilis, 2001 A genetic map in the Mimulus guttatus species complex reveals transmission ratio distortion due to heterospecific interactions. Genetics 159: 1701-1716.

Margarido, G. R. A., A. P. Souza and A. A. F. Garcia, 2007 OneMap: software for genetic mapping in outcrossing species. Hereditas 144: 78-79.

R Core Team (2014). R: A Language and Environment for Statistical Computing. R Foundation for Statistical Computing, Vienna, Austria. URL http://www.R-project.org/.

Voorrips, R.E., 2002. MapChart: Software for the graphical presentation of linkage maps and QTLs. The Journal of Heredity 93 (1): 77-78.
