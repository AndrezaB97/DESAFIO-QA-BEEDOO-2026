# DESAFIO-QA-BEEDOO-2026

Este repositório contém a documentação do desafio técnico para a vaga de Analista de Qualidade de Software Júnior.

Aplicação analisada:
https://creative-sherbet-a51eac.netlify.app/

---

## 1. Análise inicial da aplicação

A aplicação disponibilizada apresenta um módulo simples de cadastro e visualização de cursos.

O usuário pode preencher um formulário com diversas informações sobre um curso e, após o cadastro, o curso passa a ser exibido em uma lista na interface.

Durante a exploração inicial foi possível identificar que o sistema permite registrar cursos e visualizá-los em formato de cards.

Os principais campos presentes no formulário são:

- Nome do curso
- Descrição
- Instrutor
- URL da imagem
- Data de início
- Data de fim
- Número de vagas
- Tipo de curso

Dependendo do tipo de curso selecionado, o sistema exibe campos adicionais:

- Curso presencial → campo de endereço
- Curso online → campo de link de inscrição

---

## 2. Decisões tomadas para criação dos testes

Para definir os cenários de teste, primeiro explorei a aplicação para entender como o fluxo de cadastro funcionava.

Inicialmente foi realizado um cadastro completo de curso para verificar o funcionamento do fluxo principal e confirmar se o curso era exibido corretamente na listagem.

Depois disso foram realizados testes com algumas variações nos campos, como:

- deixar campos vazios
- inserir valores negativos
- inserir datas inconsistentes
- testar o comportamento do tipo de curso (online e presencial)

O objetivo foi verificar se o sistema possuía validações para evitar cadastros com dados inconsistentes.

---

## 3. Explicação do raciocínio durante a análise

Durante a exploração da aplicação procurei interagir com os diferentes campos do formulário para entender como o sistema se comportava em diferentes situações.

Primeiro foi realizado um cadastro completo de curso para validar o funcionamento do fluxo principal.

Depois disso foram realizados testes com variações nos campos, como deixar informações em branco, inserir valores negativos ou combinar dados inconsistentes.

Também foram observados alguns comportamentos da interface, como o aparecimento de campos diferentes dependendo do tipo de curso selecionado e a forma como os dados cadastrados aparecem na listagem de cursos.

---

## 4. Execução dos testes

Os cenários de teste foram executados manualmente na aplicação disponibilizada no desafio.

Durante a execução foram avaliados principalmente:

- fluxo principal de cadastro de cursos
- validação dos campos do formulário
- cenários negativos
- possíveis comportamentos inesperados do sistema

O resultado da execução de cada cenário pode ser consultado na planilha abaixo:

[https://docs.google.com/spreadsheets/d/1qE3_8hs-nTEj0TXl10GuKoC5wrCOgNJ50fUFUFqH2Pw/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1qE3_8hs-nTEj0TXl10GuKoC5wrCOgNJ50fUFUFqH2Pw/edit?usp=sharing)

Na planilha estão registrados:

- os cenários de teste
- os passos executados
- o resultado esperado
- o resultado obtido
- o status do teste (Pass ou Fail)

---

## 5. Registro de bugs

Durante a execução dos testes foram identificados alguns comportamentos que podem indicar falhas de validação ou inconsistências na aplicação.

Abaixo estão descritos os principais problemas encontrados, organizados por nível de severidade.

---

### Bug 1 — Cadastro permitido sem preencher campos obrigatórios

**Passos para reproduzir**

1. Acessar a tela de cadastro de curso  
2. Não preencher nenhum campo do formulário  
3. Clicar em "Cadastrar curso"

**Resultado atual**

O sistema permite o cadastro mesmo sem preencher os campos.

**Resultado esperado**

O sistema deveria impedir o cadastro e informar que existem campos obrigatórios.

**Severidade**

Alta

---

### Bug 2 — Data final menor que data inicial é aceita

**Passos para reproduzir**

1. Preencher a data de início com uma data posterior  
2. Preencher a data final com uma data anterior  
3. Clicar em "Cadastrar curso"

**Resultado atual**

O sistema permite o cadastro do curso.

**Resultado esperado**

O sistema deveria validar as datas e impedir o cadastro quando a data final for menor que a data inicial.

**Severidade**

Alta

---

### Bug 3 — Número de vagas aceita valores negativos

**Passos para reproduzir**

1. Preencher o campo número de vagas com um valor negativo  
2. Preencher os demais campos  
3. Clicar em "Cadastrar curso"

**Resultado atual**

O sistema permite o cadastro com número de vagas negativo.

**Resultado esperado**

O sistema deveria validar o campo e aceitar apenas valores positivos.

**Severidade**

Alta

---

### Bug 4 — Campo nome do curso aceita apenas espaços

**Passos para reproduzir**

1. Preencher o campo "Nome do curso" apenas com espaços  
2. Preencher os demais campos  
3. Clicar em "Cadastrar curso"

**Resultado atual**

O sistema permite o cadastro.

**Resultado esperado**

O sistema deveria validar o campo e impedir o cadastro quando o nome contém apenas espaços.

**Severidade**

Média

---

### Bug 5 — Tipo de curso permite valor "Selecione..."

**Passos para reproduzir**

1. Preencher os campos do formulário  
2. Deixar o campo "Tipo de curso" como "Selecione..."  
3. Clicar em "Cadastrar curso"

**Resultado atual**

O sistema permite o cadastro e salva o valor "Selecione...".

**Resultado esperado**

O sistema deveria exigir a seleção de um tipo de curso válido.

**Severidade**

Média

---

### Bug 6 — Curso online permite cadastro sem link de inscrição

**Passos para reproduzir**

1. Selecionar tipo de curso "Online"  
2. Não preencher o campo "Link de inscrição"  
3. Clicar em "Cadastrar curso"

**Resultado atual**

O sistema permite o cadastro.

**Resultado esperado**

O sistema deveria exigir o preenchimento do link de inscrição.

**Severidade**

Média

---

### Bug 7 — Número de vagas aceita valor zero

**Passos para reproduzir**

1. Preencher o campo número de vagas com valor 0  
2. Preencher os demais campos  
3. Clicar em "Cadastrar curso"

**Resultado atual**

O sistema permite o cadastro.

**Resultado esperado**

O sistema deveria exigir um número de vagas maior que zero.

**Severidade**

Média

---

### Bug 8 — URL da imagem aceita valor inválido

**Passos para reproduzir**

1. Inserir um texto comum no campo URL da imagem  
2. Preencher os demais campos  
3. Clicar em "Cadastrar curso"

**Resultado atual**

O sistema aceita o valor e realiza o cadastro.

**Resultado esperado**

O sistema aceita o valor informado e realiza o cadastro sem validar o formato da URL.

**Severidade**

Baixa

---

### Bug 9 — Campos permanecem preenchidos ao alterar tipo de curso

**Passos para reproduzir**

1. Selecionar tipo de curso "Presencial"  
2. Preencher o campo endereço  
3. Alterar o tipo para "Online"

**Resultado atual**

O valor preenchido anteriormente permanece no formulário.

**Resultado esperado**

Os campos relacionados deveriam ser limpos ao alterar o tipo de curso.

**Severidade**

Baixa

---

### Bug 10 — Informações cadastradas não aparecem na listagem

**Passos para reproduzir**

1. Cadastrar um curso preenchendo todos os campos  
2. Acessar a listagem de cursos

**Resultado atual**

Algumas informações cadastradas não aparecem no card do curso, como link de inscrição, endereço ou nome do instrutor.

**Resultado esperado**

Essas informações deveriam estar visíveis na listagem ou em uma visualização detalhada.

**Severidade**

Baixa

---

## 6. Evidências da execução dos testes

Durante a execução dos testes foram capturadas evidências em forma de prints de tela.

As imagens correspondem aos cenários de teste executados e às observações realizadas durante a análise da aplicação.

As evidências podem ser encontradas na pasta:

/evidencias

---

---

## 7. Observações adicionais

Durante a exploração da aplicação também foram observados alguns comportamentos que podem impactar a validação dos dados ou a experiência do usuário.

### Persistência dos dados no navegador

Foi observado que os cursos cadastrados continuam aparecendo mesmo após atualizar a página utilizando **F5** ou **Ctrl + F5**.

Isso indica que os dados parecem estar sendo armazenados no **localStorage do navegador**, e não em um banco de dados. Dessa forma, os dados permanecem disponíveis mesmo após atualizar a página.

### Ausência de validação de campos obrigatórios

Durante a inspeção da interface foi observado que alguns campos do formulário não possuem o atributo **required**.

Isso permite que o usuário realize o cadastro mesmo sem preencher informações importantes, como por exemplo o nome do curso ou a descrição.

### Campo de número de vagas sem restrição mínima

Também foi observado que o campo **Número de vagas** não possui uma restrição mínima definida (por exemplo `min="0"`).

Por esse motivo o sistema permite inserir valores negativos no campo, o que pode gerar dados inconsistentes no cadastro de cursos.

---

## 8. Considerações finais

Durante a execução dos testes foi possível identificar algumas falhas de validação e comportamentos inesperados no formulário de cadastro de cursos.

Os testes realizados buscaram avaliar tanto o fluxo principal da aplicação quanto cenários negativos, verificando como o sistema se comporta diante de diferentes entradas de dados.

A análise também incluiu observações sobre o comportamento da interface e validações de campos, buscando identificar possíveis melhorias para a aplicação.
