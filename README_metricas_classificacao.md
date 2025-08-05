# 📊 Projeto: Cálculo de Métricas de Avaliação para Classificação

Este projeto demonstra o cálculo manual das principais **métricas de avaliação** utilizadas em algoritmos de **classificação binária**, com base em uma **matriz de confusão arbitrária**.

---

## ✅ Métricas Implementadas

| Métrica         | Fórmula |
|------------------|---------|
| **Acurácia**     | (VP + VN) / (VP + VN + FP + FN) |
| **Sensibilidade** (Recall) | VP / (VP + FN) |
| **Especificidade** | VN / (VN + FP) |
| **Precisão**     | VP / (VP + FP) |
| **F1-Score**     | 2 × (Precisão × Recall) / (Precisão + Recall) |

---

## 📦 Exemplo de Matriz de Confusão

|                | Predito Positivo | Predito Negativo |
|----------------|------------------|------------------|
| Real Positivo  | VP = 50          | FN = 10          |
| Real Negativo  | FP = 5           | VN = 35          |

---

## 🧠 Código Python

```python
def calcular_metricas(vp, vn, fp, fn):
    total = vp + vn + fp + fn

    acuracia = (vp + vn) / total if total > 0 else 0
    sensibilidade = vp / (vp + fn) if (vp + fn) > 0 else 0
    especificidade = vn / (vn + fp) if (vn + fp) > 0 else 0
    precisao = vp / (vp + fp) if (vp + fp) > 0 else 0
    f1_score = (2 * precisao * sensibilidade) / (precisao + sensibilidade) if (precisao + sensibilidade) > 0 else 0

    return {
        "Acurácia": round(acuracia, 4),
        "Sensibilidade (Recall)": round(sensibilidade, 4),
        "Especificidade": round(especificidade, 4),
        "Precisão": round(precisao, 4),
        "F1-Score": round(f1_score, 4)
    }

# Exemplo
vp, vn, fp, fn = 50, 35, 5, 10
metricas = calcular_metricas(vp, vn, fp, fn)

for nome, valor in metricas.items():
    print(f"{nome}: {valor}")
```

---

## 📥 Requisitos

```bash
pip install jupyter notebook
```

