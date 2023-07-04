---
marp: true
title: XML e Web Semantics - nbmcd
description: XML no contexto de Web Semantics
theme: gaia
paginate: true
_paginate: false
---
<style>
section {
    background: #e1e2e7;
    color: #2b1515;
}
h1 {
    color: #0e0606;
    font-size: 70px;
}
span {
    font-weight: bold;
    color: #2b8fff;
}
a {
    font-size: 30px;
}
</style>
<!-- _class: lead -->
# XML e Web Semantics
Nilo Drumond

---
# World Wide Web
- Acessível ao <span>ser humano</span>
- Hypertext Markup Language (HTML)

<!--
Conjunto de padrões que tem como um dos principais objetivos ser acessível ao ser humano
HTML, hyperlinks
-->

---
<!-- _class: lead -->

# Semantic Web
Web acessível para <span>computadores</span>

<!-- 
Uma extensão do World Wide Web
objetivo: permitir que as máquinas leiam e compreendam as informações da web
-->

--- 

# Semantic Web
- Processar, transferir e integrar informações
- Repositório de documentos 🡒 Base de conhecimento <span>estruturada</span>

<!--
Não apenas padrões para apresentar informações para o usuário,
mas tornar essas informações acessíveis para a máquina

Semântica da Web tem como objetivo transformar a Web de um repositório de documentos
em uma base de conhecimento estruturada e interconectada.
-->

--- 

<!-- _class: lead -->
# XML
e<span>X</span>tensible <span>M</span>arkup <span>L</span>anguage

<!--
Nesse contexto de Semantic Web, um dos padrões que surgem é o XML.
-->

---

# XML
- Estrutura hierárquica
- Baseado em tags
- Dados estruturados
- Legível para humanos e máquinas
- Extensível

<!--
Representar dados estruturados e organizados. [exemplo de items de uma loja com preços]
Além de ser compreensível para máquinas, ele é legível ao ser humano, o que facilita depuração
Extensível: o usuário pode criar suas próprias tags
-->

---

![bg](./assets/xml-5.png)


<!--
XML tem como objetivo armazenar e estruturar os dados, não apresentar
outra linguagem, como javascript que vai ler esses dados e decidir como apresentar
-->

---

# XML
- Elementos
- Atributos

![bg right:70%](./assets/xml-5.png)

<!-- 
A base do XML são os elementos e os atributos. 
Um elemento é definido pela suas tags de abertura e fechamento e o seu conteudo.
Um atributo são dados associados a um elemento. Semelhante ao HTML.
Um elemento vazio pode carregar dados por meio de atributos.
-->

---
# XML - Prolog
- Declaração XML
    - version
    - encoding
    - standalone
- Referência externa

![bg right contain](./assets/prolog.png)

<!--
O Prolog consiste em uma declaração XML e uma opcional referência a estruturas externas
Na declaração xml nos temos esses campos:
version é a versão do XML que está sendo usada naquele arquivo
encoding é qual a codificação caracteres sendo usada
standalone é um campo opcional que diz se o documento faz referência a estruturas externas ou não.
-->

---
<!-- _class: lead -->
# DTD e XML Schema
<span>Validar</span> o formato do dados

<!-- 
No mesmo contexto surge a necessidade de definir formatos pros dados
de forma que diferentes grupos de pessoas concordem com o formato.
Sejam grupos diferentes equipes da mesma empresa,ou entre um cliente e um servidor...
Nos dois casos a declaração pode ser feita dentro do arquivo ou em outro arquivo. Mas na prática quase sempre é feito em um arquivo externo por mótivos manutenção e reusabilidade.
-->

--- 
<!-- _class: lead -->
# DTD
<span>D</span>ocument <span>T</span>ype <span>D</span>efinition
![bg right contain](./assets/dtd-1.png)

<!-- 
Numa declaração DTD nós definimos um documento. Nesse caso uma nota/note
Definimos os elementos permitidos num documento "note" e sua estrutura
nesse caso, o elemento note tem os elementos ...
e esses elementos tem dados de texto. PCDATA = texto consistente de caracteres permitidos
-->

--- 
<!-- _class: lead -->

# DTD
<span>D</span>ocument <span>T</span>ype <span>D</span>efinition
![bg right contain](./assets/dtd-3.png)

<!--
Aqui temos um exemplo de um XML que respeita o DTD mostrado no slide anterior.
Na segundo linha, ainda fazendo parte do Prolog, temos a referência externa de DOCTYPE. Que define o dtd que será usado para este documento.
nesse caso será um documento "note" que está definido no arquivo Note.dtd que está localizado em algum lugar no sistema
-->
---

# DTD
- cardinalidade
- tipos de atributos
- tipos de valor
![bg right contain](./assets/dtd-4.png)

<!--
O DTD também é capaz de representar a contagem de elementos, 0-1, 0+, 1+; Normalmente se chama isso de operador de cardinalidade
Tipos de atributos: ID unico, referencia a um ID unico, string (PCDATA)
Tipos de valor: obrigatorio, opcional, fixo.
-->
---

# DTD
![bg right:70% contain](./assets/dtd-5.png)


<!--
Aqui a gente tem um exemplo de XML que respeita aquele DTD
-->
---

# DTD
### Limitações
- Tipos de dados
- Namespaces

<!--
Porém, DTD tem suas limitações. Em destaque um conjunto limitado de tipos de dados e não ser capaz de suportar namespaces.
-->
---
<!-- _class: lead -->
# XML Schema

![bg right:55% contain](./assets/xmls-1.png)

<!--
Para superar essas limitações, foi desenvolvido o XML Schema. Escrito em XML e exerce o mesmo papel do DTD só que de forma mais flexível e poderosa. 
-->

---

<!-- _class: lead -->
# XML Schema

![bg right:55% contain](./assets/xmls-2.png)


<!--
Aqui está um documento XML que respeita aquele XML Schema. Como vocês podem ver ao invés de ter aquele DOCTYPE, definimos diretamente no elemento note qual o formato dele e em que arquivo está localizado
-->

---

# XML Schema
- tipos de dados mais avançados
    - data
    - inteiros
    - decimais
- tipos de dados definidos pelo usuário

<!-- 
TODO: comment
-->
---

# XML Schema
### Tipos complexos
![bg right:55% contain](./assets/xmls-3.png)

<!-- 
TODO: comment
-->
---

# XML Schema
### Namespaces
- conflitos de nome
![bg right contain](./assets/xmls-4.png)


<!-- 
TODO: comment
-->
---

# Conclusão
- importância do XML e Web Semantics
- JSON
- TOML, YAML
- SVG


<!--
Nós vimos a importância da Semântica Web na internet como um todo e o XML foi uma ferramenta crucialem transformar a internet de um conjunto aleatório de sites na internet "inteligente" que é hoje, mais integrada.

Embora o XML ainda tenha o seu lugar,ele não é mais tão popular quanto era antigamente. 

Para trocas de dados, depois da popularização de APIs RESTful, o JSON ganhou bastante popularidade. Tanto por ser mais leve quanto por ser suportado nativamente pelo Javascript, que é a linguagem da web querendo ou não considerando que é o que todo o navegador roda.

Para arquivos de configuração/definição, TOML e YAML representam alternativas muito mais leves e legíveis. 

Mas ainda há o seu uso. O suporte a namespaces por exemplo é algo que nenhuma outra linguagem markup popular suporte. 
AndroidManifest
SVG
Casos mais complexos, ja que existem linguagens semlhantes e mais simples
-->

---
# Referências bibliográficas
- [ANTONIOU, Grigoris et al. A Semantic Web Primer. The MIT Press. 2012](http://prof.mau.ac.ir/images/Uploaded_files/A%20Semantic%20Web%20Primer-The%20MIT%20Press%20(2012)%5B7460174%5D.PDF)
- [DECKER, Stefan et al. The Semantic Web: The Roles of XML and RDF. IEEE. 2000](https://ieeexplore.ieee.org/document/877487)

