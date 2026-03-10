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
