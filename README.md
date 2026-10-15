# Reconhecedor de Datilologia em Libras

Aplicação web que reconhece, em tempo real e pela webcam, as letras do alfabeto manual de Libras (datilologia) e as transforma em palavras que podem ser lidas na tela e em voz alta.

> **Status:** Semana 1 (DSAIA) — da ideia ao repositório. Ainda não há aplicação funcional; este repositório registra a proposta e a base para as próximas fases.

## Dupla

- _Kauan Moreira Petro_
- _Thauan Pereira Gomes_

## Descrição da ideia

Pessoas surdas que usam Libras enfrentam uma barreira de comunicação em atendimentos presenciais, como bancos, postos de saúde e órgãos públicos, pois poucos atendentes conhecem a língua e os intérpretes são escassos, principalmente fora das capitais. Hoje, a pessoa surda acaba dependendo de terceiros ou de escrita improvisada para resolver algo simples.

O projeto é uma aplicação web que usa a webcam para detectar a mão, extrair os 21 pontos (landmarks) com o MediaPipe e classificar, em tempo real, as letras do alfabeto manual de Libras. As letras reconhecidas formam palavras, que aparecem na tela e podem ser lidas em voz alta.

## Problema

A comunicação entre pessoas surdas e ouvintes em atendimentos presenciais depende de intérpretes, que são escassos, ou de soluções improvisadas, como escrita em papel.

## Usuários

- **Principal:** pessoa surda que usa Libras.
- **Secundário:** atendente ouvinte, que precisa entender a mensagem sem conhecer a língua.

## Resultado esperado

Que a pessoa surda consiga soletrar nomes, palavras-chave e números e ser compreendida por quem não sabe Libras, sem depender de intérprete, usando apenas um celular ou computador com navegador.

**Escopo desta fase:** comunicação básica por soletração. Não inclui tradução completa de frases.

## Como a aplicação deve funcionar

1. A webcam captura o vídeo do usuário.
2. O MediaPipe Hands detecta a mão e extrai os 21 landmarks.
3. Um modelo classifica o sinal como uma letra do alfabeto manual.
4. A letra reconhecida aparece na tela e é acrescentada à palavra em formação.
5. A palavra pode ser lida em voz alta pelo navegador.

Todo o processamento acontece no próprio dispositivo, **sem enviar vídeo a servidores**.

## Stack tecnológica inicial

| Categoria | Tecnologia |
| --- | --- |
| IDE | Visual Studio Code |
| Linguagens | Python (coleta de dados e treino) e JavaScript (aplicação web) |
| Detecção da mão | MediaPipe Hands |
| Visão e dados | OpenCV, NumPy |
| Modelo de comparação | scikit-learn |
| Modelo no navegador | TensorFlow/Keras exportado para TensorFlow.js |
| Voz | Web Speech API |
| Versionamento | Git e GitHub |

## Justificativa técnica

O MediaPipe Hands entrega os 21 pontos da mão já prontos, o que permite classificar o sinal a partir de coordenadas e não de imagens brutas. Isso reduz a quantidade de dados necessária, deixa o modelo leve e torna viável rodar em tempo real em um celular comum.

Python, com OpenCV, NumPy e scikit-learn, é a combinação mais direta para coletar os dados, treinar e comparar modelos. O TensorFlow/Keras exportado para TensorFlow.js leva o modelo final para o navegador, mantendo o processamento no dispositivo, o que protege a privacidade do usuário e dispensa servidor.

A Web Speech API fecha o fluxo ao transformar as palavras soletradas em voz, sem custo extra. Git e GitHub permitem versionar a evolução do projeto e acompanhar cada etapa do desenvolvimento orientado por especificação (SDD) nas próximas semanas.


## Acompanhamento

O instrutor [@MarcoMinozzo](https://github.com/MarcoMinozzo) foi convidado ao repositório.
