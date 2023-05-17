# Flex Container

O Flex Container é a tag que envolve os itens flex, ao indicar display: flex, essa tag passa a ser um Flex Container.

## 1 - Display

Define o elemento como um flex container, tornando os seus filhos flex-itens.

**display: flex;**
- Torna o elemento um flex container automaticamente transformando todos os seus filhos diretos em flex itens.

```html
<h1>Display</h1>

<h1>display: block;</h1>
<section class="container">
	<div class="item">1</div>
	<div class="item">2</div>
	<div class="item">3</div>
	<div class="item">4</div>
</section>

<h1>display: flex;</h1>
<section class="container flex">
	<div class="item">1</div>
	<div class="item">2</div>
	<div class="item">3</div>
	<div class="item">4</div>
</section>

<h1>display: flex;</h1>
<section class="container flex">
	<div class="item">Teste 1</div>
	<div class="item">Teste 2</div>
	<div class="item">Teste 3</div>
	<div class="item">Teste 4</div>
	<div class="item">Teste 5</div>
	<div class="item">Teste 6</div>
	<div class="item">Teste 7</div>
</section>

<h1>display: flex;</h1>
<section class="container flex flex-wrap">
	<div class="item">Teste 1</div>
	<div class="item">Teste 2</div>
	<div class="item">Teste 3</div>
	<div class="item">Teste 4</div>
	<div class="item">Teste 5</div>
	<div class="item">Teste 6</div>
	<div class="item">Teste 7</div>
</section>

<h1>display: flex; // flex-item-1</h1>
<section class="container flex">
	<div class="item flex-item-1">Teste 1</div>
	<div class="item flex-item-1">Teste 2</div>
	<div class="item flex-item-1">Teste 3</div>
</section>
```

```css
/* Flex */
.flex {
	display: flex;
}

.flex-wrap {
	flex-wrap: wrap;
}

.flex-item-1 {
	flex: 1;
}

/* Flex Item */
.item {
	margin: 5px;
	background: tomato;
	text-align: center;
	font-size: 1.5em;
}

.container {
	max-width: 400px;
	margin: 0 auto;
	border: 1px solid #ccc;
}

h1 {
	text-align: center;
	margin: 20px 0 0 0;
	font-size: 1.25em;
	font-weight: normal;
}

body {
	font-family: monospace;
	color: #333;
}
```

### 2 - Flex-Direction

Define a direção dos flex itens. Por padrão ele é row (linha), por isso quando o display: flex; é adicionado, os elementos ficam em linha, um do lado do outro.

A mudança de row para column geralmente acontece quando estamos definindo os estilos em media queries para o mobile. Assim você garante que o conteúdo seja apresentado em coluna única.

**flex-direction: row;**
- Os itens ficam em linha
 
**flex-direction: row-reverse;**
- Os itens ficam em linha reversa, ou seja 3, 2, 1.

**flex-direction: column;**
- Os itens ficam em uma única coluna, um embaixo do outro.

**flex-direction: column-reverse;**
- Os itens ficam em uma única coluna, um embaixo do outro, porém em ordem reversa: 3, 2 e 1.

```html
<h1>flex-direction: row;</h1>
<section class="container row">
	<div class="item">1</div>
	<div class="item">2</div>
	<div class="item">3</div>
</section>

<h1>flex-direction: row-reverse;</h1>
<section class="container row-reverse">
	<div class="item">1</div>
	<div class="item">2</div>
	<div class="item">3</div>
</section>

<h1>flex-direction: column;</h1>
<section class="container column">
	<div class="item">1</div>
	<div class="item">2</div>
	<div class="item">3</div>
</section>

<h1>flex-direction: column-reverse;</h1>
<section class="container column-reverse">
	<div class="item">1</div>
	<div class="item">2</div>
	<div class="item">3</div>
</section>
```

```css
.row {
	flex-direction: row;
}
.row-reverse {
	flex-direction: row-reverse;
}
.column {
	flex-direction: column;
}
.column-reverse {
	flex-direction: column-reverse;
}

/* Flex Container */
.container {
	max-width: 400px;
	margin: 0 auto;
	display: flex;
	border: 1px solid #ccc;
}
/* Flex Item */
.item {
	/* O flex: 1; é necessário para que cada item se expanda ocupando o tamanho máximo do container. */
	flex: 1;
	margin: 5px;
	background: tomato;
	text-align: center;
	font-size: 1.5em;
}

h1 {
	text-align: center;
	margin: 20px 0 0 0;
	font-size: 1.25em;
	font-weight: normal;
}

body {
	font-family: monospace;
	color: #333;
}
```

### 3 - Flex Wrap

Define se os itens devem quebrar ou não a linha. Por padrão eles não quebram linha, isso faz com que os flex itens sejam compactados além do limite do conteúdo.

Essa é geralmente uma propriedade que é quase sempre definida como flex-wrap: wrap; Pois assim quando um dos flex itens atinge o limite do conteúdo, o último item passa para a coluna debaixo e assim por diante.

**flex-wrap: nowrap;**
- Valor padrão, não permite a quebra de linha.

**flex-wrap: wrap;**
- Quebra a linha assim que um dos flex itens não puder mais ser compactado.

**flex-wrap: wrap-reverse;**
- Quebra a linha assim que um dos flex itens não puder mais ser compactado. A quebra é na direção contrária, ou seja para a linha acima.

```html
<h1>flex-wrap: nowrap;</h1>
<section class="container nowrap">
<!-- O nome grudado foi necessário pois eu preciso definir um conteúdo que não possa ser quebrado. Como uma palavra ou uma imagem. Se fosse uma frase, ele quebraria as linhas da frase antes de ultrapassar o container.	 -->
	<div class="item">TesteDoItem1</div>
	<div class="item">TesteDoItem2</div>
	<div class="item">TesteDoItem3</div>
</section>

<h1>flex-wrap: wrap;</h1>
<section class="container wrap">
	<div class="item">TesteDoItem1</div>
	<div class="item">TesteDoItem2</div>
	<div class="item">TesteDoItem3</div>
</section>

<h1>flex-wrap: wrap-reverse;</h1>
<section class="container wrap-reverse">
	<div class="item">TesteDoItem1</div>
	<div class="item">TesteDoItem2</div>
	<div class="item">TesteDoItem3</div>
</section>
```

```css
.nowrap {
	flex-wrap: nowrap;
}
.wrap {
	flex-wrap: wrap;
}
.wrap-reverse {
	flex-wrap: wrap-reverse;
}

/* Flex Container */
.container {
	max-width: 360px;
	margin: 0 auto;
	display: flex;
	border: 1px solid #ccc;
}
/* Flex Item */
.item {
	/* O flex: 1; é necessário para que cada item se expanda ocupando o tamanho máximo do container. */
	flex: 1;
	margin: 5px;
	background: tomato;
	text-align: center;
	font-size: 1.5em;
}

h1 {
	text-align: center;
	margin: 20px 0 0 0;
	font-size: 1.25em;
	font-weight: normal;
}

body {
	font-family: monospace;
	color: #333;
}
```