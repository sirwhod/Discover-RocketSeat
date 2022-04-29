# Formulários

### 🏢Estrutura

### form

Elemento que definirá um formulário

é um container estulo <selection> <footer>

Atributos básicos:

- action
- method

### Action

Serve para determinar para aonde os dados do formulário serão enviados.

### Method

Get → Os dados enviados são exibidos na URL

```html
<form action="" method="GET">
<!-- http://minhapagina.com.br/?name=rod&email=rodrigo=brandaotech.com -->

</form>
```

Post → Os Dados enviados não aparecem na URL

### Fieldset

- Agrupamento de campos
- Mesmo propósito
- Semântico
- Acessibilidade

Separação semântica do HTML, pode ser criado fora da TAG “form”, contanto que esteja com a ID Correta.

```css
<form id="fieldset"></form>
<fieldset form="fieldset"></fieldset>
```

> Nunca Criar um form dentro de outro form, pois o HTML não interpreta corretamente.
> 

**Atributos especiais**

- disabled
    - Desabilita todos os elementos internos
    - Não serão enviados ao submeter o formulário
- form
    - O id de um formulário precisar ser igual  ao qual esse fieldset pertence
    - Não precisa estar dentro do formulário
- name
    - Nome do grupo

```html
<form id="contato" action="">
	<button> Enviar </button>
</form>

<fieldset form="contato">
	<legend>Contato</legend>
</fieldset>
```

### legend

nome do agrupamento

Primeiro elemento dentro do fieldset

### label

- associar e identificar uma (ou mais) tag de entrada de dados
- Acessibilidade
- Você pode clicar para mudar o foco da entrada de dados

**Atributos**

- for
    - Para fazer a conexão entre este label e a tag de entrada de dados
    - É feita via id do input
    - Sófunciona com elementos especificos
        - button
        - input (not hidden)
        - meter
        - output
        - progress
        - select
        - textarea

```html
<label for="nome"> Nome completo</label>
<input id="nome" type="text">
```

### button

- Representa um botão
- Usado para enviar formulários
- É estilizado pelo user agent (Navegador)

**Atributos comuns**

- type
    - submit
    - reset
    - button
- autofocus
- disabled
- name
- value
- form

```html
<button type="submit" name="button" value="valor qualquer" 
autofocus disabled> Enviar </button>
```

### datalist

- Lista de valores como sugestão a uma tag <input>.
- valores sugestivos e não obrigatórios
- Usuários poderão selecionar um dos valores, ou colocar um valor diferente da sugestão.

```html
<datalist id="fruitsdata">
	<option>apple</option>
	<option>banana</option>
	<option>mango</option>
	<option>orange</option>
	<option>cherry</option>
</datalist>
```

**List**

Recebe como valor o id de um <datalist> residente no mesmo documento.

```html
<input
	type="text"
	list="fruitsdata"
	placeholder="escolha uma fruta"/>

<datalist id="fruitsdata">
	<option>apple</option>
	<option>banana</option>
	<option>mango</option>
</datalist>

<input
	type="text"
	list="colorsdata"
	placeholder="escolha uma cor"/>

<datalist id="colorsdata">
	<option>#0000FF</option>
	<option>#00FF00</option>
	<option>#FF0000</option>
</datalist>
```

### 🎲Tags de Entrada de dados

### Input

Um dos mais usados em formulários, aceita os mais diversos tipos de dados, um dos mais poderosos e complexos e elevado numero de combinações.

Atributos:

- type
- name
- id

Atributos comuns:

- autocomplete
- autofocus
- disabled
- readonly (quase todos)
- value
- form (quase todos)
- name
- required (quase todos)
- placeholder (password, search, tel, text, url)

### Password

- Colocar senha de maneira segura
- Esconde o que está sendo digitado no campo
- O estilo da apresentação do campo, depende do User Agent

**Atributos**

1. minlength / maxlength
    1. O Número mínimo e/ou máximo de caracteres ara este campo
2. size
    1. O número aceitável de caracteres que esse campo deverá conter
3. pattern
    1. Expressão regular para validar o que está sendo digitado no campo
    2. Altamente recomendado o uso de um padrão de segurança alta de senhas
    3. Exemplo: Queremos que a senha contenha caracteres hexadecimais com limite de no mínimo 4 e no máximo 8 caracteres
        1. 
        
        ```html
        <input type="password" pattern="[0-9a-fA-F]{4,8}" />
        ```
        
4. placeholder
    1. Mostra um exemplo de texto a ser digitado no campo
5. readonly / disabled
    1. Atributo booleano indicando se o campo está habilitado ou não
6. required
    1. O campo será obrigatório
7. inputmode
    1. Poderá alterar o uso do teclado em smartphones
    2. Exemplo: Queremos que o cliente só adicione números
        1. 
        
        ```html
        <input type="number" inputmode="numeric"  />
        ```
        
8. autocomplete
    1. on: Permite a sugestão de: new-password ou current-password
    2. off: Desabilita a opção de autocompletar
    3. new-password: O navegador poderá sugerir uma nova senha

### Email

- Espera que o usuário digite um email
- Irá validar e o valor digitado é um email

**Atributos**

- placeholder
- readonly / disabled
- value

- required

- multiple
    - o campo irá receber 1 ou mais emails, separado por vírgulas
- minlength / maxlength
    
    O mínimo e o máximo valor que o campo irá conter
    
- size
    - Valor numérico indicando quantos caracteres esse campo deveria conter, modificando ot amanho do campo para o usuário
- pattern
    - Uso de expressão regular para validar o campo
    - exemplo: O usuário só poderá colocar email do domínio rocketseat.com.br
        
        ```html
        <input type="password" pattern="[.+rocketseat\.com\.br]" />
        ```
        
- list
    - O id de uma tag <datalist> que está no mesmo documento
    - <datalist> irá conter uma lista de valores pré definidos a fm de sugerir ao usuário, quais valores estão disponíveis
        - Os valores do <datalist> que não forem compatíveis com o campo, não serão apresentados como sugestão.

### URL

- Espera qie o usuário digite uma URL
- Irá validar se o valor digitado é uma URL

**Atributos**

- placeholder
- readonly / disabled
- value
- required
- multiple
    - o campo irá receber 1 ou mais emails, separado por vírgulas
- minlength / maxlength
    
    O mínimo e o máximo valor que o campo irá conter
    
- size
    - Valor numérico indicando quantos caracteres esse campo deveria conter, modificando ot amanho do campo para o usuário
- pattern
    - Uso de expressão regular para validar o campo
    - exemplo: O usuário só poderá colocar email do domínio [rocketseat.com.br](http://rocketseat.com.br/)
        
        ```html
        <input type="url" pattern=".*\.com\.br\/.*" />
        
        ```
        
- List
    - O id de uma tag <datalist> que está no mesmo documento
    - <datalist> irá conter uma lista de valores pré definidos a fm de sugerir ao usuário, quais valores estão disponíveis
        - Os valores do <datalist> que não forem compatíveis com o campo, não serão apresentados como sugestão.
- spellcheck
    - Habilitar a verificação ortográfica para este input

### File

- Usuário poderá escolher 1 ou mais arquivos

**Atributos**

- Value
    - Contém arquivo a ser enviado
- accept
    - Descreve que tipos de arquivos serão aceitos
    - Exemplo: .doc, .docx, .pdf, audio/*, image/png, .png
- files
    - A lista de arquivo ou arquivos
- multiple
    - Permite o envio de múltiplos arquivos

**Envio dos arquivos**

Para envio dos arquivos o formulário deverá utilizar o método POST e o atributo enctype como:

```html
<input type="file" enctype="multipart/form-data"  />
```

### Color

- Interface para selecionar cor
- Color picker

**Atributos**

- Value: RGB
    - Se inválido, o preto será exibido
- List
    - O id de uma tag <datalist> que está no mesmo documento
    - <datalist> irá conter uma lista de valores pré definidos a fm de sugerir ao usuário, quais valores estão disponíveis
        - Os valores do <datalist> que não forem compatíveis com o campo, não serão apresentados como sugestão.

### Checkbox

- Caixas podem ser marcadas
- Selecionar um valor para ser enviado
- Se não selecionado, não será enviado nenhum dado.

**Atributos**

- Globais
- Value
    - Valor que aquele campo contém
    - se não estiver presente, o padrão é ‘on’
- Checked
    - Para deixar o campo marcado por padrão

### Hidden

```html
<input type="hidden" id="timestamp" name="timestamp" value"1286705410">
```

- Invisível ao usuário
- Será enviado com o formulário
- Não receberá foco
- Leitores de tela não recebem esse campo

### Radio

```html
<input type="radio">
```

- Projetado para selecionar uma única opção de um grupo de opções

**Atributos Essenciais**

- Checked
    - Indica que o campo foi marcado
- Value
    - Valor que aquele campo contém

### Textarea

- Mais de uma linha
- Útil para textos grandes

**Atributos**

- id
- name
- rows e cols
- maxlength e minlength
- wrap
- Outros comuns ao <input>
    - autocomplete, autofocus, disabled, placeholder, readonly, form, required

### Select

```html
<select>
```

- Controle que fornece um menu de opções

```html
<option>
```

- Contém as opções a serem selecionadas
- Atributos nescessários
    - Value
- Atributos únicos
    - multiple
        - habilita múltiplas opções
    - size
        - Quando opções invisiveis?

### Optgroup

```html
<label> Please Choose one or more pets:
	<select name="pets" multiple size="8">
		<optgroup label="4-legged pets">
			<option value="dog">Dog</option>
			<option value="cat">Cat</option>
			<option value="hamster" disabled>Hamster</option>
		</optgroup>
		<optgroup label="Flying pets">
			<option value="parrot">Parrot</option>
			<option value="macaw">Macaw</option>
			<option value="albatross">Albatros</option>
		</optgroup>
	</select>
</label>
```

### Search

```html
<input type="search" />
```

- Para campos de busca
- É igual ao campo do tipo ‘text’ mas poderá ser um pouco diferente
- dependendo do user agent

**Atributos**

- list / <datalist>
- pattern
- aria-label

### Number

```html
<input type="number" />
```

- Entrada de Números

**Atributos**

- min/max
- step

### Range

```html
<input type="range" min="-10" max="10" step="5"/>
```

- Controle para selecionar um valor numérico
- Slider ou dial control

**Atributos**

- min/max
- step

### 📐Criando um Formulário

**Desenhando**

Pensar nos requisitos ajuda a definir as necessidades

**Dicas💡**

- Simples e focado
- Somente dados necessários
- Verifique o que te agrada

Exercício:

Crie um Formulário de contato:

1. O Formulário deverá conter um título de nome Contato. Usar fieldset e legend para essa finalidade.
2. O formulário conterá 3 campos
    1. Nome (Input texto)
    2. Email (Input email)
    3. Mensagem (textarea)
3. O Formulário deverá conter um botão para enviar.

Atenção! ⚠

O Formulário deverá conter regras de acessibilidade, como o label para cada campo por exemplo.

### Correção!

[https://codepen.io/sirwhod/pen/WNdqLjJ](https://codepen.io/sirwhod/pen/WNdqLjJ)

```html
<form action=""> 
  <fieldset>
    <legend>Contato</legend>
    <label for="name" > Nome </label>
    </br>
    <input id="name" name="name" type="text" placeholder="Digite seu nome completo" >
    </br>
    </br>
    <label for="email"> Email </label>
    </br>
    <input id="email" name="email" type="email" placeholder="Digite seu email completo">
    </br>
    </br>
    <label for="mensage"> Mensagem </label>
    </br>
    <textarea name="message" id="menssage" cols="30" rows="10" placeholder="Digite sua mensagem"></textarea>
    </br>
    <button type="submit">Enviar</button>
  </fieldset>
</form>
```
