# Agente de IA para Super Mario Bros com Aprendizado por Reforço

[cite\_start]Este projeto desenvolve um agente de inteligência artificial capaz de aprender a jogar o clássico Super Mario Bros. do zero, utilizando técnicas de Aprendizado por Reforço (Reinforcement Learning). [cite: 3] [cite\_start]O objetivo final é treinar um modelo que consiga avançar o máximo possível nas fases do jogo, maximizando sua pontuação e evitando obstáculos de forma autônoma. [cite: 5]

[cite\_start]O agente aprende por tentativa e erro, interagindo com o ambiente do jogo e recebendo "recompensas" por ações bem-sucedidas, como avançar para a direita, e "punições" por ações ruins, como morrer. [cite: 4, 14]

## 🧠 Conceitos Fundamentais

O projeto é baseado nos seguintes conceitos de Aprendizado por Reforço:

  * **Agente**: O nosso "robô" ou cérebro, que é uma Rede Neural Convolucional (CNN) responsável por tomar as decisões (ações) dentro do jogo. 
  * **Ambiente**: O próprio jogo Super Mario Bros emulado, com suas regras, fases e inimigos. O ambiente fornece ao agente o estado atual da tela e uma recompensa após cada ação. 
  * **Estado**: Uma "fotografia" da tela do jogo em um determinado momento, representada pelos pixels da imagem. Para dar ao agente a noção de movimento, nós empilhamos 4 frames consecutivos como um único estado.
  * **Ações**: As decisões que o agente pode tomar, como andar para a direita, pular ou correr. Para simplificar, utilizamos um conjunto reduzido de 7 ações essenciais. 
  * **Recompensa**: Um sinal numérico que o ambiente envia ao agente. A recompensa padrão premia o avanço para a direita, penaliza o tempo e a morte do personagem. 

## 🛠️ Tecnologias e Bibliotecas

Este projeto foi construído utilizando Python 3.7 e um conjunto específico de bibliotecas para garantir a compatibilidade.

  * [cite\_start]**Stable-Baselines3 (v1.8.0)**: O framework de alto nível que contém a implementação do algoritmo de aprendizado **PPO (Proximal Policy Optimization)**. [cite: 25, 36]
  * **Gym (v0.21.0)**: O "ginásio" que fornece a interface padrão para comunicação entre o agente e o ambiente.
  * [cite\_start]**gym-super-mario-bros**: A biblioteca que encapsula o emulador do Super Mario Bros como um ambiente Gym. [cite: 37]
  * **NumPy (v1.21.6)**: Biblioteca fundamental para todos os cálculos numéricos e manipulação dos frames do jogo.
  * [cite\_start]**OpenCV-Python**: Utilizada para o pré-processamento das imagens (redimensionamento e conversão para tons de cinza). [cite: 38]
  * **TensorBoard**: Ferramenta para visualizar as métricas e o progresso do treinamento em tempo real.

## 🚀 Como Executar o Projeto

Para replicar este projeto, siga os passos abaixo.

### 1\. Pré-requisitos

  * **Anaconda (ou Miniconda)** instalado para gerenciar o ambiente virtual.
  * **Python 3.7**.
  * [cite\_start]**Visual Studio (Community Edition)** com a carga de trabalho "Desenvolvimento para desktop com C++" (necessário no Windows para compilar uma das dependências). [cite: 39]

### 2\. Configuração do Ambiente

Primeiro, crie um ambiente virtual e instale todas as dependências a partir do arquivo `requirements.txt`.

```bash
# Crie e ative um novo ambiente com Python 3.7
conda create -n mario-ia python=3.7
conda activate mario-ia

# Instale todas as bibliotecas necessárias de uma vez
pip install -r requirements.txt
```

**Conteúdo do arquivo `requirements.txt`:**

```
# Framework de Aprendizado por Reforço (versão antiga e estável)
stable-baselines3==1.8.0

# Padrão de ambiente de treinamento (versão clássica)
gym==0.21.0

# Biblioteca para o ambiente do jogo Super Mario Bros
gym-super-mario-bros

# Processamento de imagem (usado pelos wrappers)
opencv-python

# Cálculos numéricos (versão compatível com Python 3.7 e a pilha acima)
numpy==1.21.6

# Dependência do Gym 0.21.0 para gerenciamento de plugins
importlib-metadata==4.13.0

# Para visualização e monitoramento do treinamento
tensorboard

# Ambiente de desenvolvimento interativo
jupyter
```

### 3\. Treinando o Agente

Para iniciar um novo treinamento, execute o script `treinamento.py`. O progresso será salvo periodicamente na pasta `./train/`.

```bash
python treinamento.py
```

### 4\. Testando o Agente

Para assistir a um agente já treinado jogando, execute o script `teste.py`. Lembre-se de alterar o nome do arquivo `.zip` dentro do script para carregar o modelo desejado.

```bash
python teste.py
```
