---
theme: geist
title: Diogo Castro PAP
class: text-center
highlighter: shiki
drawings:
  persist: false
transition: fade-out
mdc: true
---

# Bem-vindos à apresentação da minha prova de aptidão profissional

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
     <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/blursed-org" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

---

# Blursed

Blursed foi a organização sem fundos lucrativos e sem personalidade jurídica que os dois colegas, João Gonçalves e Diogo Castro criaram para este projeto.

- **Privacidade** - A Blursed compromete-se a proteger a privacidade de todos os utilizadores e participantes, garantindo que os dados pessoais são tratados com a máxima confidencialidade e em conformidade com as regulamentações de proteção de dados.
- **Segurança** - A segurança é uma prioridade máxima para a Blursed. Implementamos medidas rigorosas para proteger a integridade dos nossos sistemas e a confidencialidade das informações, assegurando que todos os participantes possam colaborar num ambiente seguro.
- **Open-Source Software** - A Blursed promove e utiliza software de código aberto, incentivando a transparência, a colaboração e a inovação comunitária. Todos os nossos projetos e ferramentas são disponibilizados publicamente para que qualquer pessoa possa contribuir e beneficiar.
- **Tecnologias Bleeding-Edge** - A Blursed está na vanguarda da tecnologia, adotando e experimentando com as mais recentes inovações tecnológicas para desenvolver soluções avançadas e eficazes para os desafios contemporâneos.
- **HackClub Bank Sponsored** - A Blursed é patrocinada pelo HackClub Bank, uma plataforma financeira que apoia organizações sem fins lucrativos, fornecendo-lhes os recursos e a infraestrutura necessários para gerir e expandir os seus projetos com eficiência e transparência.
  <br>
  <br>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Com a criação da Blursed, nós pretendemos formar um ambiente colaborativo e inovador, onde a tecnologia e a comunidade se unem para criar impacto positivo.
-->

---

# Projeto n.º1: Rosie AI

<img src="https://cdn.discordapp.com/avatars/1132759106994847766/8455c144fe5c73f414658bb658a14253.png?size=128" class="rounded-full">

## O que é a Rosie AI?

Rosie é uma chatbot capaz de participar em conversas em real-time e criar imagens, isto tudo dentro da plataforma Discord!

---

# Rosie: Key features

- **Privacidade** As mensagens são enviadas diretamentes do Discord para o modelo GPT-4o da OpenAI, e são 100% encriptadas no nosso servidor.
- **Open-Source Software** A Rosie é 100% open-source, sendo assim possível verificar como as mensagens são tratadas.
- **Tecnologias Bleeding-Edge** A Rosie usa tecnologias como Bun (nova runtime para JavaScript/TypeScript, consegue processar mais 960.000 mensagems por segundo que o Node.js (baseado na V8 engine do Chromium)), os últimos modelos da OpenAI (GPT-4o no momento) e Upstash Redis.
- **Criação de Imagens** A Rosie é capaz de criar imagens espetaculares!
  <br>
  <br>

---

# Rosie: Exemplo de criação de imagem

<center>
 <img src="https://i.imgur.com/JSZTfba.png" class="rounded-md " width="400px">
</center>
---

# Projeto no.º 2: Menutree

O seu restaurante num link. Menos papéis, a apenas um QRCode de distância.

## O que é o Menutree?

O Menutree é uma plataforma online para restaurantes criarem os seus menus digitais e servi-los como QRCode como forma de economizar papéis e tornar a Terra mais sustentável.

## Motivação

A principal motivação por trás do Menutree é salvar a Terra. Nós usamos muitos papéis para imprimir os menus e alguns são mandados para o lixo após um único uso. Isso não é sustentável e tem um enorme impacto no meio ambiente.

---

# Menutree: Key features

- **Crie o seu próprio menu digital** - Utilize uma plataforma online ou um software específico para criar um menu digital para o seu restaurante, permitindo uma gestão fácil e rápida das opções oferecidas.

- **Adicione categorias e itens ao menu** - Organize o menu digital em categorias como entradas, pratos principais, sobremesas e bebidas, e adicione os itens correspondentes a cada categoria, incluindo descrições detalhadas e preços.

- **Adicione imagens aos itens** - Melhore a apresentação dos itens do menu adicionando imagens de alta qualidade, que ajudem a atrair a atenção dos clientes e a aumentar as vendas.

- **Crie um QRCode para o restaurante** - Gere um QRCode único que, quando escaneado, redireciona os clientes diretamente para o menu digital do seu restaurante.

- **Imprima o QRCode e coloque nas mesas** - Distribua os QR Codes impressos de forma estratégica, colocando-os em cada mesa do restaurante, para facilitar o acesso dos clientes ao menu digital.

- **Clientes podem dar scan ao QRCode e ver o menu nos seus telemóveis** - Os clientes podem usar os seus telemóveis para dar scan ao QRCode, proporcionando uma experiência de consulta ao menu rápida e sem contato, melhorando a conveniência e a segurança.
  <br>
  <br>

---

# Deployment

Todos os projetos da Blursed são hospedados no Fly.io. Fly dá-nos mais controlo sobre os nossos serviços, privacidade e segurança comparado com outro PaaS, por exemplo, a Vercel

Basta criar um container estilo este:

```docker {*|1|7|11|13}
FROM oven/bun:latest # A imagem do runtime Bun

WORKDIR /app

COPY package.json bun.lockb ./

RUN bun install --frozen-lockfile --production # Instalar as dependências

COPY . .

ENV NODE_ENV=production # Definir que o environment em que estamos é de produção

ENTRYPOINT [ "bun", "run", "index.ts" ] # Comando para executar o script
```

e executarmos um <span v-mark.circle.orange="1">simples</span> comando:

```sh
$ fly deploy
```

---

# Tecnologias

**Bun** / **Node.js** / **TypeScript** / **React/Next.js** / **OpenAI's GPT-4o** / **Upstash Redis** / **Docker/Colima** / **Tailwind CSS** / **PostgreSQL** / **Prisma** / **Radix UI** / **shadcn/ui** / **UploadThing** / **Auth.js**

---

# Fim

## Obrigado pelo vosso tempo e atenção.

<div class="w-60 relative">
  <div class="relative w-40 h-40">
    <img
      v-motion
      :initial="{ x: 600, y: 400, scale: 2, rotate: 100 }"
      :enter="final"
      class="absolute inset-0"
      src="https://github.com/blursed-org.png"
      alt=""
    />
  </div>

  <div
    class="text-5xl absolute top-14 left-40 text-[#ffffff] -z-1"
    v-motion
    :initial="{ x: -80, opacity: 0}"
    :enter="{ x: 0, opacity: 1, transition: { delay: 2000, duration: 1000 } }">
    blursed
  </div>
</div>

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/blursed-org" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
   <a href="https://www.instagram.com/blursed_org" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-instagram />
  </a>
</div>

<script setup lang="ts">
const final = {
  x: 0,
  y: 0,
  rotate: 0,
  scale: 1,
  transition: {
    type: 'spring',
    damping: 10,
    stiffness: 20,
    mass: 2
  }
}
</script>
