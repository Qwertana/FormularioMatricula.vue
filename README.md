# Formulário de Matrícula em Vue.js

Projeto desenvolvido para a disciplina de Backend I para estudo de matéria da Universidade Veiga de Almeida

## **Funcionalidades**

- Campo **Nome Completo** (obrigatório)  
- Campo **E-mail** (obrigatório e com validação de formato)  
- Select de **Cursos** (simulado back no front)  
- **Botão de envio** que só habilita quando o formulário está válido  
- Mensagem de sucesso após envio  
- Limpeza dos campos após o envio  

---

## **Tecnologias**

- Vue.js 3
- HTML5 / CSS3  

---

## **Como rodar o projeto**

1. Clone ou abra este projeto no CodeSandbox.  
2. O projeto já está pronto para rodar.  
3. O select de cursos é preenchido diretamente no front, sem necessidade de back-end.  

> **Nota:** Para usar um back-end real, é necessário alterar o `mounted()` para buscar os cursos via `fetch` ou `axios`. Existe o código do backend criado e está nas notas.

---

## **Estrutura do projeto**

- `App.vue` — componente principal com formulário e lógica de validação.  
- `data()` — guarda os dados do formulário e cursos.  
- `mounted()` — simula os cursos que seriam buscados do back.  
- `computed` — contém validações de campos e verificação de formulário válido.  
- `methods` — função `enviarFormulario()` que exibe mensagem de sucesso e limpa os campos.  

---

## **Exemplo de uso**

1. Digite seu nome e e-mail.  
2. Selecione um curso.  
3. Clique em **Matricular**.  
4. A mensagem de sucesso aparecerá abaixo do formulário.  

---

## **Screenshots**

---

## **Observações**

- Este projeto é voltado para estudo e aprendizado de Vue.js.  
- O fetch para back-end foi removido para funcionar no CodeSandbox sem problemas de CORS ou containers separados.  
- Para produção, você pode integrar com um servidor Node.js ou qualquer back-end que forneça os cursos via API.
