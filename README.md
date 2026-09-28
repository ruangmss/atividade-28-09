# Aula 28/09 — Vue.js

Passos para iniciar um projeto Vue.js e um contador simples, com estilização em Tailwind CSS.

## Características do Vue.js

- **Componentização:** divide a interface em partes reutilizáveis, como botões, menus e formulários, facilitando a organização e a manutenção do código.
- **Velocidade:** acompanha as mudanças nos dados e atualiza as partes da interface que dependem deles, evitando trabalho desnecessário.
- **Leveza:** possui um núcleo enxuto; o tamanho final da aplicação também depende das bibliotecas e dos recursos adicionados.
- **Reatividade:** atualiza a tela automaticamente quando o estado muda, como nos contadores deste projeto.
- **Simplicidade:** utiliza conhecimentos de HTML, CSS e JavaScript, facilitando os primeiros passos.
- **Flexibilidade:** pode ser usado em uma parte de uma página ou na construção de uma aplicação completa.

## Passo 1: Instalar o Node.js

Baixe em [nodejs.org](https://nodejs.org/) e siga o instalador, clicando em Next e aceitando os termos.

**Versão mínima:** o Node.js 18.3 não atende aos requisitos deste projeto. Conforme o `package.json`, use Node.js 22.x a partir de 22.18.0 ou versão 24.12.0 ou superior.

## Passo 2: Criar o projeto Vue.js

No terminal, execute:

```sh
npm create vue@latest
```

Responda às perguntas do assistente e configure o projeto conforme suas preferências. Depois, entre na pasta criada. Se já está usando este repositório, vá direto ao passo 3.

## Passo 3: Instalar as dependências

Na pasta do projeto, execute:

```sh
npm install
```

## Passo 4: Executar o projeto

```sh
npm run dev
```

Abra o link local exibido no terminal.

## Contador

O botão **Valor usando ref** começa em 0 e soma 1 a cada clique usando `ref`. Ao recarregar a página, volta a zero.
O botão **Valor usando reference** começa em 0 e soma 1 a cada clique usando `reference`. Ao recarregar a página, volta a zero.

## Diferença entre ref e reactive

Os dois criam estados reativos: quando o valor muda, o Vue atualiza a tela.

- **ref:** aceita valores simples, como números e textos, e também objetos. No script, usamos `.value`, como em `refCount.value++`. No template deste exemplo, usamos apenas `refCount`.
- **reactive:** trabalha com objetos e arrays. Acessamos suas propriedades diretamente, sem `.value`, como em `reactiveCount.count++`.

Neste projeto, `ref(0)` guarda o número do primeiro contador e `reactive({ count: 0 })` guarda o objeto do segundo contador. Ambos começam em 0, somam 1 a cada clique e voltam a zero ao recarregar a página.
