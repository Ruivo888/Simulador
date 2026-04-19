# Simulador de Fluxo Concatenado e Indução Mútua

**Desenvolvido por:** José Antonio Ruivo  
**Curso:** Engenharia Elétrica - FMU  
**Objetivo:** Visualização interativa de fenómenos eletromagnéticos para conversão de energia.

---

## 1. Sobre o Projeto
Este projeto é uma aplicação web interativa desenvolvida em **HTML5 Canvas** e **JavaScript**. O simulador permite visualizar conceitos abstratos do eletromagnetismo, como a formação do campo magnético em bobinas, a concatenação de fluxo e a indução de tensão baseada na variação temporal.



[Image of a solenoid magnetic field lines diagram]


## 2. Fundamentação Teórica

### Lei de Biot-Savart e Campo Magnético ($B$)
A simulação calcula a densidade de fluxo magnético baseada na corrente ($i$), no número de espiras ($N$) e na permeabilidade do meio ($\mu$):
$$B = \mu \cdot \frac{N \cdot i}{L}$$

### Fluxo Concatenado ($\lambda$)
Diferente do fluxo unitário ($\Phi$), o fluxo concatenado representa a soma total do fluxo que atravessa todas as espiras da bobina, sendo a base para o cálculo de indutância:
$$\lambda = N \cdot \Phi$$

### Lei de Faraday-Lenz
O motor físico do simulador deteta a variação de $\lambda$ no tempo ($dt$). Quando o utilizador altera a corrente bruscamente, o sistema calcula a Força Eletromotriz (FEM) induzida ($\epsilon$):
$$\epsilon = -\frac{d\lambda}{dt}$$
*O sinal negativo (Lei de Lenz) indica que a tensão induzida opõe-se à variação que a gerou.*

---

## 3. Funcionalidades e Controles

O simulador oferece quatro eixos de ajuste em tempo real:
1. **Corrente Bobina 1 ($i_1$):** Controla a intensidade e o sentido do campo magnético.
2. **Número de Espiras ($N$):** Altera a geometria da bobina e a magnitude do fluxo concatenado.
3. **Permeabilidade ($\mu$):** Simula a presença de diferentes materiais no núcleo (ex: ar vs. ferro).
4. **Indução Mútua:** Visualização das linhas de fluxo da Bobina 1 atravessando a Bobina 2, demonstrando o princípio dos transformadores.

---

## 4. Descrição Técnica do Código

### Estrutura de Renderização
* **Canvas API:** Utilizada para desenhar as bobinas e vetores. O ciclo de animação corre a **60 FPS** via `requestAnimationFrame`, garantindo fluidez.
* **Curvas de Bézier:** As linhas de campo magnético são calculadas matematicamente para simular a dispersão real de um solenoide.
* **Animação de Partículas:** O efeito de movimento nas linhas de fluxo é obtido através da manipulação do `lineDashOffset`, cuja velocidade é proporcional à intensidade da corrente.

### Lógica de Programação
O código foi estruturado de forma modular:
* `drawCoil()`: Renderiza a geometria das espiras.
* `drawFluxLines()`: Gera o campo magnético dinâmico.
* `animate()`: O loop principal que integra a física e a atualização da interface (DOM).

---

## 5. Como Executar
1. Faça o download do arquivo `index.html` deste repositório.
2. Abra o arquivo em qualquer navegador moderno (Chrome, Firefox, Edge ou Safari).
3. Não é necessária ligação à internet ou instalação de dependências.

---
*Este simulador faz parte do portfólio acadêmico de José Antonio Ruivo para a FMU.*
