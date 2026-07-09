# Trabalho Final - Snakes and Ladders (COCADA 2025.2)

Este repositório armazena o projeto final da disciplina de Computação Científica e Análise de Dados (COCADA) da UFRJ, desenvolvido por Nicholas de Araujo Figueira. A análise completa está detalhada no relatório (Projeto Final - Cocada.pdf) e a implementação computacional pode ser executada no notebook (Trabalho_Final_Cocada.ipynb).

O trabalho realiza a modelagem computacional do jogo *Snakes and Ladders* (Cobras e Escadas) utilizando Cadeias de Markov de estados finitos, dividida em três frentes:

1. **Tempo Médio de Vitória**: O tabuleiro de 100 casas é representado por uma Matriz de Probabilidade de Transição (TPM) de dimensão $100 \times 100$. A última casa atua como um estado absorvente. O tempo médio esperado para a vitória ($e$) a partir de qualquer casa é calculado pelo sistema linear $(I - Q)e = \mathbf{1}$, resolvido via fatoração LU. A partir da Casa 0, o tempo médio para a vitória é de **34,87 jogadas**.
2. **Velocidade de Convergência (Autovalores)**: A análise espectral da submatriz transiente $Q$ revelou um autovalor dominante de $|\lambda_{dom}| = 0,9564$. Esse valor indica que, assintoticamente, $95,6\%$ da probabilidade de o jogo continuar "resta" no sistema a cada rodada. Cobras longas próximas ao final do tabuleiro, como as transições (97-78) e (95-56), criam gargalos probabilísticos que elevam esse autovalor e retardam o encerramento do jogo.
3. **Clusterização de Partidas (PCA + K-Means)**: Foram simuladas rodadas de Monte Carlo para gerar dados de partidas reais. Aplicou-se o algoritmo PCA para redução de dimensionalidade e K-Means para agrupar os caminhos em três perfis distintos de comportamento, separando partidas curtas (alta sorte) de partidas longas (alta incidência de cobras).

O projeto conta com visualizações gráficas essenciais: o *Spy Plot* (esparsidade da matriz de transição), o *Heatmap de Dificuldade* (tempo esperado até a vitória projetado no tabuleiro), o *Espectro de Autovalores* (plano complexo) e o gráfico de *Clusterização*.
