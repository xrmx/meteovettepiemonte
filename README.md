# API regione piemonte previsioni in vetta

## Lista dei settori

Per avere la lista dei settori l'API è la seguente:

```
http://www.regione.piemonte.it/retescursionistica/cms/meteovetta/servizio_elenco_settori.php
```

La risposta in formato JSON ha questo formato:

```
[
    {
        "id": "1",
        "nome": "Alpi Lepontine Nord"
    },
    ...
]

```

## Previsioni per un dato settore

L'url della API JSON per le previsioni è la seguente:

```
http://www.regione.piemonte.it/retescursionistica/cms/meteovetta/servizio_dettaglio_settore.php
```

L'API prende i seguenti parametri come query string:

- `type`, una stringa fissa `previsioni`
- `data`, il giorno in formato `dd/mm/YYYY` per cui visualizzare le previsioni
- `settore`, l'id del settore di interesse

Ad esempio per avere le previsioni per il 10 settembre 2017 per il settore 1:

```
http://www.regione.piemonte.it/retescursionistica/cms/meteovetta/servizio_dettaglio_settore.php?type=previsioni&date=10/09/2017&settore=1
```

che ritorna un JSON nel seguente formato:

```
{
    "Denominazione": "Alpi Lepontine Nord",
    "data": "09/09/2017",
    "pomeriggio": {
        "codice": "25",
        "descrizione": "Pioggia molto forte"
    },
    "quotaNeve": "",
    "quotaNeve24": "2700",
    "stazioni": [
        {
            "denominazione": "FORMAZZA BRUGGI",
            "quota": "1226",
            "temperatura": {
                "max": "14",
                "min": "11"
            },
            "vento": {
                "direzione": "W",
                "velocita": "debole"
            }
        },
        {
            "denominazione": "ALPE DEVERO",
            "quota": "1634",
            "temperatura": {
                "max": "13",
                "min": "9"
            },
            "vento": {
                "direzione": "NW",
                "velocita": "debole"
            }
        },
        {
            "denominazione": "FORMAZZA",
            "quota": "2453",
            "temperatura": {
                "max": "6",
                "min": "4"
            },
            "vento": {
                "direzione": "W",
                "velocita": "moderato"
            }
        }
    ],
    "valanghe": {},
    "zeroTermico": "",
    "zeroTermico24": "3000"
}
```
