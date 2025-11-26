# Rota Inteligente — MVP (Final da Jornada)

**Resumo rápido:** Projeto autoral de Helen Ortega — solução para reduzir deslocamento não remunerado do entregador no final do turno, sem aumentar a quilometragem paga nem alterar clientes/valores. MVP foca no *momento final da jornada* (última corrida).

---

## 🚩 Por que isso importa
Entregadores frequentemente terminam o turno longe de casa, acumulando quilômetros não remunerados. Mudando a **ordem final das entregas já aceitas** (sem alterar valores nem clientes) é possível reduzir esse deslocamento — gerando ganho direto para o entregador e benefício operacional para a plataforma.

---

## 📉 Exemplo de impacto (comparação)

| Métrica | Rota original | Rota IA | Diferença |
|---:|---:|---:|---:|
| Total percorrido | 31,0 km | 22,2 km | – 8,8 km |
| Km pagos | 20,0 km | 20,0 km | 0 |
| Km não pagos | 11,0 km | 2,2 km | – 8,8 km |
| Tempo após a rota | ~25 min | ~6 min | – 19 min |

**Interpretação:** A IA não altera o valor pago; altera a ordem das entregas aceitas para minimizar km não pago no fim do turno.

---

## 📂 Dados de exemplo
Os dados de exemplo estão nos arquivos:
- `rota_original.csv`  
- `rota_ajustada.csv`

### Prévia (dados de exemplo)

**Rota Original**

| Etapa | Origem | Destino | Distância (km) | Valor Recebido (R$) | Pago | Observações |
|------:|--------|---------|----------------:|---------------------:|:-----:|-------------|
| 1 | Casa (Rua Porto do Una 306) | Roldão Tiradentes | 2.0 | 6.00 | Sim |Deslocamento inicial (casa → mercado)|
| 2 | Roldão Tiradentes | José Bonifácio | 3.0 | 9.00 | Sim | Entrega 1 |
| 3 | José Bonifácio | Guaianases | 2.5 | 7.50 | Sim | Entrega 2 |
| 4 | Guaianases | Inácio Monteiro | 3.0 | 9.00 | Sim | Entrega 3 |
| 5 | Inácio Monteiro | Prestes Maia | 3.5 | 10.50 | Sim | Entrega 4 |
| 6 | Prestes Maia | São Mateus | 6.0 | 18.00 | Sim | Entrega 5 |
| TOTAL_PAGO | --- | --- | 20.0 | 60.00 | Sim | Total da rota |
| VOLTA_PARA_CASA | São Mateus | Casa (Rua Porto do Una 306) | 11.0 | 0.00 | Não | Deslocamento final não pago |

**Rota Ajustada**

| Etapa | Origem | Destino | Distância (km) | Valor Recebido (R$) | Pago | Observações |
|------:|--------|---------|----------------:|---------------------:|:-----:|-------------|
| 1 | Casa (Rua Porto do Una 306) | Roldão Tiradentes | 2.0 | 6.00 | Sim | Deslocamento inicial (casa → mercado) |
| 2 | Roldão Tiradentes | Inácio Monteiro | 4.0 | 12.00 | Sim | Entrega 1 |
| 3 | Inácio Monteiro | São Mateus | 4.0 | 12.00 | Sim | Entrega 2 |
| 4 | São Mateus | Guaianases | 4.0 | 12.00 | Sim | Entrega 3 |
| 5 | Guaianases | José Bonifácio | 3.0 | 9.00 | Sim | Entrega 4 |
| 6 | José Bonifácio | Jardim São Paulo | 3.0 | 9.00 | Sim | Entrega 5 (perto de casa) |
| TOTAL_PAGO | --- | --- | 20.0 | 60.00 | Sim | Total da rota |
| VOLTA_PARA_CASA | Jardim São Paulo | Casa (Rua Porto do Una 306) | 2.2 | 0.00 | Não | Deslocamento final não pago |

---

## 🎯 Fluxogramas (Estado atual & Solução proposta)

**Estado atual (pontos de dor)**
```mermaid
flowchart TD
  A[Tela: Pacote de entregas aceito] --> B[Ordem fixa apresentada ao entregador]
  B --> C[Entregador aceita sem reordenar]
  C --> D[Execução da rota conforme ordem]
  D --> E[Última entrega acontece (sem controle)]
  E --> F[Desfecho: entrega final longe de casa]

  subgraph DORES [Pontos de dor]
    G1[Km não pagos altos no final]
    G2[Falta de previsibilidade do fim do turno]
    G3[Desgaste físico e tempo perdido]
    G4[Risco de cancelamento/insatisfação]
    G5[App não usa histórico do entregador]
  end

  E --> G1
  E --> G2
  D --> G3
  C --> G4
  B --> G5
