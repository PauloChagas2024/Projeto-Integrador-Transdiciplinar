# Projeto-Integrador-Transdiciplinar
Seja Bem vindo ao meu projeto Integrador - Transdiciplinar para o ano letivo de 2024, esse software foi desonvolvido em Low Code ( Abordagem de desenvolvimento de software que permite a criação de aplicações e soluções digitais com pouco ou nenhum código) a intenção foi automatizar e facilitar o controle de agendamento de visitas.
Essa fórmula é composta por verificações e ações para registrar uma visita em uma coleção colpessoas. Aqui está uma descrição detalhada:

 

1. Primeira Verificação (Campos em Branco):

 

A função IsBlank é utilizada para verificar se algum dos campos de texto (TextInput1, TextInput1_30, TextInput1_20, TextInput1_10, TextInput1_11, TextInput1_12, TextInput1_13) ou o campo de seleção (ComboBox1.Selected.Value) está vazio.

 

Se algum campo estiver em branco, a função Notify exibe uma mensagem de erro: "Existem campos vazios, por favor VERIFICAR".

 

 

 

2. Segunda Verificação (Limite de Pessoas):

 

Se todos os campos estiverem preenchidos, a fórmula verifica o número de registros na coleção colpessoas com a função CountRows(colpessoas).

 

Caso o número de registros seja menor que 10, ela permite a coleta dos dados. Caso contrário, uma mensagem de aviso é exibida: "O limite de 10 pessoas já foi atingido".

 

 

 

3. Coleta de Dados:

 

Quando o número de pessoas é inferior a 10, a função Collect adiciona um registro na coleção colpessoas, com os seguintes campos:

 

Data: _dateSelected

 

Matrícula: TextInput1.Text

 

Solicitante: TextInput1_30.Text

 

Motivo da Visita: TextInput1_20.Text

 

Visitante: TextInput1_10.Text

 

Objetivo: TextInput1_11.Text

 

Líder: TextInput1_12.Text

 

Área: TextInput1_13.Text

 

Email do Solicitante: User().Email (retorna o e-mail do usuário logado)

 

Email do Aprovador: obtido com a função LookUp na tabela tb_user, buscando o email_corp correspondente ao nome_user selecionado em ComboBox1.

 

Aprovador: valor selecionado em ComboBox1.

 

 

 

 

4. Notificação de Sucesso:

 

Após a coleta, a função Notify exibe a mensagem de sucesso "Visita Cadastrada com Exito".

 

 

 

5. Reset dos Campos:

 

Os campos TextInput1_20 e TextInput1_10 são resetados para limpar os dados inseridos.

 

 

 

6. Notificação de Informação:

 

Uma notificação é exibida mostrando o nome_user associado ao solicitante (TextInput1_30.Text) com uma mensagem do tipo Information.

 

 

 

 

Em resumo, essa fórmula realiza uma verificação para garantir que todos os campos estejam preenchidos, que o limite de 10 pessoas não tenha sido ultrapassado, e então coleta as informações do visitante.

