Testes automatizados para teste de API, criado com Postman.

Endpoit: http://dummy.restapiexample.com/api/v1

Escopo:
- Cadastro
- Consulta a funcionario cadastrado
- Exclusão de usuário cadastrado

Relatórios gerados com Newman: o primeiro foi gerado com o relatório padrão, e o segundo customizado e disponivel com a instalação do package:
npm install -g newman-reporter-htmlextra

Comando para geração de relatorio em link compartilhado do projeto:
newman run https://www.getpostman.com/collections/39e8852000cec527508e --reporters=cli,htmlextra


Todos os scripts possuem validação de status e mensagem, além dos dados retornados na consulta.

O script de cadastro gera randomicamente o nome, salario e idade do funcionario.
O script de consulta ao funcionario que foi cadastrado retorna erro na execução. Infelizmente parece existir um erro no servidor e o ID não esta sendo gerado adequadamente. Se for consultado um cadastro já existente, o retorno funciona corretamente. Mantive então o script para pesquisa do funcionario que foi gravado por mim, apesar de retornar erro.
Se por exemplo for utilizado o endpoint /api/v1/employee/3, que é um cadastro pré-existente, irá retornar dados. Não irá funcionar com os testes que validam os dados cadastrados, pois esses testes procuram validar as informações que eu gerei no cadastro.
A exclusão remove o funcionario cadastrado, corretamente.