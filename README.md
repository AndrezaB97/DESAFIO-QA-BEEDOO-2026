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
