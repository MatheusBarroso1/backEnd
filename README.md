# ProjetoBack-end-LTD
![Spring](https://img.shields.io/badge/spring-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white)
![MySQL](https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white)
![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white)

## Microserviços de Agendamento de consulta.

A continuação da aplicação Back-End do LTD Estácio onde é incluso os microserviços de Consultas.

## Condições de instalação

1.  Instalar JAVA 17
2.  Instalar GIT

## Instrução de uso

1. Após "buildar" a aplicação, abra em seu aplicativo de teste de API Back-End a porta http://localhost:8080/

2. Prepare seus métodos com as instruções a seguir:

```bash
    POST  /home/consulta/salvar: End point para salvar a consulta referente ao usuário e clínica.
    
    GET  /home/consulta/listar: End point para listar todas as consultas agendadas pelo o paciente.
    
    GET  /home/consulta/por-clinica: End point para listar todas as consultas agendadas pelo o paciente mas filtrando por clínica.
    
    DELETE  /home/consulta/deletar: End point para excluir alguma consulta agendada(apenas certos usuario tem acesso a esse end-point).
    
    PUT  /home/consulta/info: End point para "setar" as informações de funcionário que irá atender o paciente com alguma informação adicional.
    
    GET  /home/consulta/listarByDay: End point para listar todas as consultas agendadas por data e clínica.
    
    GET  /home/consulta/listarByPaciente: End point para listar todas as consultas agendadas pelo o paciente mas filtrando por usuário do paciente.
    
```

BODY da requisição em JSON 

```bash
    POST  /home/consulta/salvar: End point para salvar a consulta referente ao usuário e clínica.
    
    {
  "dia": "2024-05-27",
  "clinica": {
    "id": 1,
		"nome": "Fisica",
		"descricao": "TE ACALMA",
		"quantidadeMax": 7,
		"maxPorHorario": 3
  },
	"horaInicio": "15:00:00",
	"horaFim": "16:00:00",
  "paciente": "nicolas",
  "info": ""
}
```
--

```bash
  GET  /home/consulta/listar: End point para listar todas as consultas agendadas.
    
```
--
```bash
   GET  /home/consulta/por-clinica: End point para listar todas as consultas agendadas pelo o paciente mas filtrando por clínica.
   
   {
	"clinica": "Direito"
}
```

--

```bash
  DELETE  /home/consulta/deletar: End point para excluir alguma consulta agendada(apenas certos usuario tem acesso a esse end-point).
  
  {
	"id": 1
}
```
--
```bash
   PUT  /home/consulta/info: End point para "setar" as informações de funcionário que irá atender o paciente com alguma informação adicional.
   
   {
	"consulta": 1,
	"info": "VC é neuro-divergente, mas é legal",
	"user": "diego"
}
```
--
```bash
   GET  /home/consulta/listarByDay: End point para listar todas as consultas agendadas por data e clínica.
   
   {
	"clinica": {
		"id": 1,
		"nome": "Fisica",
		"descricao": "TE ACALMA",
		"quantidadeMax": 7,
		"maxPorHorario": 3
	},
	"date": "2024-05-27"
}
   
```
--
```bash
  GET  /home/consulta/listarByPaciente: End point para listar todas as consultas agendadas pelo o paciente mas filtrando por usuário do paciente.
  
  {
	"paciente": "diego"
}
```
--
## Informações Adicionais

Vale a pena dizer que, temos algumas restrições de agendamento de consulta para cada clínica como:
1. Quantidade Máxima por Dia.
2. Quantidade Máxima por Intervalo De Horário.
