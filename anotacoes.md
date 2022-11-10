## Anotações referentes ao projeto Ignite-Timer 

- Aqui utilizamos o Vite para criar esse projeto para criar basta rodar o seguinte comando
# npm create vite@latest 
- O Vite vai dá a opção de escolher o React e também optar por JS ou TS.
- Quando criado o projeto utilizado o vite é necessário que as dependencias sejam instaladas rodando o comando npm i
# npm i 

## Styled Components 

- É uma maneira de estilizar css com um conceito chamado css in js que é escrever o css da aplicação 
na sintaxe da linguagem javaScript
- Para instalar o Styled-components rodamos o seguinte comando abaixo: 
# npm i styled-components 
- ele não traz de forma nativa as tipagens do typescript por isso devemos instalar.
# npm i @types/styled-components -D 
- O Styled-components cria componentes estilizados por isso que eu crio esses arquivos com extensão ts ou js 
e dentro eu importo o styled e em seguida a criação de uma constante que deve ser criado com primeira letra 
maiuscula por se tratar de um componente.
- PS- Como estamos utilizando typeScript também é necessário criar interfaces dentro dos componentes de estilização 
do styled.

## Configurando temas 

- O Styled components permite que seja feita a gestão de temas na aplicação, é possivel ter varios temas 
- Esses temas são controlados por JavaScript.
- Foi criado uma pasta Styles e dentro da pasta foi criada uma pasta themes, dentro dessa pasta eu criei 
um arquivo para um tema e chamei de default, e dentro dele pode-se criar variaveis de cores, dentro do App,tsx 
podemos importar o ThemeProvider ou seja o tema ele será aplicado para componentes que estiverem dentro do 
ThemeProvider
- Esse componente recebe uma propriedade chamada theme e nela podemos passar o thema que criamos dentro do arquivo default.ts

## Tipagem de temas 

- Aqui temos a integração do styled-components com o tipyscript feita de forma manual para os themas 
estamos sobrescrevendo tipagens de uma biblioteca já existente. PS- não é algo que sempre é feito porem 
e bom saber.
- Dentro do styled quando criamos esses temas personalizados ele não entende as propriedade que temos dentro 
do tema que o usuario vai poder utilizar dentro do css.
- Quando trabalhamos com TypeScript temos a possibilidade de criar arquivos de tipagem especificos da minha 
aplicação. 
- eu crio uma pasta chamada @types e dentro eu vou criar um arquivo chamado styled.d.ts esse tipo de arquivo indica 
que dentro dele eu só possuo codigo de definição de tipos do typeScript.
- dentro desse arquivo eu devo fazer a importação do styled-components e também do meu tema default que eu criei após isso eu faço a total integração ao typeScript utilizando algumas palavras reservadas do TS. 

## Estilos Globais

-Dentro da pasta styles eu crio um arquivo para meu css global e dentro desse arquivo eu devo importar de dentro do 
styled-component o createGlobalStyle e vou utilizar o GlobalStyle dentro eu crio todo o css global da aplicação.