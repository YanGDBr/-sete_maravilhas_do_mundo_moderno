# 🎨 Style Guide Sete Maravilhas Do Mundo Moderno

Este repositório serve como a "fonte da verdade" para o desenvolvimento do projeto. Abaixo estão as definições de arquitetura, padrões de escrita e estilos que devem ser seguidos por todos os colaboradores.

---

## 🏗️ Estrutura Base de Estilização

* **CSS Puro ou Bootstrap?** Utilizaremos **CSS Puro**. O objetivo é manter o código leve, sem dependências externas e com total controle sobre a especificidade.
* **Uso de `:root`?** Sim. Todas as variáveis globais (cores, espaçamentos e fontes) devem ser declaradas dentro do seletor `:root` para facilitar a manutenção.
* **Indentação:** Utilizaremos **4 espaços** tabs normais.
* **Comentários:** Devem ser usados para separar seções lógicas (ex: `/* --- Header Styles --- */`) ou para explicar "hacks" necessários para navegadores específicos.

---

## 🎨 Padrões de CSS

### 1. Metodologia BEM (Block, Element, Modifier)
Para evitar o "inferno da especificidade", adotamos o padrão BEM:
* **Block (`.block`):** Entidade independente (ex: `.card`, `.nav`).
* **Element (`.block__element`):** Parte de um bloco que não tem significado isolado (ex: `.card__title`).
* **Modifier (`.block--modifier`):** Uma flag que altera a aparência ou comportamento (ex: `.card--featured`).

### 2. Esquema de Cores
* **Nomenclatura:** Utilizaremos predominantemente **Hexadecimal** para cores sólidas. 
* **Transparências:** Caso precise de opacidade, utilizaremos **RGBA**.
* **Exemplo no `:root`:**
    ```css
    :root {
      --primary-color: #3498db;
      --secondary-color: #2ecc71;
      --overlay: rgba(0, 0, 0, 0.5);
    }
    ```

---

## ⚡ Padrões de JavaScript

### 1. Regras de Criação
* **Variáveis:** Utilize `const` por padrão. Use `let` apenas se a variável precisar de reatribuição. **Nunca use `var`**.
* **Funções:** Preferência por *Arrow Functions* para funções anônimas e callbacks. Funções nomeadas devem usar `camelCase`.
* **Classes:** Devem seguir o padrão `PascalCase` (ex: `class ShoppingCart`).
* **Objetos:** Devem ser declarados de forma literal e clara.
* **Comentários:** Use `//` para comentários rápidos e `/** ... */` (JSDoc) para documentar parâmetros de funções complexas.

### 2. Eventos de Clique
É estritamente **proibido** o uso de `onclick=""` diretamente no HTML. 
* **Padrão:** Todos os eventos devem ser vinculados via **`addEventListener`** no arquivo JavaScript externo, mantendo o HTML limpo e focado na estrutura.



---

## 🏗️ Estrutura HTML e Layout

### 1. Semântica e Organização
* **Tags Semânticas:** É obrigatório o uso de tags HTML5 (`<header>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<nav>`) para garantir acessibilidade e SEO.
* **Uso de `<br>`:** O uso da tag `<br>` é **proibido** para espaçamento visual. Deve-se utilizar propriedades CSS como `margin` ou `padding`..
* **Containers:** Utilizaremos uma estrutura de container centralizado para manter a consistência visual em telas largas.

### 2. Modelo de Layout: Fluido (Liquid)
Adotaremos o **Layout Fluido**. Diferente do layout fixo, o fluido utiliza unidades relativas (como `%`, `vw`, `vh`, `rem`) para se ajustar suavemente a diferentes larguras de tela.
* **Largura Máxima:** O conteúdo principal terá um `max-width` definido para evitar que as linhas de texto fiquem excessivamente longas em monitores UltraWide.



### 3. Responsividade e Breakpoints
O projeto não será limitado apenas a Mobile e Desktop. Utilizaremos uma estratégia de **breakpoints intermediários** inspirada no Bootstrap para garantir uma experiência fluida:

| Dispositivo | Breakpoint | Descrição |
| :--- | :--- | :--- |
| **Extra Small (xs)** | `< 576px` | Smartphones (Retrato) |
| **Small (sm)** | `≥ 576px` | Smartphones (Paisagem) |
| **Medium (md)** | `≥ 768px` | Tablets |
| **Large (lg)** | `≥ 992px` | Laptops/Desktops comuns |
| **Extra Large (xl)** | `≥ 1200px` | Desktops Grandes |

---

## 🗺️ Mapa do Site (Páginas)

Com base no tema "As Sete Maravilhas do Mundo Moderno", as seguintes páginas serão criadas:

1.  **Home (`index.html`):** Introdução geral, mapa mundi interativo e cards resumidos das 7 maravilhas.
2.  **Cristo Redentor (`cristo.html`):** História, localização e curiosidades (Brasil).
3.  **Grande Muralha da China (`muralha.html`):** Detalhes sobre a construção e extensão (China).
4.  **Petra (`petra.html`):** A cidade de pedra e sua arquitetura (Jordânia).
5.  **Coliseu (`coliseu.html`):** O anfiteatro romano e seu legado (Itália).
6.  **Chichén Itzá (`chichen-itza.html`):** A pirâmide maia e astronomia (México).
7.  **Machu Picchu (`machu-picchu.html`):** A cidade perdida dos Incas (Peru).
8.  **Taj Mahal (`taj-mahal.html`):** O monumento ao amor (Índia).
9.  **Sobre/Contato (`contato.html`):** Informações sobre os desenvolvedores e referências bibliográficas.

---

## 🎨 Identidade Visual e Cores

### 1. Referência de Design
O esqueleto e a disposição dos elementos devem seguir o protótipo definido no Excalidraw:
* 🔗 [Wireframe do Projeto - Excalidraw](https://excalidraw.com/#room=d586db1a3eeb33229b1f,SJJuOAth54-bO2rRylMwGg)

### 2. Paleta de Cores
Abaixo, cole a paleta definida no Adobe Color ou Realtime Colors:

> **[COLE AQUI SUA PALETA DE CORES OU O PRINT DO ADOBE COLOR]**
> Exemplo de aplicação sugerida:
> * **Primary:** #XXXXXX (Botões e Títulos)
> * **Secondary:** #XXXXXX (Destaques e Hovers)
> * **Background:** #XXXXXX (Fundo da página)
> * **Text:** #XXXXXX (Cor da fonte principal)
