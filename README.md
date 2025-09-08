## 📌 Descrição Geral

Este código implementa uma **hierarquia de classes em Kotlin** para simular o funcionamento de um telefone comum (`Phone`) e um telefone dobrável (`FoldablePhone`).
Ele demonstra conceitos de **orientação a objetos** como:

* **Herança** (`FoldablePhone` herda de `Phone`)
* **Sobrescrita de métodos** (`override`)
* **Encapsulamento de estado** (uso de variáveis de instância para controlar luz da tela e se o aparelho está dobrado)

---

## 📱 Classe `Phone`

Representa um **telefone básico** com uma tela que pode ser ligada e desligada.

### 🔹 Propriedades

* `isScreenLightOn: Boolean`

  * Define se a luz da tela do telefone está ligada (`true`) ou desligada (`false`).
  * Inicialmente `false` (tela apagada).

### 🔹 Métodos

* `open fun switchOn()`

  * Liga a tela do telefone, mudando `isScreenLightOn` para `true`.
  * É **aberto para sobrescrita** por classes filhas (`open`).

* `fun switchOff()`

  * Desliga a tela do telefone, mudando `isScreenLightOn` para `false`.

* `fun checkPhoneScreenLight()`

  * Verifica se a tela está ligada ou desligada.
  * Exibe no console:

    * `"The phone screen's light is on."` se ligada.
    * `"The phone screen's light is off."` se desligada.

---

## 📱📂 Classe `FoldablePhone`

Representa um **telefone dobrável** que herda da classe `Phone`.
Adiciona o comportamento de **dobrar e desdobrar** o aparelho.

### 🔹 Propriedades

* `isFolded: Boolean`

  * Indica se o telefone está dobrado (`true`) ou desdobrado (`false`).
  * Inicialmente `true` (dobrado).

### 🔹 Métodos

* `override fun switchOn()`

  * Liga a tela **apenas se o telefone estiver desdobrado** (`isFolded == false`).
  * Caso contrário, a tela permanece apagada.

* `fun fold()`

  * Dobra o telefone, definindo `isFolded = true`.

* `fun unfold()`

  * Desdobra o telefone, definindo `isFolded = false`.

---

## 🏃 Função `main`

Simula o uso do telefone dobrável (`FoldablePhone`):

1. Cria um objeto `foldablePhone` (inicialmente dobrado e tela desligada).
2. Tenta ligar a tela enquanto dobrado → não funciona, tela permanece apagada.
3. Exibe o estado da tela (`off`).
4. Desdobra o telefone (`unfold()`).
5. Liga a tela novamente → agora funciona, pois o telefone está desdobrado.
6. Exibe o estado da tela (`on`).

### 🔹 Saída Esperada no Console

```
The phone screen's light is off.
The phone screen's light is on.
```

---
