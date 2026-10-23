# Relatório — Datilologia em Libras

## Viabilidade

- Grupo: Dupla 06
- Integrantes: Kauan Moreira Petro e Thauan Pereira Gomes
- Repositório: https://github.com/kauanp11/reconhecer-libras
- Stack: Python, MediaPipe, scikit-learn, TensorFlow.js, JavaScript e Web Speech API.
- Veredito: Viável com recorte

O problema e o limite (“soletrar, não traduzir frases”) estão claros. Coletar dataset, treinar rede e ainda servir tempo real no celular não cabe junto. O caminho viável é classificar landmarks de letras estáticas.

## SWOT

### Forças

Usuário principal e secundário separados. Processamento no aparelho, sem enviar vídeo. MediaPipe reduz o problema de imagem bruta para 21 pontos. A dupla já exclui tradução de frase.

### Fraquezas

A stack lista scikit-learn e TensorFlow/Keras ao mesmo tempo, mais OpenCV, NumPy e voz. Não há plano de quantas letras, quantas amostras nem como medir acerto. 

### Oportunidades

Alfabeto estático, um classificador simples sobre os landmarks e acerto medido num conjunto pequeno gravado pela dupla. TensorFlow.js e letras com movimento (J, Z) ficam fora.

### Ameaças

Letras parecidas, mão esquerda, luz e distância derrubam a acurácia. Sem métrica na spec, o projeto não tem como dizer que funciona. Dataset próprio pode consumir o prazo inteiro.

## Stack técnica

**Parecer: Inadequada no conjunto.** Python, TensorFlow.js, scikit-learn, OpenCV e voz ao mesmo tempo são demais; a stack recomendada é JavaScript no navegador com MediaPipe Hands e um classificador simples sobre os 21 pontos.

A ideia técnica central está certa: classificar a letra a partir dos pontos da mão, no próprio aparelho, sem enviar vídeo. O que não está adequado é a lista inteira. Há dois treinamentos possíveis, scikit-learn e TensorFlow/Keras, mais a exportação para TensorFlow.js, mais OpenCV, NumPy e a Web Speech API. Isso são dois projetos, o de treino e o de execução, e a disciplina não comporta os dois com meta de acerto.

A stack recomendada fica no navegador: Visual Studio Code, JavaScript, MediaPipe Hands e um classificador simples, como kNN, usando só as coordenadas. A câmera do browser substitui o OpenCV. A voz fica para depois que a taxa de acerto das letras estáticas estiver escrita na spec e atingida. Python com MediaPipe e scikit-learn seria um segundo caminho válido, desde que a demonstração também seja em Python e TensorFlow.js saia da stack.

## Recomendação

**Reconheçam apenas letras estáticas a partir dos pontos da mão, com uma meta de acerto escrita na spec.**

O problema da datilologia está bem colocado, e o limite de soletrar em vez de traduzir frases deve permanecer. O que não cabe é fazer, nas mesmas semanas, coleta grande de imagens, treino de rede neural e execução em tempo real no celular. A constitution pode descrever um caminho mais curto e ainda assim fiel à ideia. A câmera vê a mão parada, o MediaPipe devolve os 21 pontos, e um classificador simples, como kNN ou scikit-learn, escolhe a letra. A spec lista quais letras entram, quantas amostras a dupla vai gravar e qual taxa de acerto considera suficiente no conjunto de teste. TensorFlow.js, a leitura em voz alta e as letras que dependem de movimento, como J e Z, ficam para uma etapa posterior, quando o classificador estático já tiver essa meta. Sem a meta escrita, o grupo não tem como mostrar que o reconhecimento funciona.
