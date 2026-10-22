# Constitution — Reconhecedor de Datilologia em Libras

## 1. Papéis e responsabilidades

**Dupla:** Kauan Moreira Petro e Thauan Pereira Gomes. As decisões abaixo são tomadas **pelos dois em conjunto**.

| Decisão | Quem decide |
| --- | --- |
| Aprovar a spec antes do desenvolvimento | Os dois integrantes, em conjunto |
| Aprovar e realizar o merge na `main` | Os dois integrantes, em conjunto |
| Alterar requisitos, critérios de aceitação ou escopo | Os dois integrantes, em conjunto |
| Trocar modelo, dataset ou limiar de confiança | Os dois integrantes, em conjunto |
| Executar tarefas de código dentro de uma spec aprovada | Agente de IA, sob as regras abaixo |

**Como a aprovação conjunta é registrada:** a aprovação de cada integrante fica escrita no pull request (comentário ou aprovação no GitHub). Sem os dois registros, não há merge. Quem clica em "Merge pull request" só o faz depois que os dois aprovaram.

## 2. O que o agente de IA pode fazer

**Sem aprovação prévia da dupla, o agente pode:**

- criar branches com nome `agente/<assunto>`;
- fazer commits nessas branches;
- escrever e rodar testes localmente;
- abrir pull requests (sempre como rascunho/draft);
- sugerir melhorias na spec **por escrito**, sem alterá-la.

**Exige aprovação dos dois integrantes antes de acontecer:**

- qualquer merge na `main`;
- alterações em `spec/`, nos critérios de aceitação ou neste arquivo;
- adicionar, remover ou trocar dependências e bibliotecas;
- alterar o modelo treinado, o dataset ou o limiar de confiança do reconhecimento;
- mudar qualquer comportamento visível ao usuário (letras reconhecidas, textos da tela, leitura em voz alta).

**O agente nunca pode:**

- fazer push direto na `main`;
- reescrever histórico (`force push`, `rebase` em branch já publicada);
- aprovar ou fazer merge do próprio pull request.

## 3. Decisões que ficam sempre com humanos

- O que o projeto faz e o que ele **não** faz (escopo).
- Quais letras e sinais entram em cada fase.
- Quais pessoas podem aparecer nos dados de treino e sob qual autorização.
- Quando uma funcionalidade está pronta.
- O que é entregue ao instrutor.

## 4. Três regras inegociáveis

### Regra 1 — Imagens e vídeos de pessoas não entram sem autorização

Nenhuma imagem, vídeo ou conjunto de landmarks de pessoa real entra no repositório, em prompts enviados a agentes de IA ou em logs sem autorização por escrito da pessoa filmada. O projeto promete processar tudo no próprio dispositivo; os dados de treino são tratados com o mesmo cuidado. Arquivos de dados brutos ficam fora do Git (`.gitignore`), e o repositório guarda apenas dados já autorizados e anonimizados.

### Regra 2 — O agente nunca altera a spec nem os critérios de aceitação sozinho

Requisitos, lista de letras suportadas, acurácia mínima e demais critérios de aceitação só mudam com aprovação explícita dos dois integrantes, registrada no pull request. Se o agente achar que a spec precisa mudar, ele escreve a sugestão e para; não implementa a mudança.

### Regra 3 — Uma funcionalidade só está "pronta" quando cumprir critérios verificáveis

Uma funcionalidade de reconhecimento só é considerada pronta quando:

1. atinge a acurácia definida na spec em dados de teste de pessoas que **não participaram do treino**;
2. roda na webcam, no navegador, **sem enviar vídeo a nenhum servidor**;
3. tem testes automatizados passando;
4. foi aprovada e mergeada pelos dois integrantes via pull request.

Se um dos quatro itens falta, a funcionalidade continua em desenvolvimento.

## 5. Mudanças nesta Constitution

Qualquer alteração neste arquivo é feita por pull request e exige aprovação dos dois integrantes. O agente de IA não edita este documento.
