# Projeto de IHC: Acessibilidade - Perceptível (Contraste e Cores)

**Grupo:** 02

**Integrantes:**
<table>
  <tr>
<td align="center"><a href="https://github.com/arthurevg"><img style="border-radius: 50%;" src="https://github.com/arthurevg.png" width="100px;" alt=""/><br /><sub><b>Arthur Evangelista</b></sub></a><br/>
<td align="center"><a href="https://github.com/caio-venancio"><img style="border-radius: 50%;" src="https://github.com/caio-venancio.png" width="100px;" alt=""/><br /><sub><b>Caio Venâncio</b></sub></a><br/>
<td align="center"><a href="https://github.com/brunocrzz"><img style="border-radius: 50%;" src="https://github.com/brunocrzz.png" width="100px;" alt=""/><br /><sub><b>Bruno Cruz</b></sub></a><br/>
<td align="center"><a href="https://github.com/fabioaletorres"><img style="border-radius: 50%;" src="https://github.com/fabioaletorres.png" width="100px;" alt=""/><br /><sub><b>Fabio Torres</b></sub></a><br/>
<td align="center"><a href="https://github.com/Faehzin"><img style="border-radius: 50%;" src="https://github.com/Faehzin.png" width="100px;" alt=""/><br /><sub><b>Gabriel Sampaio</b></sub></a><br />   
  </tr>
  </table>

---

## Critérios WCAG 2.2 Implementados

Nosso projeto foca na implementação de diretrizes WCAG (Web Content Accessibility Guidelines) 2.2 relacionadas à percepção visual do conteúdo, especificamente em **Contraste e Cores**. Abordamos os seguintes critérios:

### 1. Critério 1.4.1: Uso da Cor (Nível A)

* **O que significa:** Este critério garante que a cor não seja o único meio visual para transmitir informações, indicar ações ou diferenciar elementos. É fundamental que haja alternativas não-visuais para a cor.
* **Implementação no código:**
    * **Links Sublinhados:** Todos os links (tag `<a>`) possuem um sublinhado (ou um indicador visual similar, como uma linha pontilhada que se torna sólida ao passar o mouse) que os distingue do texto comum, mesmo que a cor seja a mesma. Isso é crucial para usuários daltônicos ou com baixa visão que podem não perceber a mudança de cor.
    * **Mensagens de Feedback (Formulário):** As mensagens de sucesso (verde) e erro (vermelho) no formulário prático não dependem apenas da cor. Elas também incluem **texto explícito** ("Sucesso:", "Erro:") e são apresentadas com um **fundo contrastante** para garantir que a informação seja compreendida independentemente da percepção da cor.
    * **Indicação de Campo Obrigatório:** No exemplo do formulário, campos que poderiam ser indicados apenas por cor (como um asterisco vermelho) são complementados com o atributo `required` no HTML e, em cenários reais, poderiam ter texto adicional como "(Obrigatório)" para reforçar a informação.

### 2. Critério 1.4.3: Contraste Mínimo (Nível AA)

* **O que significa:** Este critério estabelece requisitos mínimos de contraste de cores entre o texto e o seu fundo para garantir legibilidade para pessoas com deficiência visual (como baixa visão ou algumas formas de daltonismo).
    * Para **texto normal**, a taxa de contraste deve ser de no mínimo **4.5:1**.
    * Para **texto grande** (18pt ou 14pt em negrito), a taxa de contraste deve ser de no mínimo **3:1**.
* **Implementação no código:**
    * **Design Responsivo a Temas:** O código implementa dois temas (claro e escuro) que podem ser alternados. As variáveis CSS (`--cor-fundo-claro`, `--cor-texto-claro`, `--cor-fundo-escuro`, `--cor-texto-escuro`) foram escolhidas para tentar garantir que o contraste de texto/fundo atenda ou exceda os requisitos de 4.5:1 em ambos os temas.
    * **Exemplos Diretos:** A seção "Critério 1.4.3" demonstra visualmente exemplos de texto com "Contraste Suficiente" e "Baixo Contraste" para ilustrar a importância deste critério.
    * **Feedback do Formulário:** As mensagens de sucesso/erro e seus respectivos fundos foram definidos com cores que garantem um contraste adequado, independentemente do tema selecionado.

### 3. Critério 1.4.11: Contraste de Conteúdo Não Textual (Nível AA)

* **O que significa:** Este critério se aplica ao contraste de elementos gráficos essenciais para a compreensão do conteúdo ou para a funcionalidade da interface do usuário. Estes elementos devem ter uma taxa de contraste de no mínimo **3:1** com as cores adjacentes. Isso inclui bordas de campos de entrada, ícones essenciais, indicadores de foco e estados de componentes (como o "checked" de um checkbox).
* **Implementação no código:**
    * **Bordas de Campos de Formulário:** As bordas dos campos `input` e `textarea` no formulário prático foram definidas com cores que mudam de acordo com o tema, garantindo um contraste mínimo de 3:1 em relação ao fundo do campo e ao fundo da seção. Isso assegura que os limites dos campos sejam claramente visíveis.
    * **Indicadores de Foco (`:focus-visible`):** Implementamos um anel de foco claro (azul vibrante) que aparece ao redor de elementos interativos (links, botões, campos de formulário) quando navegados via teclado. Este indicador de foco possui contraste suficiente com o fundo para ser facilmente perceptível, crucial para usuários que não usam mouse.
    * **Elementos Gráficos de Exemplo:** A seção "Critério 1.4.11" exibe círculos coloridos que simulam componentes gráficos. As cores usadas nesses círculos demonstram visivelmente o conceito de contraste necessário para elementos não textuais.

---

## Importância dos Critérios e Público-Alvo

A implementação desses critérios WCAG é fundamental para construir uma web mais inclusiva e acessível para todos.

* **Critério 1.4.1 (Uso da Cor):**
    * **Importância:** Evita que a informação seja perdida para usuários que não conseguem discernir cores (como pessoas daltônicas) ou que usam dispositivos que exibem cores de forma diferente (monitores em preto e branco, leitores de tela que não transmitem cor).
    * **Público-alvo:** Principalmente pessoas com **daltonismo** (cegueira para cores), **baixa visão**, e usuários de **leitores de tela** ou **dispositivos monocromáticos**.

* **Critério 1.4.3 (Contraste Mínimo):**
    * **Importância:** Garante que o texto seja legível e discernível para a grande maioria dos usuários, reduzindo o esforço cognitivo e a fadiga ocular. Sem contraste adequado, o texto pode se misturar ao fundo, tornando-se ilegível.
    * **Público-alvo:** Pessoas com **baixa visão** (incluindo idosos com presbiopia), algumas formas de **daltonismo**, e qualquer pessoa em condições de **pouca luz** ou usando telas de **baixa qualidade/brilho**.

* **Critério 1.4.11 (Contraste de Conteúdo Não Textual):**
    * **Importância:** Permite que usuários com deficiência visual percebam e interajam com componentes importantes da interface (botões, campos, ícones) e gráficos informativos. Se esses elementos não tiverem contraste, eles podem ser "invisíveis" funcionalmente.
    * **Público-alvo:** Pessoas com **baixa visão**, usuários de **navegação por teclado** (que dependem do indicador de foco), e usuários de **dispositivos com telas de baixa qualidade**.

---

## Técnicas de Programação Utilizadas

Para implementar os critérios WCAG 2.2 focados em contraste e cores, utilizamos as seguintes técnicas de programação:

1.  **HTML Semântico:**
    * Uso de tags HTML semanticamente corretas (`<header>`, `<main>`, `<section>`, `<form>`, `<label>`, `<input>`, `<button>`, `<ul>`, `<li>`) para estruturar o conteúdo. Isso não só organiza o código, mas também fornece um contexto importante para tecnologias assistivas (como leitores de tela).
    * Atributos como `required` e `aria-required="true"` em campos de formulário para indicar sua obrigatoriedade de forma programática.
    * Associação explícita de `<label>` com `<input>` via atributos `for` e `id` para garantir que o propósito do campo seja claro para todos os usuários.

2.  **CSS com Variáveis (Custom Properties):**
    * Definição de cores utilizando **variáveis CSS** (`--cor-fundo-claro`, `--cor-texto-claro`, `--cor-destaque`, etc.) dentro do seletor `:root`. Isso permitiu a criação de um sistema de cores robusto e fácil de gerenciar.
    * **Temas Claro e Escuro:** A alternância de tema é controlada pela adição/remoção de classes (`.tema-claro` e `.tema-escuro`) na tag `<body>`. As variáveis CSS são então redefinidas ou utilizadas de forma diferente sob essas classes, permitindo que as cores de fundo, texto, bordas e outros elementos se ajustem automaticamente para manter o contraste em ambos os temas.
    * **Contraste de Borda:** As bordas dos campos de formulário e dos separadores de lista (`border-bottom`) foram estilizadas usando variáveis de cor específicas para o tema atual (`--cor-borda-claro`, `--cor-borda-escuro`), garantindo um contraste mínimo de 3:1 para elementos não textuais.
    * **Indicadores de Foco:** O pseudosseletor CSS `:focus-visible` foi usado para criar um indicador de foco claro e personalizado (um `box-shadow` colorido) para elementos interativos quando navegados via teclado. Isso substitui o `outline` padrão do navegador, que muitas vezes não tem contraste suficiente.

3.  **JavaScript para Interatividade:**
    * **Alternância de Tema:** Um script JavaScript simples (`toggleTheme()`) é responsável por adicionar/remover as classes `.tema-claro` e `.tema-escuro` do `<body>` ao clicar no botão.
    * **Persistência do Tema:** Utilizamos `localStorage` (`localStorage.setItem('theme', 'dark')`) para salvar a preferência de tema do usuário. Ao recarregar a página, o JavaScript verifica essa preferência e aplica o tema salvo, proporcionando uma experiência consistente.
    * **Validação e Feedback do Formulário:** O JavaScript simula a validação de um formulário (`contactForm`). Ao detectar erros de preenchimento, ele adiciona as classes CSS (`.show`, `.error` ou `.success`) e insere uma mensagem de feedback textual, que é colorida (verde para sucesso, vermelho para erro) e tem um fundo contrastante para reforçar a informação visualmente.

4.  **Uso de Fontes Web:**
    * Importação de fontes do Google Fonts (`Open Sans`, `Segoe UI`) para melhorar a estética sem comprometer a legibilidade.

---

## Como Rodar o Código

Para visualizar e testar o projeto no seu computador, siga os passos abaixo:

1.  **Baixe ou Clone o Repositório:**
    * Se você baixou o arquivo ZIP do GitHub, descompacte-o em uma pasta no seu computador.
    * Se você está usando Git, pode clonar o repositório com o comando:
        ```bash
        git clone https://github.com/arthurevg/ContrasteECoresWCAG.git
        ```
        Em seguida, navegue até a pasta do projeto:
        ```bash
        cd ContrasteECoresWCAG
        ```

2.  **Abra o Arquivo HTML:**
    * Localize o arquivo principal `index.html` dentro da pasta do projeto.
    * Dê um **clique duplo** no arquivo. Ele será aberto automaticamente no seu navegador de internet padrão (Google Chrome, Mozilla Firefox, Microsoft Edge, Safari, etc.).

3.  **Interaja com a Página:**
    * **Alternar Tema:** Clique no botão "Alternar Tema (Claro/Escuro)" no cabeçalho para ver como o contraste e as cores se adaptam em ambos os modos.
    * **Exemplos de Contraste:** Observe os blocos de texto e os círculos gráficos nas seções "Critério 1.4.3" e "Critério 1.4.11" para visualizar as diferenças de contraste.
    * **Formulário de Contato:**
        * Tente enviar o formulário sem preencher todos os campos ou sem aceitar os termos para ver a mensagem de **erro** (vermelha, com texto e fundo contrastante).
        * Preencha todos os campos e aceite os termos, e então envie o formulário para ver a mensagem de **sucesso** (verde, com texto e fundo contrastante).
        * Navegue pelo formulário usando a **tecla Tab** para observar o indicador de foco claro nos campos e no botão.