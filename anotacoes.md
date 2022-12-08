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

## Cores e fontes

- Nesse projeto ao invés de colocar as cores no arquivo css global eu coloquei no arquivo de theme.
- lembrando que para poder usar essas cores deve ser utilizada a propriedade props setando o theme 
fazendo interpolação.

## Configurando ESLint

- Vem de ECMA SCRIPT Lint ele basicamente vai validar se o código está seguindo os padrões do projeto 
- Essa ferramenta é utilizada para padronizar projetos por que em projetos com varias pessoas trabalhando 
as vezes cada pessoa utiliza formatações diferentes por ex.
- Existe uma extensão no VScode ESLint é importante ter instalada.
- Também vou instalar como uma dependencia de desenvolvimento com o comando  npm i eslint -D  
- também vamos instalar um pacote da Rocketseat com o comando npm i @rocketseat/eslint-config -D 
- Caso fosse necessário criar uma configuração propria poderemos rodar o comando   npx eslint --init  
- Após isso eu crio um arquivo chamado .eslintrc.json dentro desse arquivo eu crio um extends com o nome do pacote que vou utilizar.
- Para de forma automatica fazer correções em um projeto ja existente e corrgir tudo que estiver em outro padrão  basta rodar o comando    npx eslint src --ext .ts,.tsx --fix

## React Router DOM 

- Utilizamos a biblioteca mais famosa dentro do react para lidar com rotas que é a react-router como etsamos 
lidando com ele na web utilizaremos o react-router-dom e para instalar eu rodo o seguinte comando: 
        npm i react-router-dom 
- dentro de src foi criada uma pasta page e dentro dela temos dois componentes que serão duas páginas History.tsx e Home.tsx
- Também foi criado um componente chamado Router.tsx para fazer a definição de rotas é importante  fazer as importações do Routes e Route e em seguida passar as path e as paginas dentro do element.
- Importante após isso voltar ao App.tsx e importar o Router.
- Importante também importar o BrowserRouter e colocar em volta do Router dentro do arquivo App.tsx

## Layout de rotas

- Criei um componente chamado Header 
- Foi criado uma pasta chamada layouts e dentro um arquivo chamado DefaultLayout.tsx
- dentro desse componente de defaultlayout eu vou colocar o Header que vai aparecer em 
todas as páginas e vou importar de dentro do react-router-dom o  Outlet que esse componente 
gera um espaço que será preenchido com algum conteudo.
- Para que funcione eu devo voltar ao arquivo de rotas e por volta das minhas rotas eu devo 
colocar mais um elemento Route, nesse Route eu devo colocar uma / no path e no element passar meu componente DefaultLayout.
- com isso eu conigo definir componentes que vão aparecer em todas as páginas e evitar duplicação de códigos.

## Header & Layout 

- O DefaultLayout é um componente que criamos que vai servir com ripper ou seja como um 
container em todas as páginas vamos configurar todo o layout da nossa aplicação dentro desse componente.
- Foi utilizado o pacote de icones do phosphor react para instalar basta rodar o comando abaiixo 
    npm i phosphor-react  
- No meu menu ao inves de usar a tag ancora do html eu  utilizo o componente NavLink e no lugar da propriedade src eu utilizo to 
- O NavLink cria uma propriedade active que eu posso dentro do meu css utilizar por exemplo para colocar 
alguma cor depois que clicar no icone.

## Aprimorando inputs 

PS- O datalist me permite criar uma lista de coisas dentro do meu input, uma lista de sugestões
por ex.
- dentro do html existem alguns elementos que podem ser utilizadas como o step que permite com 
que seja definido um valor para incrementar toda vez eu auamentar a quantidade de valores, e a 
propriedade min para estipular um valor minimo e max para um valor maximo.

 ## Componente status

 - Quando estamos trabalhando com Styled-components nem sempre é necessário criar 
 um arquivo style separado, dependendo pode ser criado um componente de styles dentro do arquivo já existente. 

 - No styled conseguimos adicionar elementos através do after e do before inserimos esses elementos dentro do html pelo componente styles.
 - quando utilizamos um before é necessário colocar a propriedade content mesmo estando vazia.

 - Dá para fazer componentes de stilos do styled receber propriedades e para isso 
 é necessário criar uma interface e passar propriedades utilizando props, lembrando que 
 após fazer isso é necessário passar a propriedade onde o componente foi setado.

 - como estamos passando cores nessa propriedade foicriado um objeto chamado STATUS_COLOR passando os rgbs das cores.

 - A propriedade as const é utilizada para o typescript entender que cada chave do objeto vai 
 possuir um valor especifico, nesse caso se não for utilizado vai dar erro por que ele vai entender tudo como string na hora de utilizar no   props.theme[STATUS_COLORS[props.statusColor]]

 - Eu posso refatorar a propriedade da minha interface  statusColor: 'yellow' | 'red' | 'green' 
 por  statusColor: keyof typeof STATUS_COLORS com isso eu evito duplicação de código caso eu queira adicionar mais cores.

## Controllerd vs Uncontrolled 

- Quando se trabalha com formularios dentro do React tesmo dois modelos de trabalho dentro da aplicação, a forma controlled ou uncontrolled, esses termos tem muita haver como o react funciona.

- Controlled é manter em tempo real o estado a informação que é inserida pelo usuario dentro 
do estado que é uma variavel no componente, toda vez que o usuario digitar uma informação no 
input será atualizada a informação no stado contendo esse novo valor para que o valor que o 
usuario digitou seja atualizado, Ou seja é quando a gente mantem em tempo real a informação do 
input do usuario guardada no estado da aplicação.

- O React toda vez que é feita uma atualização de estado é provocada uma nova renderização, toda vez que qualquer função com alteração de estado é chamada o  react recalcula todo o conteudo do 
componente do estado que mudou, isso não necesspariamente é um processo lento mas se tivermos 
interfaces muito complexas com muitas informaçãoes isso pode virar um problema, por isso o formulario feita desta maneira controlled pode ser um problema para a aplicação em questão de performace, na maioria das vezes não vai ser mas em alguns momentos pode ser.

- Uncontrolled é a busca da informação do valor do input somente quando for necessário, quando for precisar dela. 
- Uma das maneiras de fazer isso é utilizar o proprio elemento onSubmit do html e criar uma função handleSubmit que pega o event e pega o valor do input. Com isso eu ganho em performace 
mas perco em fluidez, existem momentos na aplicação em que precisamos escolher qual dos dois tipos de formularios vamos fazer.

## React hook: Form 

- Nesse projeto para fazer os inputs funcionarem utilizamos uma biblioteca do React chamada react hook form essa biblioteca consegue trabalhar das duas formas Controlled e Uncontrolled 
conseguindo ter performace e flexibilidade ao mesmo tempo.
- É necessario ir ao site https://react-hook-form.com e seguir os passos da instaslação da biblioteca que é bem simples.

- comando para instalar   npm i react-hook-form 

- importamos a função useForm do react-hook-form em seguida eu chamo essa função dentro do meu 
componente e ela devolve algumas informações.

- Podemos utilizar a desestruturação e extrair duas funções a register e a handleSubmit a função 
register é um metodo que adiciona um input ao formulario, o  useForm é como se tivesse criado um 
novo form na aplicação, a função register informa quais são os campos que vai ter no formulário
eu abro parenteses e utilizo ... setando register e depois dou um nome para ela {...register('task')} dessa forma.

- A função register recebe o nome do input e ela retorna alguns metodos que são os metodos que 
utilizamos para trabalhar com inputs no JavaScript como onChange, onBlur,onFocus e varias outras
funções, como ela retorna várias funções é por isso que utilizamos em sua sintaxe spred operation ... , essa função é na verdade um objeto que traz todas as outras funções.

- A função handleSubmit eu vou utilizar dentro do meu form passando como parametro para ela a 
função que eu criei handleCreateNewCycle. 

- Dentro da função handleCreateNewCycle eu recebo como argumento o data que são os dados do 
meu input do formulario. 

- Dentro do meu {...register('minutesAmount')} ele está retornando o valor como uma string e eu 
posso utilizar um segundo argumento para trazer um objeto de configurações e trazer uma propriedade chamada valueAsNumber que eu posso fazer um boleano true ou false, fazendo isso ele 
irá retornar um number ao inves de uma string.

- Eu posso desestruturar também de dentro do useform a função watch que observa e posso utilizar ela para observar os campos do meu input, e com isso dá para conseguir saber o valor do campo em 
tempo real, dentro disso eu posso estabelecer uma condição para que se o campo for diferente de vazio eu quero habilitar o botão, para fazer isso va no botão e colocar disabled={!task}.

- As variaveis auxiliares não alteram a funcionalidade do código, também não vão prejudicar em 
performace, elas melhoram a legibilidade do código, por isso eu criei a variavel isSubmitDisabled
pelo nome ela já indica meu submit está desabilitado ? e subistiuo ela no meu disabled, quem pegar esse código já vai entender que estamos desabilitando o submit quando a task não estiver presente.

## Validando formulários

- Aqui abordamos como fazer validações no formulário, mostrar mensagens,bordas, o react-hook-form
ele não tráz validação de forma padrão, o react-hook-form prefere utilizar outras bibliotecas que já são feitas para validação e faz integração com essas libs, abaixo alguns exemplos de boas libs para validação.
- yup 
- joi
- zod 
- Todas elas são boas e semelhantes, utilizaremos a zod por que ela integra um pouco mais com o 
typeScript.

- Para fazer a integração com essas libs externas é necessário rodar o comando abaixo: 
    npm i @hookform/resolvers 

- Para instalar a lib do zod rodamos o comando abaixo: 
    npm i zod

- Após instalados os pacotes é necessário fazer o import da lib 
    import { zodResolver } from '@hookform/resolvers/zod';

-Como essa lib não tem um export default é necessário indocar que todas as funções da lib 
na importação dessa maneira:    import * as zod from 'zod';

- Dentro do useForm é criado um objeto resolver e será utilizada a função zodResolver(), nessa 
função será passada as regras de validação, por isso foi criado um objeto fora do componente 
chamado newCycleFormValidationSchema Ps- utilizamos schema por que essas libs utilizam um formato
de validação que é schema base que nada mais é que um formato que a validalçao é feita com base nesse formato, utilizamos zod.object por que estamos validando um objeto, dentro desse objeto eu possuo dois campos o campo task eu defino o que eu quero na minha validação e posso passar uma mensagem de validação que será retornada ao usuario caso o campo não seja valido, o outro campo 
é o minutesAmount.

- O próximo passo é passar o objeto que foi criado newCycleFormValidationSchema para o zodResolver

- Eu posso utilizar dentro do useForm a propriedade formState e posso acessar ela dando um console.log passando ela e a propriedade errors isso vai mostrar detalhes de quando não for feita a validação.

## TypeScript no formulário

- Existe uma propriedade no useForm que se chama defaultValues que permite passar o valor 
inicial de cada campo.

- como já foi criado uma inteface posso passsar para useform deixando o código mais inteligente.

- o zod possue uma função que extrai a tipagem do form de dentro do schema de validação eu posso 
substituir minha interfce por um type e passar zod.infer passando para ele o newCycleFormValidationSchema lembrando que não se pode colocar uma variavel javascript assim de forma direta eu necessário converter em uma tipagem por isso utilizamos o typeof.

- O legal disso é que se caso seja necessário adicionar mais uma propriedade ao newCycleFormValidationSchema ele já faz a tipagem de forma automatica não sendo necessário colcar na interface.

- PS- sempre que for necessário referenciar uma variavel JavaScript dentro do typeScript é 
necessário utilizar o typeof antes dela.

## Resetando o form 

- Dentro do useForm podemos utilizar uma função chamada reset e apenas invocando essa função 
dentro do handleCreateNewCycle que automaticamente ele irá limpar os valores dos campos após 
o submit, essa função volta os valores do campo para os valores que forma definidos como default.

## Iniciando novo ciclo  (Estado)

- Adicionando um ciclo ativo dentro da aplicação para que o novo ciclo se inicie na aplicação 
é necessário ter um estado, IMPORTANTE --> O estado é a unica forma de conseguir armazenar alguma
informação dentro do componente que consiga fazer a interface reagir e essa informação.

- Por isso foi criado um estado(useState) para armazenar esse ciclo.
- Também foi criado uma interface chamada cycle para definir o formato dos ciclos da aplicação

- Importante que quando passei para a interface Cycle para meu estado eu passei como uma lista 
de ciclos por isso eu passo como array <Cycle[]>

- É Importante iniciar o estado com uma informação do mesmo tipo que for ser manuseado ao longo da aplicação. ex: const [cycles, setCycles] = useState<Cycle[]>([]) eu passei uma lista de definir um lista vazia.

- com isso eu posso dentro do handleCreateNewCycle iniciar a criação do ciclo.

- Quando o estado depende da sua verão anterior antes de ser alterado é interessante esse 
valor do estado ser setado em formato de function é o conceito de closures no React 
     setCycles((state) => [...state, newCycle])

- Existe uma lista de ciclos na aplicação porém só existe um ciclo ativo por momento e para isso 
foi definido um novo state  activeCycleId.

- Para mostrar em tela qual o ciclo ativo foi criado uma variavel chamada activeCycle essa variavel com base no id do ciclo ativo, percorrer todos os ciclos existentes e retornar qual o 
ciclo que tem o mesmo id do ciclo ativo para que se consiga retornar essas informações.

## Criando countdown 

- Na versão atual pode ser inserido a quantidade de minutos no ciclo porém a redução do tempo é
feita a partir de segundos e por isso é necessário conseguir manipular o Countdown em segundos.

- Foi criado uma variavel que converte o numero de ciclos de minutos para segundos essa variavel 
se chama totalSeconds.

- Foi necessário também a criação de um novo estado chamado amountSecondsPassed esse estado armazena a quantidade de segundos que já se passaram desde que o ciclo foi criado. Com isso 
a gente vai mostrar na interface a informação atualizada.

- Também foi criada uma variavel chamada currentSeconds que conta a quantidade que já passou. 

- É necessário converter essa varialvel de forma que se consiga exibir em tela, em tela tem que
ser exiibido em minutos e segundos, para isso é necessário calcular a partir do total de segundos
quantos minutos se tem dentro do total de segundos vou pegar o total de segundos divido por 60 porém essa divisão pode dar um numero quebrado e por isso utilizamos o metodo floor que faz o arredondamento para baixo, vou armazenar em uma variavel chamada minutesAmount.

- Também é necessário calcular a quantidade de segundos do resto dessa divisão e vou armazenar em uma variavel chamada secondsAmount.

- Foi criada mais uma variavel chamada minutes ela converte para string o minutesAmount e com isso foi utilizado o metodo padStar que preenche uma string até um tamanho especifico caso não tenha, com algum caracter. A variavel de minutos é necessário ter 2 caracteres se caso ela não possuir vai ser incluido 0 no start da string ou seja no começo até completar 2 caracteres. Foi duplicado esse mesmo código porém para segundos.
    