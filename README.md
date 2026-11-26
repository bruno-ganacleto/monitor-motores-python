# Monitoramento de Motores Industriais :scroll:
### :exclamation: Objetivo principal:
O projeto tem como objetivo realizar a análise das leituras de motores inseridas e validá-las com base em seus limites de operação, exibindo ao final do programa uma tabela com os dados dos motores e resultados das validações.


## :gear: Funcionamento:
O código tem seus limites de operação e leituras dos motores inseridos previamente dentro do código fonte, como mostrado abaixo:
```
LIMITES = {
    "temperatura_max": 80.0,
    "corrente_max": 18.5,
    "vibracao_max": 4.5,
    "rpm_min": 1400,
    "rpm_max": 1800,
}

LEITURAS_MOTORES = [
    {"id": "MTR-01", "setor": "Estamparia", "temperatura": 68.4, "corrente": 14.2, "vibracao": 2.1, "rpm": 1750, "potencia_kw": 7.5},
    {"id": "MTR-02", "setor": "Usinagem", "temperatura": 84.7, "corrente": 19.3, "vibracao": 5.2, "rpm": 1690, "potencia_kw": 11.0},
    {"id": "MTR-03", "setor": "Bobinagem", "temperatura": 76.2, "corrente": 17.8, "vibracao": 4.7, "rpm": 1520, "potencia_kw": 5.5},
    {"id": "MTR-04", "setor": "Pintura", "temperatura": 61.0, "corrente": 11.5, "vibracao": 1.8, "rpm": 1780, "potencia_kw": 7.5},
]
```  

Após isso, o programa valida se os dados da leitura estão dentro do limite, checando os alertas e atualizando os status de funcionamento.  

Sucessivamente ele realiza calcula os seguintes dados:
- Média de temperatura
- Média de corrente
- Potência total
- Maior temperatura atingida

E ao fim do processo, ele retorna os status e leituras de cada motor, como no exemplo abaixo:

---

_Status_ | _ID_ | _Setor_ | _Temperatura_ | _Corrente_ | _Vibração_ | _RPM_
:---: | :---: | :---: | :---: | :---: | :---: | :---:
NORMAL | MTR-01 | Estamparia | 68.4 C | 14.2A | 2.1 mm/s | 1750
CRÍTICO | MTR-02 | Usinagem | 84.7 C | 19.3A | 5.2 mm/s | 1690

--> Alerta: **Superaquecimento** (84.7 C)  
--> Alerta: **Sobrecorrente** (19.3A)  
--> Alerta: **Vibração Elevada** (5.2mm/s)

---


Retorna uma tabela contendo o id, setor, temperatura , corrente, vibração e rpg de cada motor, junto de seus status e alertas.
Termina exibindo as estatisticas de temperatura média, corrente média, potência total e maior temperatura.  

> Criador do README: [Bruno Gabriel Anacleto](https://github.com/bruno-ganacleto)
> Link para o site com a explicação do software: https://bruno-ganacleto.github.io/monitor-motores-python/
