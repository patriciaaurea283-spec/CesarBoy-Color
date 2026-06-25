# 🎮CESAR Boy

Sobre - 
O Space Invaders no ESP32 é um jogo arcade baseado no clássico absoluto dos videogames, totalmente desenvolvido para rodar de forma embarcada. O projeto combina a alta capacidade de processamento do microcontrolador ESP32 com a velocidade de atualização de um display LCD TFT colorido controlado pelo driver ST7789.  O sistema foi projetado para gerenciar, em tempo real, a lógica completa de estados do jogo, análise geométrica de colisões, movimentação sincronizada da frota inimiga e o controle simultâneo de múltiplos projéteis na tela. Tudo isso acionado por botões físicos configurados diretamente no microcontrolador, entregando uma experiência nostálgica, responsiva e de baixo custo.

- Objetivo do Projeto
O principal objetivo do projeto é implementar uma versão totalmente funcional e fluida de Space Invaders, alcançando uma taxa de quadros estável de aproximadamente 30 FPS sem depender de nenhum hardware externo complexo de processamento gráfico.  Além disso, o projeto visa aplicar e consolidar conceitos práticos de:Programação em C++ voltada para arquiteturas de microcontroladores de alta performance (ESP32);  Otimização gráfica de baixo nível e manipulação seletiva de buffers em displays TFT;  Implementação de algoritmos de colisão por hitboxes e gerenciamento matricial de entidades;  Integração direta entre hardware e software através de varredura de entradas digitais.

- Como o Sistema Funciona.
  
Ao energizar o sistema, o ESP32 inicializa a comunicação com o display ST7789 utilizando o barramento periférico de alta velocidade VSPI. Os pinos conectados aos botões de controle são configurados com resistores internos de Pull-Up ativos, dispensando componentes externos para estabilização de sinal.  A arquitetura do software é baseada em um Game Loop síncrono controlado de forma estrita pelo tempo de execução de milissegundos não bloqueantes (millis()), o que elimina atrasos estruturais prejudiciais (delay()). A cada ciclo, o sistema processa as seguintes etapas de forma coordenada:  Processamento de Entradas: Lê o estado lógico dos botões físicos para mover a nave para a esquerda ou direita e computar os comandos de disparo;  Cálculo Vetorial: Atualiza a translação física ascendente dos projéteis do jogador e a movimentação descendente dos contra-ataques inimigos;  Gerenciamento da Frota: Desloca a matriz de alienígenas em bloco pelas laterais e força a descida da linha sempre que a borda da tela é atingida;  Análise de Colisões: Varre a área geométrica dos elementos ativos para validar os impactos e atualizar as vidas do jogador e a pontuação global;  Renderização Otimizada: Atualiza apenas as regiões alteradas da tela para suprimir artefatos visuais de rastro e manter o desempenho estável.  O jogo segue ativo enquanto o jogador possuir vidas e a frota alienígena não invadir o solo. Caso todas as naves inimigas sejam eliminadas, a tela exibe a mensagem de vitória.

- Componentes do Projeto.

| Eletrônicos:1x Placa de desenvolvimento ESP32 DevKitC (Dual-Core Tensilica LX6, 240MHz);  1x Módulo Display LCD TFT Colorido de 1.3" ou 1.54" com controlador ST7789 (Resolução de 240x240 pixels via interface SPI);  3x Botões do tipo Push Button de quatro pinos (Configurados para movimentação e ação de tiro);  1x Protoboard para montagem rápida do circuito;  Jumpers de conexão do tipo macho-fêmea e macho-macho. 

- Resultado Esperado:
Criar um console arcade de bolso totalmente funcional, robusto e de baixo custo. O dispositivo será capaz de rodar o clássico Space Invaders a estáveis 30 FPS, provando que conceitos eficientes de software e tratamento geométrico conseguem extrair gráficos fluidos diretamente de um microcontrolador embarcado.

Link do vídeo sobre nosso projeto: https://canva.link/w89em01f1gehbxx
