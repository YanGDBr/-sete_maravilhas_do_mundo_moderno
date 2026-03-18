# -sete_maravilhas_do_mundo_moderno
# 🎨 Style Guide sete_maravilhas_do_mundo_moderno

Este repositório serve como a "fonte da verdade" para o desenvolvimento do projeto. Abaixo estão as definições de arquitetura, padrões de escrita e estilos que devem ser seguidos por todos os colaboradores.

---

## 🏗️ Estrutura Base de Estilização

* **CSS Puro ou Bootstrap?** Utilizaremos **CSS Puro**. O objetivo é manter o código leve, sem dependências externas e com total controle sobre a especificidade.
* **Uso de `:root`?** Sim. Todas as variáveis globais (cores, espaçamentos e fontes) devem ser declaradas dentro do seletor `:root` para facilitar a manutenção.
* **Indentação:** Utilizaremos **2 espaços** (Soft Tabs) em vez de tabs.
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

https://excalidraw.com/#room=d586db1a3eeb33229b1f,SJJuOAth54-bO2rRylMwGg

```javascript
// Exemplo correto
const btnSubmit = document.querySelector('.form__button--submit');

btnSubmit.addEventListener('click', (event) => {
  event.preventDefault();
  // lógica aqui
});
