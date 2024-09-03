# Sistema de Gerenciamento de Eventos

Este projeto define um sistema SQL para gerenciamento de eventos, incluindo tabelas para Eventos, Participantes e Inscrições. O sistema permite o cadastro de eventos, participantes e a gestão das inscrições, com várias funcionalidades de consulta, atualização e exclusão de dados.

## Estrutura do Banco de Dados

1. **Eventos**:
   - `EventoID` (INT, PK, Auto Increment)
   - `NomeEvento` (VARCHAR(100), NOT NULL)
   - `DataEvento` (DATE, NOT NULL)
   - `LocalEvento` (VARCHAR(100), NOT NULL)
   - `Descricao` (TEXT)

2. **Participantes**:
   - `ParticipanteID` (INT, PK, Auto Increment)
   - `NomeParticipante` (VARCHAR(100), NOT NULL)
   - `Email` (VARCHAR(100), UNIQUE, NOT NULL)
   - `Telefone` (VARCHAR(15))

3. **Inscrições**:
   - `InscricaoID` (INT, PK, Auto Increment)
   - `EventoID` (INT, FK, REFERENCES Eventos)
   - `ParticipanteID` (INT, FK, REFERENCES Participantes)
   - `DataInscricao` (DATE, NOT NULL)

## Inserção de Dados

1. **Eventos**: 
   - Dois eventos foram inseridos com suas datas, locais, e descrições.
   
2. **Participantes**: 
   - Dois participantes foram inseridos com seus nomes, emails, e telefones.
   
3. **Inscrições**: 
   - As inscrições dos participantes nos eventos foram registradas.

## Funcionalidades

### Consultas

1. **Consultar Todos os Eventos Disponíveis**:
   - Retorna todos os eventos cadastrados:
   ```sql
   SELECT * FROM Eventos;
