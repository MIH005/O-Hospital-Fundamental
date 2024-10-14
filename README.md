# O-Hospital-Fundamental - Sistema de Controle de Consultas para Hospital

## Descrição

O hospital necessita de um sistema para sua área clínica que ajude a controlar consultas realizadas. Os médicos podem ser generalistas, especialistas ou residentes e têm seus dados pessoais cadastrados em planilhas digitais. Cada médico pode ter uma ou mais especialidades, que podem ser pediatria, clínica geral, gastroenterologia e dermatologia. Alguns registros antigos ainda estão em formulário de papel, mas será necessário incluir esses dados no novo sistema.

Os pacientes também precisam de cadastro, contendo dados pessoais (nome, data de nascimento, endereço, telefone e e-mail), documentos (CPF e RG) e convênio. Para cada convênio, são registrados nome, CNPJ e tempo de carência.

As consultas também têm sido registradas em planilhas, com data e hora de realização, médico responsável, paciente, valor da consulta ou nome do convênio, com o número da carteira. Também é necessário indicar na consulta qual a especialidade buscada pelo paciente.

Deseja-se ainda informatizar a receita do médico, de maneira que, no encerramento da consulta, ele possa registrar os medicamentos receitados, a quantidade e as instruções de uso. A partir disso, espera-se que o sistema imprima um relatório da receita ao paciente ou permita sua visualização via internet.


______________________________________________________________________________________________________________________________________________________________________________________________________________

## Estrutura do Banco de Dados

### Entidades e Atributos

1. **Médico**
   - Num_CRM (PK)
   - Nome_Med
   - Data_Nasci_med
   - Endereço_med
   - Telefone_med
   - Email_med

1.1 **Médico_Generalista**
      - Num_CRM(PK e FK)
      
1.2 **Médico_Especialista**
      - Num_CRM(PK e FK)
      
1.3 **Médico_Residente**
      - Num_CRM(PK e FK)

2. **Especialidade**
   - COD_Especialidade (PK)
   - Nome_Especialidade

3. **Pacientes**
   - CPF_Paci (PK)
   - Nome_Paci
   - data_nasci_paci
   - Endereço_Paci
   - Telefone_Paci
   - Email_Paci
   - RG_Paci
   - COD_Convenio (FK)

4. **Convênio**
   - COD_Convenio (PK)
   - Nome_Convenio
   - CNPJ
   - Tempo_Carencia

5. **Consulta**
   - COD_Consulta (PK)
   - Data
   - Horario
   - Num_Carteira
   - Num_crm (FK)
   - CPF_Paci (FK)
   - COD_Convenio (FK)
   - COD_Especialidade (FK)

6. **Receita**
   - COD_Receita (PK)
   - COD_Consulta (FK)
   - Medicamento
   - Quantidade
   - Instrucoes

### Relacionamentos e Cardinalidades

1. **Especialista - Especialidade**
   - Relacionamento: Um Especialista pode ter uma ou mais especialidades.
   - Cardinalidade: 1:N

2. **Pacientes - Convênio**
   - Relacionamento: Um paciente pode ter um convênio.
   - Cardinalidade: 1:1

3. **Consulta - Pacientes**
   - Relacionamento: Uma consulta é realizada para um paciente.
   - Cardinalidade: N:1

5. **Consulta - Convênio**
   - Relacionamento: Uma consulta pode ser coberta por um convênio.
   - Cardinalidade: N:1

6. **Receita - Consulta**
   - Relacionamento: Uma receita é gerada a partir de uma consulta.
   - Cardinalidade: 1:1
   - 
7. **Pacientes - Receita**
   - Relacionamento: Um paciente recebe uma receita.
   - Cardinalidade: 1:1


## Desenho do **DIAGRAMA ER** 
![image](https://github.com/user-attachments/assets/b332585f-fe42-46f1-b610-1e12103dbbb1)


