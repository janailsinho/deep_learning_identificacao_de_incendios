# Identificação de Incêndios Florestais utilizando Deep Learning

Projeto desenvolvido para a disciplina **IF867** do Centro de Informática (CIn) da Universidade Federal de Pernambuco (UFPE).

Autor: José Janailson de Arruda Cunha

---

## 📌 Sobre o Projeto
A detecção precoce de incêndios é crucial para mitigar os danos causados por esses eventos em áreas florestais, industriais ou residenciais. Este projeto implementa e compara diferentes arquiteturas de Redes Neurais Convolucionais (CNNs) e abordagens de *Transfer Learning* para classificar imagens em duas categorias: **com fogo** e **sem fogo**.

---

## 📊 Base de Dados
O conjunto de dados utilizado é o **Forest Fire BigData**, disponível no [Kaggle](https://www.kaggle.com/datasets/mohammedborhanuddin/forest-fire-bigdata). 
* **Total de imagens:** 1.842
* **Conjunto de Treino:** 1.475 imagens (80%)
* **Conjunto de Validação:** 367 imagens (20%)
* **Classes:** `fire_images` e `non_fire_images`

As imagens foram redimensionadas para `128x128` pixels e normalizadas com escala de `0 a 1`.

---

## 🚀 Modelos Avaliados
1. **CNN Simples (Baseline):** Construída do zero com 2 blocos convolucionais, camadas de *MaxPooling*, *Dropout* e densas.
2. **VGG16 (Transfer Learning):** Rede pré-treinada no ImageNet com camadas convolucionais congeladas e novas camadas densas ajustadas.
3. **ResNet50 (Transfer Learning):** Arquitetura com conexões residuais (*skip connections*) para facilitar o fluxo de gradientes.
4. **MobileNet (Transfer Learning):** Modelo leve e otimizado para eficiência, utilizando convoluções separáveis em profundidade.

---

## 📈 Resultados Principais

| Modelo | Acurácia de Treino | Acurácia de Validação | AUC |
| :--- | :---: | :---: | :---: |
| **CNN Simples** | 97.32% | 92.10% | 0.495 |
| **VGG16** | 98.92% | 94.28% | 0.485 |
| **ResNet50** | 87.58% | 90.46% | 0.583 |
| **MobileNet** | **99.48%** | **97.82%** | 0.506 |

* **D destaque:** O **MobileNet** apresentou o melhor desempenho geral, alcançando uma acurácia de validação de **97.82%**, sendo a opção mais eficiente para esta tarefa.

---

## 🛠️ Tecnologias Utilizadas
* Python
* TensorFlow / Keras
* Scikit-Learn
* Matplotlib
* Google Colab

---

## 📚 Referências
* [Dive into Deep Learning](https://d2l.ai/)
* [Kaggle Dataset - Forest Fire BigData](https://www.kaggle.com/datasets/mohammedborhanuddin/forest-fire-bigdata)
* TensorFlow Documentation & Keras Library
