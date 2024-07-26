# Documentação da API Health&Med

Esta documentação fornece uma visão geral dos endpoints da API Health&Med e seu uso.

## URL Base

```
https://pikwe9lct4.execute-api.us-east-1.amazonaws.com/prod
```

## Autenticação

Para acessar os endpoints da API, você precisa incluir um token de portador no cabeçalho `Authorization` das suas requisições. O token pode ser obtido fazendo uma requisição GET para o endpoint de autenticação apropriado:

- Para médicos: `/token/medico`
- Para pacientes: `/token/paciente`

## Endpoints

Horários
#### Obter todos os horários

Método: GET
Endpoint: /horarios
Autenticação: Token de portador do paciente ou médico

#### Obter um horário por ID

Método: GET
Endpoint: /horarios/{id}
Autenticação: Token de portador do paciente ou médico

#### Atualizar um horário

Método: PUT
Endpoint: /horarios
Autenticação: Token de portador do médico
Corpo da requisição:
{
  "data_hora": "20240724230300",
  "id_medico": "idmedico",
  "id_consulta": "cheidesal",
  "id": "1721873754998",
  "status_consulta": "confirmado",
  "id_paciente": "idpaciente123"
}

#### Excluir um horário

Método: DELETE
Endpoint: /horarios/{id}
Autenticação: Token de portador do médico

  ## Autenticação

### Autenticação do Médico

- Método: `GET`
- Endpoint: `/token/medico`
- Corpo da requisição:
  ```json
  {
    "crm": "12345sp",
    "password": "12345Abc@@@"
  }
  ```

### Autenticação do Paciente

- Método: `GET`
- Endpoint: `/token/paciente`
- Corpo da requisição:
  ```json
  {
    "cpf": "22496741839",
    "email": "22496741839@teste.com",
    "password": "Teste@22496741839"
  }
  ```

Espero que esta documentação seja útil para entender e utilizar a API Health&Med. Se você tiver alguma dúvida adicional, não hesite em perguntar.
