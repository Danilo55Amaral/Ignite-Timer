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
    
## hook useEffect

- Os hooks são funcionalidades no React e elas tem como função acoplar algum funcionamento ao componente da aplicação, eles tem prefixo use como useState, useEffect.

# useState

- O useState consegue armazenar variaveis que quando tem o seu valor alterado provocam uma nova
renderização no  componente, com isso se consegue exibir em tempo real uma  informação conforme
for atualizada por alguma funcionalidade ou clique do usuario ou algo semelhante.

# useEffect 

- useEffect -> Side-effect -> Efeito Colateral

- O useEffect permite ficar monitorando mudanças em uma variavel, e toda vez que essa variavel mudar indenpendente de motivo, origem, ou quem alterou essa variavel, uma função pode ser disparada.

- O useEffect executa também no inicio assim que o componente for exibido em tela e depois toda vez que a lista por ex for alterada, caso nao queira que isso aconteça ser feito condições dentro do useEffect.

- O useEffect caso não seja passado nada para o array de dependencias que faz o monitoramento ele apenas irá executar uma vez quando o componente for exibido em tela. Essa estratégia é muito 
utilizada para fazer chamas api.

- Ps- Quando utiloizamos dentro do useEffect uma variavel externa e sempre qie for usada uma
variavel externa obrigatoriamente é necessário incluir essa variavel como uma dependencia do 
useEffect, no projeto foi a variavel activeCycle.

## Reduzindo countdown  (useEffect )

- Existem muitas formas de resuzir o time por segundos na aplicação, mas aqui comecamos 
definindo uma nova propriedade starDate que sua finalidade é salvar a data que o time inicia.
- Dentro do newCycle foi jogado o starDate como sendo a data atual sendo a data que o ciclo 
iniciou. 

- Também é necessário criar um useEffect e dentro dele é criado o intervalo.

- É necessário comparar a data atual com a data que fica salva no starDate e verificar 
quantos segundos se passaram, para isso foi instalado um pacote chamado date fns basta 
rodar o comando   npm i date-fns  de dentro desse pacote utilizamos uma função chamada 
differenceInSeconds que calcula a diferença de duas datas em segundos.

- Ps- Quando utiloizamos dentro do useEffect uma variavel externa e sempre qie for usada uma
variavel externa obrigatoriamente é necessário incluir essa variavel como uma dependencia do 
useEffect, no projeto foi a variavel activeCycle, isso vai inplicar em um funcionamento toda vez 
que essa variavel mudar esse trecho de código vai executar novamente isso pode ser bom ou ruim. Para esse projeto não vai ter relevancia no momento.

## Mudando title da página (useEffect)

- Aqui resolvemos alguns bugs e melhoramos um pouco o código da aplicação.
- Umas das coisas sobre o useEffect é que pode-se ter um retorno e esse retorno sempre será 
uma function essa função possue uma responsabilidade de se tinha um intervalo rodando com o ciclo criado anteriormente essa função serve para que quando o useEffect for executado novamente 
por ter tido alguma mudança na variavel de dependencia eu possa fazer algo para resetar o que 
estava sendo feito no useEffect anterior. Essa função é importante para deletar os intervalos que não são mais necessários. Isso irá corrigir o bug que ficava acrescentando os novos intervalos ao que já estava sendo feito a contagem.

- Um dos bugs foi resolvido com essa implementação mas quando o novo ciclo foi criado ele cria baseado na quantidade de tempo que passou no ciclo anterior, isso acontece por que o tempo que segundo quie se passaram não está sendo resetado  na variavel amountSecondsPassed, isso faz com que seja aproveitado a quantidade de segundos que se passaram no ciclo anterior para o novo ciclo criado, para resolver esse bug bastou passar a variavel setAmountSecondsPassed dentro da função handleCreateNewCycle resetando para zero.

- Também foi criado uma nova funcionalidade que quando se abre uma nova aba o contdown fica contando em cima na aba do titulo, Para isso foi criado outro useEffect e nele toda vez que minutes e seconds for atualizados irpa ser interpolado uma template string no document.title, isso foi colocado em uma condição para acontecer apenas quando se tiver um ciclo ativo.

## Interromper o ciclo

- Quando o ciclo estiver rolando o botão precisa mudar para a funcionalidade de interromper o ciclo.

- Para isso na parte do botão de iniciar um novo ciclo é necessário criar um if com a seguinte 
condição se tiver um ciclo ja rolando irá ser mostrado algo se não será mostrado o botão de iniciar um novo ciclo. No primeiro trecho dessa condição eu criei um StopCounterButton o tipode dele não será submit e sim button isso por que dessa vez eu não quero fazer um submit no form apenas interromper o ciclo atual.

- Uma das implementações é desabilitar o campo de input quando algum ciclo estiver rodando e para isso basta passar a propriedade disabled com o activeCycle dentro de TaskInput. O valor dessa propriedade precisa ser convertido para bolean e por isso basta colocar !! que faz com que se tiver algum valor converta para true.

- Quando o botão de interromper for clicado é necessário retornar ao estado inicial da aplicação
para isso foi criada uma função chamada handleInterruptCycle essa função vai setar o setActiveCycle de volta para null e outra coisa também é anotar dentro do ciclo se ele foi 
interrompido ou não, para que depois se tenha um histórico de quais ciclos foram interrompidos 
pela metade e quais não foram.

- Eu preciso dentro da minha interface cycle colocar mais um Date chamado interruptedDate.

## Ciclo completo

- Temos um useEffect que percorre setInterval e calcula a diferença de segundos, é preciso que 
se a diferença em segundos da data que o ciclo foi criado, para a data atual for igual ou maior 
que o total de segundos quer dizer que o ciclo acabou. 

- Foi pego differenceInSeconds e foi colocado em uma variavel chamada secondsDifference 

- Eu preciso criar uma outra informação na interface finisheDate.

## Separando Componentes

- Nota-se que o componente da home está muito grande e ficando complexo nesse caso para melhorar 
o código podemos separar em mais componentes.
- Quando um componente começa a crescer muito devemos separar ele em componentes menores.

- Dentro de home eu crio duas pastas NewCycleForm com um arquivo index.tsx e um 
arquivo styled. 
- Também crio uma outra pasta que também será um componente chamado Countdown
- Depois foi separado nesses dois componentes partes do home.

## Prop Drilling no React

- Note que mesmo que depois de separar em componentes existem variaveis que devem
ficar no componente home, existem informações que não podem ser movidas para dentro do Countdown por que elas precisam ser usadas fora desse componente também.

- A principal forma de se fazer comunicação entre componentes é utilizando propriedades, eu posso passar essas propriedades com interfaces.

- Note que ao separar em componentes separados tivemos que criar varias propriedaes e passar entre componentes isso meio que acabou deixando o código 
ainda mais complexo de que quando estava tudo no componente home.

- Esse problema é bem comum no react e se chama Prop Drilling que é quando temos 
muitas propriedades apenas para comunicação entre componentes, quando se tem muitas propriedade sendo passadas para componentes filhos apenas para fazer a 
comunicação entre esses componentes, isso pode ser bem trabalhoso e prejudicar 
bastante a manuntenção da aplicação.

- Quando não é utilizado em excesso tipo sendo necessário passar 2 ou 3 as propriedades resolvem lindamente nossos problemas mas a partir do momento que 
se tem em excesso isso acaba poluindo o código para dar manutenção.

- As Propriedades são a princípal forma de fazer a comunicação entre componentes porém não é a única existe uma outra forma  de fazer isso com  um conceito do React Context API. 

## Context API 

- Permite compartilharmos informações entre Varios componentes ao mesmo tempo
- Ela não precisa utilizar de propriedades 
- É como se fossem informações Globais que todos os componentes podem ter acesso,
Todos os componentes podem modificar essas informações, quando modificadas e 
independentemente de quem modificou essas informações, todos os componentes que 
dependiam e dependem dessa informação são atualizados.
- É como conseguir se comunicar com varios componentes ao mesmo tempo da aplicação.

## Entendendo contextos

- A context API é uma maneira de compartilhar informações entre varios componentes do app de uma maneira mais sinples sem precisar utilizar várias
proppriedades.

- Sempre que for necessário que as informações fiquem acessiveis por contexto os 
dados so contexto precisam está no componente mais por fora possivel dos subcomponentes que precisam de acesso aquela informação.

- Para compartilhar a informação entre todos os componentes filhos, devemos criar um provider e colocar em volta dos componentes filhos no componetne raiz, 
e as infomrações devem ser passadas utilizando value={{}}.

- É necessário importar o useContext e createContext.

## Convertendo para Contexto 

- Eu crio dentro do componente home uma const chamada CycleContext passando 
createContext passando um objeto vazio. o createContext deve ser inportado de dentro do 'react'.

- Também foi necessário criar uma interface que coloquei o nome de CyclesContextType. Nessa interface vamos informar quais são as informações 
que vamos armazenar dentro do contexto.

- A propriedade activeCycle eu passar na interface como Cycle ou undefined por que se ela não tem um ciclo ativo ela é indefinida, ele não consegue encontrar 
nenhum ciclo ativo.

-  Passaei ainterface como tipagem no createContext  dessa forma createContext({} as CyclesContextType) se eu não fizer isso o TypeScript vai dar erro informando que temos um contexto vazio.

- Eu vou passar o meu provider por em volta dos componentes que precisam acessa-lo <CyclesContext.Provider />

- Para que o Countdown consiga acessar o contexto é necessário exporta-lo 
        export  const CyclesContext = createContext({} as CyclesContextType)

- Dentro do Countdown utilizaremos o useContext e dentro passamos o CyclesContext, com isso podemos acessar a propriedade activeCycle, Posso com isso chamar qualquer informação do meu contexto.

- Eu criei uma função markCurrentCycleAsFinished para marcar um ciclo como finalizado e vou enviar a função como contexto.

- PS- A função arkCurrentCycleAsFinished foi definida no componente home por que ela usa da função setCycles que só existe dentro do componente home, a função arkCurrentCycleAsFinished
foi enviada dentro do contexto assim todos os componentes que estão dentro desse contexto tem 
acesso a ela e quando o componente Countdown chama essa função ele chama a função que está na home que vai alerar o estado de ciclos.  Essa lógica é muito  importante.

## Contexto no formulario

- geralmente quando temos uma informação que não pertence tanto ao contexto como a função 
register, é algo de uma lib externa que pode ser trocada a qualquer momento. Geralmente 
tentamos manter no contexto somente coisas que não vão mudar se for trocada uma lib ou qualquer outra coisa assim.

- O react hook form oferece um contexto proprio que podemos utilizar e vou utilizar, FormProvider em volta do NewCycleForm. dentro do FormProvider eu vou utilizar o spred 
operation {...newCycleForm} que é a variavel.

- O operador spred pega cada uma das propriedades do objeto e passa como uma propriedade 
para o meu componente.

- Eu utilizei o contexto do form FormProvider apenas em volta do NewCycleform por que apenas 
esse componente irá precisar dele.

- PS- Eu criei um array com propriedade e armazenei em uma variavel chamada newCycleForm 
depois utilizei o operador spred passando esse variavel {...newCycleForm} enviando todas as propriedades pelo meu  contexto.

## Contexto entre rotas 

- Existe também na aplicalção a página de hitórico e ela também precisa saber sobre os ciclos,
o provider do CyclesContext está dentro da home não tem como essas informações serem acessadas 
na página do Histórico.

- É necessário compartilhar essa informação dos ciclos entre as duas páginas da aplicação, uma das estratégias é mover o contexto para um local que englobe todos os componentes que vão precisar dessas informações, o  unico local em que todas as páginas e componentes vão ter acesso é no componente rayz da aplicalção o app.tsx, existem um porém que para fazer isso será necessário mover varias funções e importações para dentro do app.tsx e isso o deixaria bastante poluido quando levamos em conta que outros contextos podem ser criados para alguma implementação futura.

- Para resolver esse problema criamos uma pasta separada contexts só para contextos e dentro dela eu crio um arquivo para o meu contexto vou chama-lo de CyclesContext.tsx dentro desse arquivo foi colocado tudo que tem relação com o contexto.

- É importante criar o arquivo de contexto desacoplado de libs externas por que se um dia 
for necessário mudar as libs externas o contexto não seja afetado. Por isso foicriado 
uma nova interface CreateCycleData para tipar alguns dados que em home estão juntos com libs externas.

- Após criar meu arquivo de contexto eu volto ao meu app.tsx e por volta das rotas eu coloco o  componente que foi criado no arquivo de contexto.

- Feito isso agora eu posso acessar minhas propriedades também na página de histórico basta utilizar o meu contexto.

- Para fazer um teste basta eu utilizar o seguinte código 
      <pre>{JSON.stringify(cycles, null, 2)}</pre>



## children

- Eu passei  um elemento dentro da tag do CyclesContextProvider que é o Router e isso 
irá retornar um erro do react, isso acontece por que eu preciso dentro do CyclesContextProvider falar no return onde que o conteúdo que está por dentro que é considerado como filho vai ser acoplado, isso no react é chamado de children, dentro 
das propriedades do componente pai deve-se passar uma propriedade especial do react chamada children e vou utilizar ela dentro do CyclesContext.Provider dessa forma {children}

- Para satisfazer a tipagem da propriedade children eu posso utilizar o ReactNode e passa-lo como propriedade, devo importar do react.

- O ReactNode serve para tipar tudo aquilo que eu utilizo no meu código tsx.

## Reset do formulario

- Uma das coisas importantes foi não trazer libs externas para dentro do contexto isso por que o contexto deve ficar intacto caso seja necessário trocar alguma lib.

- Dentro de home é necessário criar uma função chamada handleCreateNewCycle e ela irá chamar a função createNewCycle, essa função recebe os dados que é NewCycleFormData e passa esses dados  para createNewCycle, ela também chama a função reset resetando o formulario.

## funções handle
- Toda vez que eu crio uma função para ser chamada a partir de um evento eu coloco o prefixo handle.

## Listagem do Histórico 

- Agora fizemos a listagem dos dados na página de histórico.

- dentro da tbody eu chamo a variavel cycles passando um map e para cada um dos ciclos eu vou retornar um tr, na tr é necessário passar o atributo key que é a informação única que se tem para cada ciclo no passo eu passei o id, em seguida é só passar os dados para as tds.

- Na parte de mostrar o Status eu criei uma condição utilizando && que tudo que tiver na segunda parte só vai ser executada se o que tiver na primeira pare for true com isso o componente Status só vai ser mostrado se o que eu setei na primeira parte da minha condição for verdadeira.

## Formatação de data

- Para fazer a formatação da data foi utilizado a lib date-fns e foi utilizado um metodo chamado formatDistanceToNow eu também devo importar o indioma ptBR.

## Reducers

## Criando reducer de ciclos

- Aqui temos mais um hook do react o useReducer esse hook serve para arazenar uma 
informaçao e alterar essa informação posteriormente, geralmente se usa o reducer para 
armazenar informações mais complexas, principalmente nas horas em que se precisa alterar 
essas informações.

- Um exemplo prático é na função interruptCurrentCycle que criamos para interrromper ciclos 
se quisermos que ela seja utilizada em outro local da aplicação será necessário copiar ela, e 
com o reducer isso não é necessárop por que  é como se tivesse um local fixo para todas as alterações que possam acontecer dentro de um estado do componente.

- Foi criado o Reduce dentro do proivider que criamos em CyclesContext.tsx, o useReducer recebe 
dois parametros o primeiro parametro é uma função. o segundo parametro é qual o valor inicial da variavel, esse valor inicial pode ser um array vazio.

- A função do reducer sempre irá receber dois  parametros o state que é o valor atual em tempo 
real da variavel, e a action é a ação que o usuario quer realizar de alteração dentro da variavel essa action é algo unico para indicar uma ação que o usuario está querendo fazer para alterar o estado ou seja são ações que o uruario pode querer utilizar para modificar o estado, essa função vai retornar um state. 

- É necessário tipar o state e nesse caso como estámos utilizando cycles vamos utilizar um 
array de Cycle, isso por que eu devo tipar com o formato que vai ser armazenado no meu state, 
o action por ainda não se ter uma tipagem para ele pode usar o any. 

- O setCycles vai ser agora um metodo para a action ser disparada ele não vai ser mais um metodo que altera o valor de cycles, por isso eu troquei o nome dele para dispatch é um nome que é dado geralmente para uma variavel ou função que se quer disparar algum funcionamento.

- Após isso eu substituo os locais em que eu utilizo o setCycles por dispatch.

- Dentro do dispatch é preciso enviar alguma informação que dentro do reducer seja disntinguir 
uma action da outra, ou seja quando a função dispatch é chamada ela será executada e o valor que foi passado ao dispatch para para o lugar de action e dentro do reducer pode ser feita a 
alteração desejada no estado.

- Quando se usa reducer dentro do react é muito comum que ao invés de enviar a informação crua seja enviado um objeto, dentro desse objeto um type e dentro do type seja informado a ação que se quer realizar, e dentro de um novo objeto chamado payload eu envio os dados. ou seja o type
que podemos chamar do quer quiser e o payload que enviamos o que quisermos enviar.

- Eu dei um log dentro do reducer em state  e action para testar se o valor enviado estava chegando.

- Dentro do reducer eu criei a seguinte condição se o action.type for igual a ADD_NEW_CYCLE ao 
invés de retornar o state se nenhuma alteração vai ser retornado um novo array copiando o state
e adcionando no final o action.payload.newCycle.

# Resumindo
- Nota-se que dentro do reducer temos uma função que vai agregar a função que recebe todas as 
ações de modificações nesse estado, ou seja eu vou ter um ponto central para todas as alterações que precisam acontecer, essas alterações são indentificadas através do type que é 
enviado no dispatch.

- O reducer nem sempre é utilizado é mais utilizado quando se tem um estado complexo que armazena informações complexas dentro de um estado e essas informações precisam mudar de forma
constante com alterações provindas de varias fontes diferentes.

## Salvando um objeto no Reducer

- O que estava acontecendo é que o ciclo estava sendo alterado e o id estava sendo alterado logo em seguida nota-se que era feita duas alterações no estado uma após a outra, algumas 
vezes alterar até 3 coisas no estado ao mesmo tempo, existiam estados que eram correlacionados e que era necessário alterar eles ao mesmo tempo e para isso era preciso chamar funções diferentes. 

- Quando um Reducer é usado não se tem mais a obrigatoriedade de salvar dentro do reducer somente uma informação, pode-se salvar várias informações dentro e alterar várias informações
ao mesmo tempo. 

- No meu algoritimo o id do ciclo ativo vão ser controlados por um unico estado que é o reducer
e com isso não é necessário ter vários estados dentro do componente para controlar o valor de 
várias informações se essas informações pertencem ao mesmo assunto ou mesma regra.

- Eu renomeei cycles por cyclesState e criei uma const que estrai cycles e activeCycled de cyclesState.

- O Reducer é um padrão um patern utilizado em varias ferramentas diferentes, várias libs diferentes, varios contextos diferentes.

## Marcando ciclo como finalizado (Refatorando o Reducer)

- Aqui vamor marcar o ciclo como finalizado 
- Nota-se que temos dentro do reduce um encadeamento de ifs que dá para ser refatorato 
por um switch

## Separando Action Types

- Para melhorar o código pegamos o conteudo da função do reducer e colocamos em outro arquivo dentro de uma pasta chamada reducers.

## Separando Actions

- Podemos abstrair também as chamadas das actions, dentro da pasta reducers foi criado uma pasta chamada cycles e dentro dela foi renomeado o arquivo cycles para 
reducer e foi criado um novo arquivo chamado actions.

- dentro do arquivo actions foi criada uma função para cada action.

## Utilizando immer 

- O immer é um lib que é utilizada para trabalhar com dados imutaveis, quando vai 
alterar estados e a alteração ela é muito profunda, alterar alguma posição que pode 
está dentro de uma posição no aray é necessário fazer map que muitas vezes podem 
ser confusos, o  immer permite com que trabalhemos com estruturas de dados imutaveis
como se essas estruturas de dados não fossem imutaveis, ou seja ele permite que seja feita alterações nas variaveis no estado do react, reducer do react, como se fossem 
variaveis tradicionais do JS.

- Para instalar o immer basta rodar o comando npm i immer

- Dentro do reducer foi importado o produce de dentro do immer e esse metodo produce é que vai ser chamado.

- basta chamar o metodo produce passar o que gostaria de modificar e no segundo parametro recebe uma variavel draft que é o rascunho e dentro dele podemos fazer as 
alterações que queremos fazer. Com isso eu consigo por ex utilizar metodos como o push que são metodos que não respeitam a imutabilidade do react.

## Salvando estado no storage

- Uma das coisas que podemos fazer como melhoria no código é salvar as informações dos ciclos, no storage do Browser com isso assim que a página for atualizada os dados não serão perdidos e os ciclos não irão ter que ser recriados do zero.

- Para isso dentro do CyclesContext foi criado um useEffect e vou definir que toda 
vez que o cyclesState mudar independente do motivo isso será salvo no local storage.

- Ps- o localStorage só permite que salvamos textos dentro dele.

- Quando for salvar informações no localStorage sempre coloque um prefixo com o nome 
da aplicação e dois pontos o nome da informação ex: @ignite-timer:cycles-state outra 
dica importante é colocar também uma versão @ignite-timer:cycles-state-1.0.0 versionamos por que se algum dia for necessário trocar essa variavel isso pode evitar bugs.

- Eu posso ir no Browser em Application -> Local Storage -> Eu já vou sonseguir encontrar meu @ignite-timer:cycles-state-1.0.0

- Pode-se enviar um terceiro parametro para o useReducer que é uma função que é disparada assim que o reducer for criado.
Para que esses dados iniciais do reducer sejam recuperados em um outro lugar

