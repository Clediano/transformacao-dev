# Anotações aula sobre 'Panorama Web'

Ter uma visão geral sobre o desenvolvimento vai te ajudar muito no entendimento onde cada peça se encaixa. Essa compreensão é fundamental para construir aplicações completas.

# Objetivos

- Evolução das arquiteturas
- Camadas de uma aplicação
- Server-Side vs Client-side
- Multi page App (MPA) vs Single Page App (SPA)
- Conteúdos estáticos vs Dinâmicos
- Fases do desenvolvimento Web
- Entendendo os componentes
- Organizando uma aplicação
- Gerenciamento de estado
- Backend & Computação em núvem

## Evolução das arquiteturas

1. MainFrame: Aplicação no mainframe com vários terminais burros;
2. Cliente-servidor: Temos a aplicação rodando no servidor e no cliente;
3. Web: Server-side: Aplicação rodando no servidor web, mandando HTML para o cliente mostrar em tela;
4. Web: Client-side: Servidor manda os dados para o cliente 'rico' montar a página rodando JS;
5. Web moderno: Servidor manda dados ou HTML pronto para o lado cliente, dependendo da solicitação do cliente (sem o problema de distribuição de versões);

## Camadas de uma aplicação

1. Frontend: Camada aonde o usuário interage com a aplicação por meio de uma interface gráfica;
2. Backend: Camada que processa as interações do usuário com a interface gráfica;
3. Banco de dados: Camada que salva os dados da aplicação. Geralmente bem segura e até mesmo, sem acesso aberto à internet;

## Server-Side vs Client-side

1. Server-side: Códigos executados no lado do servidor, exclusivamente no servidor;

   > Algumas linguagens como o PHP, geram arquivos HTML, CSS e JS e mandam para o browser esses arquivos
   > já prontos.

2. Client-side: Linguagens nativamente interpretada nos browsers, JS, HTML e CSS;
   > Frameworks modernos geralmente recebem dados do lado servidor e processam essas informações no lado cliente para gerar a tela de forma dinâmica, e assíncrona.

## Multi page App (MPA) vs Single Page App (SPA)

1. Surgiram depois do nascimento das tecnologias modernas de frontend como Angular, React, Vue etc.
   MPA: Múltiplas páginas(arquivos HTML) na sua aplicação.

SPA: A aplicação inteira roda dentro de apenas um arquivo HTML, que é gerado dinamicamente do lado cliente ou servidor.

## Conteúdos estáticos vs Dinâmicos

1. Conteúdo estático: Arquivo gerado apenas uma vez, sem mutação, ele sempre vai ser igual; Página provida a partir de arquivos físicos.
2. Conteúdo dinâmico: Quando o HTML sobre mutações conforme o conteúdo é carregado. Quando o conteúdo de dinâmico, existe um código que vai ser usado para gerar o conteúdo; Página gerada a partir de códigos;

> A vantagem de usar arquivos estáticos é que você não precisa buscar as informações no banco de dados toda vez que precisar gerar a página. Economizando muito recurso computacional.

## Fases do desenvolvimento Web

Fase 1: Vanilla JS (1993 - 2006)

    - Aplicações confusas
    - Problemas de compatibilidade
    - Aplicações server-side

Fase 2: jQuery (2006 - 2011)

    - Camada de compatibilidade
    - Popularizou o Ajax (técnica para fazer requisição de forma assíncrona)
    - Aplicações server-side

Fase 3: Frames (Angular) (2011 - 2016)

    - Começou a era dos Frames
    - Aplicações mais interativas
    - Aplicações client-side

Fase 4: Frames + Componentes (React.JS, Angular 2, Vue) (2013 - hoje)

    - Baseados em componentes
    - Aplicações client-side
    - Aplicações mais complexas

Fase 5: Frames + JAMStack (Gatsby, Next.JS) (2015 - hoje)

    - Geração de conteúdo estático
    - Escalabilidade
    - Desacoplamento View/Data

Fase 6: Fullstack Apps (React.JS + Next.JS) (2021 - hoje)

    - Melhor divisão entre Server/Client
    - Componentes no servidor
    - Menos JS no client

## Entendendo os Componentes

Na fase 1 do desenvolvimento web com o uso do Vanilla.JS, ou se preferir, JS puro, eram comum separar uma aplicação por tecnologias. Dividir em 3 pacotes, um pacote HTML, outro CSS e outro JS. Isso não está errado, mas, se formos mostrar para alguém sem conhecimento dessas tecnologias, ele não vai dizer absolutamente nada. Com a evolução das tecnologias se torna comum a separação de uma aplicação por componentes. E estes componentes representam uma pequena parte de uma aplicação completa. Melhorando a manutenção da aplicação.

No caso do React.JS, um componente nada mais é que uma função JS que retorna um pedaço de HTML hidratado, isto é, com os valores das variáveis já transpiladas. Por exemplo:

javascript
<>
  <Header />
  <Main />
  <Footer />
</>;

const Header = () => {
  return <div>Cabeçalho</div>;
};

const Main = () => {
  return <div>Corpo</div>;
};

const Footer = () => {
  return <div>Rodapé</div>;
};


## Comunicação entre Componentes

Dentro do React.JS, existem várias formas de fazer os componentes se comunicar.

*Comunicação Direta*: fazer os componentes se comunicar é através de propriedades, assim como as tags HTML. Por exemplo:

javascript
<>
  <Header nome="Nome do usuário" />
</>;

const Header = (propriedades) => {
  return <div>{propriedades.nome}</div>;
};


*Comunicação Indireta*: fazer os componentes filhos se comunicar com os pais é feito através da passagem de funções por propriedades, o componente filho chama a função passando dados via propriedade da função. Por exemplo:

javascript
<>
  <Header nome="Nome do usuário" logarComGoogle={locarComGoogle} />
</>;

const Header = (propriedades) => {
  return (
    <div>
      {propriedades.nome}
      <button onClick={() => propriedades.logarComGoogle(meuParametro)}>
        Logar com Google
      </button>
    </div>
  );
};


## Organizando uma aplicação

Existe várias formas para organizar um projeto, um exemplo é através de tecnologias, porém, já vimos que não é adequada visto que outras pessoas vão dar manutenção para a aplicação.

## Gerenciamento de estado

Novamente, existe várias formas de gerenciar o estado da aplicação em React, podendo ser utilizado bibliotecas como Redux, ou através da Context API do React.

## Backend & Computação em Nuvem

A núvem se divide em 3 principais tipos:
IAAS: AWS, AZURE, GOOGLE CLOUD...
PAAS: FIREBASE, HEROKU, VERCEL...
SAAS: NOTION, SALESFORCE...

58:12
