# Relatório — Datilologia em Libras — semana 2

## Viabilidade

- Grupo: Dupla 06
- Integrantes: Kauan Moreira Petro e Thauan Pereira Gomes
- Repositório: https://github.com/kauanp11/reconhecer-libras
- Constitution: https://github.com/kauanp11/reconhecer-libras/blob/main/CONSTITUTION.md
- Veredito: Atende

O arquivo abre na `main`. Os dois aprovam a spec e os dois aprovam o merge, com os dois registros no pull request. O agente cria branch `agente/`, commita, roda teste local e abre pull request em rascunho. Não faz push na `main`, não dá force push e não aprova o próprio PR. Não troca modelo, dataset, limiar nem comportamento da tela sem os dois.

## SWOT

### Forças

As regras são do reconhecedor. Imagem, vídeo e landmark de pessoa real não entram no Git, no prompt nem no log sem autorização escrita. O agente sugere mudança de spec por escrito e para. “Pronto” exige acurácia em pessoas que não entraram no treino, webcam no navegador sem enviar vídeo a servidor, testes passando e merge dos dois. Dado bruto fica no `.gitignore`.

### Fraquezas

A URL do repositório no PDF aponta para `/tree/main`, a raiz. O link que vale é o do arquivo, e esse abre. A acurácia mínima não tem número nesta constitution. Ela fica para a spec, e a regra 3 já exige que a spec a defina.

### Oportunidades

A primeira spec pode fixar o conjunto de letras, o número da acurácia e de quem são os dados de teste. O merge continua com as duas aprovações no pull request.

### Ameaças

Subir vídeo de treino no repositório quebra a regra 1 mesmo com o modelo melhorando. Mandar o quadro da webcam para um servidor quebra a regra 3 e a promessa de processar no aparelho.

## Stack técnica

**Parecer: Sem mudança de governança.** A constitution não troca Python, MediaPipe nem a leitura no navegador. Ela trava o que a semana 1 já pedia: reconhecimento no dispositivo, sem servidor de vídeo.

Modelo e dataset só mudam com os dois. Não há stack nova para corrigir.

## Recomendação

**Mantenham este arquivo e escrevam na spec o conjunto de letras e a acurácia mínima.**

Os dois aprovam spec e merge. O agente trabalha em branch de rascunho. Imagem de pessoa real, modelo e dataset não mudam sem os dois. Vídeo não sai do navegador.
