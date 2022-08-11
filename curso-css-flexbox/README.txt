# Curso Posicionamento elementos com Flexbox em CSS

Apresentação dos fundamentos e aplicações da propriedade flexbox na criação de layouts responsivos, sem a necessidade de valores fixos.

## Informações gerais

* Nível intermediário
* Duração de 4 horas
* Professora Karen Santos
  * Software Developer na nTopus Possibilidades

## Requisitos básicos

* Conclusão do curso de Introdução a criação de websites com HTML5 e CSS3;
* Editor de texto (Visual Studio Code);
* Navegador Chrome;

## Percurso

* **Aula 1:** Introdução ao Flexbox
* **Aula 2:** Fundamentos do Flexbox
* **Aula 3:** Projeto integrador
  * Construção de Landing Page com Figma

## Anotações das aulas

### Flex Container

Flex Container é a tag que envolve os itens filhos para aplicação da propriedade "display:flex".

Suas propriedades relacionadas são: display, flex-direction, flex-wrap, flex-flow, justify-content, align-items e o align-content.

Flex Item podem ser passíveis de aplicação da propriedade Flex Container, sendo um processo recursivo.

​	Suas propriedades relacionadas são: flex-grow, flax-basis, flex-shrink, flex, order 	e o align-self.

### Propriedades do Flex Container

#### Aula 1 - Propriedade display: flex

* Instalar extensões no VSCode
  * HTML Snippets
  * Live Server Preview

- [x] Cria arquivo display-flex.html

#### Aula 2 - Propriedade flex-direction

Estabelece o eixo principal do container para a direção que os flex items são inseridos dentro do container, sendo os eixos:

* **Eixo horizontal row (padrão):** linha na direção do texto, da esquerda para direita.
* **Eixo row-reverse:** sentido oposto à direção do texto.
* **Eixo vertical column:** coluna ordenada de cima para baixo.
* **Eixo column-reverse:** ordenação inversa do column.

- [x] Cria arquivo flex-direction.html

#### Aula 3 - Propriedade flex-wrap

O flex-container por padrão vem definido com a propriedade row.

O comportamento do flex-container por padrão (row) não permite a quebra de linha, ou seja, que os items passem para a próxima linha ou coluna.

Isso é ocasionado devido aos flex items serem compactados ao máximo do limite do conteúdo e do container. Uma vez que o container não consiga mais comporta-lós, esses items irão vazar.

A propriedade flex-wrap, portanto, define (ou não) a quebra de linha dos containers. Esses comportamentos veremos a seguir.

* **nowrap:** é o comportamento padrão do flex-container, não permitindo a quebra de linha, ocasionando em problemas de interface com a possibilidade de elementos vazando.
* **wrap:** permite a quebra de linha, ajustando o comportamento assim que algum dos flex items não possam mais ser compactados dentro de um container, passando esse item para a linha abaixo, entretanto, pode ocasionar em outros problemas como espaçamento que será preciso tratar.
* **wrap-reverse:** tem a mesma lógica do wrap, permitindo a quebra de linha, entretanto ao invés de passar os items para a linha para baixo, os items são passados para linha acima (ou na direção contrária, no caso de colunas); esse comportamento não altera a ordem dos elementos, podendo exemplificar como:
  * 5, 6, 7; 1, 2, 3.

#### Aula 4 - Propriedades do flex-flow

Basicamente, essa propriedade é um atalho para as propriedades flex-flow e flex-wrap anteriores. 

Seu uso não é tão comum, pois quando mudamos o flex-direction para column, mantemos o padrão do flex-wrap (que é a propriedade nowrap), ou seja, é mantido os comportamentos padrões esperados.

Não é só uma remoção de linha. Ganhamos independência para setar esse valores, mas o que afeta quando unimos esses dois elementos? Existem prós e contras. Com curiosidade, modifique o código abaixo no wrap e nowrap e entenda o funcionamento desse atalho, como os items ficam expostos.

#### Aula 5 - Propriedade justify-content

##### Justify-content rows

Essa propriedade se encarrega do alinhamento dos itens dentro do container.

Além disso, trata também da distribuição do espaço entre os itens.

Caso seus itens estejam ocupando 100% de todo o container, ou seja, os itens filho desse flex container não deixam sobras de espaço (margens ou congêneres), essa propriedade não se aplica, porque não faria sentido.

Utilizamos a propriedade justify-content para distribuir os espaços sobressalentes. 

Suas variações são:

* **Flex-start:** alinha os itens no início do container;
* **Flex-end:** alinha os itens no fim do container;
* **Center:** alinha os itens no centro do container;
* **Space-between:** alinha dois elementos (ou mais) nas extremidades do container, esquerda e direita;
* **Space-around:** trata os espaçamentos do meio do container são duas vezes maiores do que o espaçamento inicial e final do container;

Esses são os principais utilizados. Existem outros valores como left, right, stretch, normal e alguns outros, entretanto, não necessariamente todos vão se aplicar quando lidamos com flex-container e flexbox.

##### Justify-content columns

Até o momento só manipulamos os itens e os alinhamentos dos espaços contanto com o comportamento padrão que é o row. Agora, vamos adicionar os comportamentos com colunas.

#### Aula 6 - Propriedade align-items

#### Propriedade align-content

Conheceremos a última propriedade relacionada ao flex-contain.

Essa propriedade é responsável por tratar o alinhamento do eixo vertical do container, ou seja, a orientação das linhas desses containers. Para isso, precisamos respeitar as seguintes regras:

* O container precisará utilizar quebras de linha, ou seja, o container precisa implementar a propriedade flex-wrap com modo wrap;
* A altura do container precisa ser maior do que a soma das linhas dos itens, ou seja, supondo que eu tenha 2 linhas de 20px que somem 40px no total, o container precisará ser maior do que 40px;
* Essas duas condições são necessárias para que o align-content funcione.

A propriedade align-content tem alguns tipos de alinhando, sendo eles:

* **Center:** alinha os itens ao centro
* **Stretch (comportamento padrão / row):** crescimento igualitário de todos os items, responsável por pegar o maior elemento daquela linha e fazer com que os demais elementos cresçam iguais a esse elemento;
* **Flex-start:** alinha os itens no início do container;
* **Flex-end:** alinha os itens no final do container;
* **Space-between:** cria um espaçamento igual entre os elementos;
* **Space-around:** espaça os elementos com o dobro de espaço entre os elementos (observando a proporcionalidade dos itens que estão subsequentes ao primeiro item ou estão anteriores ao último item do container)

:warning: Existem alguns conceitos misturados que já vimos do **justify-content** (center, stretch, flex-start e flex-end) e alguns elementos da propriedade **align-items** (space-between e space-around). São as mesmas lógica de funcionamento, logo, se complementam.

#### Propriedade align-items

Ainda está relacionada com nosso flex-container.

Trata do alinhamento dos flex itens de acordo com o eixo do container (horizontal e vertical).

Permite o <u>alinhamento central</u> no **eixo vertical**, ou seja, alinhamento de items no meio da tela.

Um diferencial do align-content é que o align-items não precisamos conhecer a altura dos elementos filhos dentro de cada container filho (somente no container pai). Ou seja, essa propriedade tenta pegar essa proporcionalidade e expande esses elementos de forma crescente.

* **Center:** alinha no centro;
* **Stretch (comportamento padrão):** os flex itens crescem igualitariamente;
* **Flex-start:** alinha no início do container; 
* **Flex-end:** alinha no fim do container;
* **Baseline:** Utiliza o eixo da linha relacionada ao texto do conteúdo dos itens;

- [x] Cria arquivo align-items.html

#### Propriedade align-content

Trata do <u>alinhamento das linhas</u> do container, em relação ao **eixo vertical** do container.

Para essa propriedade funcione, precisamos que:

* Container utilize quebras de linha;
* A altura do container seja maior do que a soma das linhas dos itens, ou seja, se se temos dois itens com 20px cada, totalizando 40px de altura, a altura do container precisa ser maior do que 40px.

Tipos de alinhamento do align-content:

* **Center:** alinha os itens ao centro;
* **Stretch (comportamento padrão):** flex itens crescem de forma crescente;
* **Flex-start:** alinha os itens no início do container;
* **Flex-start:** alinha os itens no fim do container;
* **Space-between:** cria um espaçamento igual entre os elementos;
* **Space-around:** cria espaçamentos no meio dos itens sendo duas vezes maiores que os espaçamentos iniciais e finais do container; 

:warning: Existem conceitos mesclados, novamente, aqui nessa propriedade, do align-items (center, stretch, flex-start e o end) e um pouco do conceito do justify-content (space-between e align-round).

- [x] cria arquivo align-content.html

Última propriedade relacionada aos flex containers.

Agora, falaremos sobre os flex-items relacionados aos filhos desses containers.

---

### Flex items

#### Propriedade flex-grow

Define a proporcionalidade de crescimento dos itens, respeitando o tamanho dos conteúdos internos, ou seja, o tamanho dos conteúdos internos. 

Essa propriedade não funcionará caso tenhamos adicionado justify-content ao flex container.

