## 📉 Comparação geral das rotas (em KM)

Antes de analisar os números, é importante explicar como defini o **valor de referência por quilômetro**.

### 📌 Como estimei o valor por quilômetro

O iFood não informa oficialmente quanto paga por km, mas como entregadora na Zona Leste observei um padrão constante no dia a dia:  
as rotas mais equilibradas financeiramente costumam se aproximar de **R$ 3,00 por km pago**.

Essa estimativa veio de:

- dezenas de entregas analisadas em horários diferentes  
- regiões como Guaianazes, Tiradentes, Inácio Monteiro, José Bonifácio, Prestes Maia e São Mateus  
- comparação entre pacotes com valores semelhantes  

Ou seja, não é um valor fixo, mas uma **métrica prática e realista** para entender o impacto dos quilômetros não pagos.  
Ainda assim, toda a análise deste projeto foca **em quilômetros**, não em dinheiro.

---

## 📊 Tabela comparativa das rotas

| Métrica | Rota original | Rota IA | Diferença |
|--------|---------------|---------|-----------|
| **Total percorrido** | **31,0 km** | **22,2 km** | **– 8,8 km** |
| **Km pagos** | 20,0 km | 20,0 km | 0 |
| **Km não pagos** | **11,0 km** | **2,2 km** | **– 8,8 km** |
| **Km economizados (não remunerados)** | 0 | **8,8 km** | 0 |
| **Tempo após a rota** | ~25 min | ~6 min | **– 19 min** |

---

## 🧠 Como interpretar essa comparação

A IA **não altera a rota**, o valor pago e nem os 20 km remunerados.  
O que muda é **apenas a ordem das entregas** já aceitas.

E essa pequena mudança altera muito o resultado final:

- Na rota original, a última entrega é em **São Mateus**, deixando **11 km** até a minha casa (escolha como rota final) todos não pagos.  
- Na rota otimizada, a última entrega é no **Jardim São Paulo**, resultando em apenas **2,2 km** não pagos da rota final escolhida.  

Isso significa:

👉 **8,8 km de deslocamento não remunerado evitado**,  
👉 **menos cansaço**,  
👉 **menos perda de tempo**,  
👉 **menos gasto com combustível**,  
👉 **e uma finalização de rota mais humana e justa**.

É exatamente o tipo de diferença que afeta a rotina de qualquer entregador que roda todos os dias.

---

## 💡 Possibilidade de melhoria no app: ajustar a ordem da rota

Um ponto que observo diariamente na operação é a falta de opção para **alterar a ordem das entregas que já fazem parte do pacote**.

Não estou falando sobre escolher bairro ou decidir onde trabalhar.  
Estou falando de algo simples:

➡️ **reorganizar a sequência das entregas já aceitas**,  
➡️ **sem mudar o valor**,  
➡️ **sem mudar os clientes**,  
➡️ **sem mudar a distância paga**,  
➡️ **sem interferir na operação do mercado**.

Hoje, o entregador aceita um conjunto de pedidos e só descobre onde vai terminar depois que já está no meio da rota.

Se o app permitisse apenas mudar **o pedido final**, mantendo todo o restante igual, seria possível:

- terminar mais perto de casa  
- reduzir deslocamentos não pagos  
- evitar perda de tempo no fim do expediente  
- diminuir desgaste físico e estresse  

Este projeto demonstra exatamente isso:  
uma simples troca na ordem final evita **8,8 km não remunerados**.

Essa funcionalidade agregaria qualidade de vida para quem está na rua, sem alterar prazos, clientes ou logística.

---

## ⭐ Por que essa visão é importante

Essa análise fala a linguagem do entregador, não só dos dados:

- **Vou terminar longe de casa?**  
- **Quanto vou andar sem receber?**  
- **Compensa aceitar essa rota?**  
- **A rota realmente vale o valor que aparece?**

Ajustar a ordem da entrega é uma pequena melhoria que geraria um impacto enorme.  
E este projeto mostra exatamente como isso pode ser pensado com IA — mostrando um problema real, vivido na prática, traduzido em números concretos e em uma solução possível.

