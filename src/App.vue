<script setup>
import { ref, reactive } from 'vue';

const refCount = ref(0);
const reactiveCount = reactive({ count: 0 });

function increment() {
  refCount.value++;
}
</script>

<template>
  <main class="min-h-screen bg-gray-100 px-4 py-10 text-gray-800">
    <div class="mx-auto max-w-2xl rounded-lg bg-white p-6 shadow-sm">
      <h1 class="text-2xl font-bold">Aula 28/09 — Vue.js</h1>
      <p class="mt-2 text-gray-600">Passos para iniciar um projeto Vue.js e um contador simples.</p>

      <section class="mt-6 space-y-5">
        <div>
          <h2 class="font-semibold">Passo 1: Instalar o Node.js</h2>
          <p>
            Baixe em <a href="https://nodejs.org/" class="text-green-700 underline">nodejs.org</a> e
            siga o instalador, clicando em Next e aceitando os termos.
          </p>
          <p class="mt-1 text-sm text-gray-600">
            Versão mínima: o Node.js 18.3 não atende aos requisitos deste projeto. Conforme o
            package.json, use Node.js 22.x a partir de 22.18.0 ou versão 24.12.0 ou superior.
          </p>
        </div>
        <div>
          <h2 class="font-semibold">Passo 2: Criar o projeto Vue.js</h2>
          <p>
            No terminal, execute
            <code class="rounded bg-gray-100 px-1">npm create vue@latest</code>, responda às
            perguntas do assistente e configure o projeto conforme suas preferências. Depois, entre
            na pasta criada.
          </p>
          <p class="mt-1 text-sm text-gray-600">
            Se já está usando este repositório, vá direto ao passo 3.
          </p>
        </div>
        <div>
          <h2 class="font-semibold">Passo 3: Instalar as dependências</h2>
          <p>
            Na pasta do projeto, execute <code class="rounded bg-gray-100 px-1">npm install</code>.
          </p>
        </div>
        <div>
          <h2 class="font-semibold">Passo 4: Executar o projeto</h2>
          <p>
            Execute <code class="rounded bg-gray-100 px-1">npm run dev</code> e abra o link local
            exibido no terminal.
          </p>
        </div>
      </section>

      <section class="mt-6 border-t border-gray-200 pt-5">
        <h2 id="counter-title" class="font-semibold">Contador</h2>
        <p class="mt-1 text-sm text-gray-600">
          Começa em 0 e soma 1 a cada clique usando ref. Ao recarregar a página, volta a zero.
        </p>
        <button
          type="button"
          @click="increment"
          class="mt-3 cursor-pointer rounded bg-green-700 px-4 py-2 text-white hover:bg-green-800 focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-green-700"
        >
          Valor usando ref: <span>{{ refCount }}</span>
        </button>
      </section>

      <section class="mt-6 border-t border-gray-200 pt-5">
        <h2 id="counter-title" class="font-semibold">Contador</h2>
        <p class="mt-1 text-sm text-gray-600">
          Começa em 0 e soma 1 a cada clique usando reactive. Ao recarregar a página, volta a zero.
        </p>
        <button
          type="button"
          @click="reactiveCount.count++"
          class="mt-3 cursor-pointer rounded bg-green-700 px-4 py-2 text-white hover:bg-green-800 focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-green-700"
        >
          Valor usando reactive: <span>{{ reactiveCount.count }}</span>
        </button>
      </section>
      <section class="mt-6 border-t border-gray-200 pt-5">
        <h2 class="font-semibold">Diferença entre ref e reactive</h2>
        <p class="mt-2 text-sm text-gray-600">
          Os dois criam estados reativos: quando o valor muda, o Vue atualiza a tela.
        </p>
        <ul class="mt-3 list-disc space-y-2 pl-5 text-sm text-gray-600">
          <li>
            <strong>ref:</strong> aceita valores simples, como números e textos, e também objetos.
            No script, usamos <code>.value</code>: <code>refCount.value++</code>. No template deste
            exemplo, usamos apenas <code>refCount</code>.
          </li>
          <li>
            <strong>reactive:</strong> trabalha com objetos e arrays. Acessamos suas propriedades
            diretamente, sem <code>.value</code>: <code>reactiveCount.count++</code>.
          </li>
        </ul>
        <p class="mt-3 text-sm text-gray-600">
          Neste projeto, <code>ref(0)</code> guarda o número do primeiro contador e
          <code>reactive({ count: 0 })</code> guarda o objeto do segundo contador.
        </p>
      </section>
    </div>
  </main>
</template>
