---
title: nmcli - Impostare la Connessione Automatica
author: wale soyinka
tags:
  - nmcli
---

# Modifica della proprietà di autoconnessione del profilo di connessione di NetworkManager

Per prima cosa utilizzate nmcli per interrogare e visualizzare il valore corrente della proprietà autoconnect per tutte le connessioni di rete su un sistema Rocky Linux. Digitare:

```
nmcli -f name,autoconnect connection 
```

Per modificare il valore di una proprietà per una connessione di rete, utilizzare il sottocomando `modify` con `nmcli connection`. 
Ad esempio, per modificare il valore della proprietà autoconnect da `no` a `yes` per il profilo di connessione `ens3`, digitare:

```
sudo nmcli con mod ens3 connection.autoconnect yes
```

## Spiegazione dei Comandi

```
connection (con) : oggetto di connessione NetworkManager. 
modify (mod) : Modifica di una o più proprietà di un dato profilo di connessione.
connection.autoconnect : L'impostazione e la proprietà (<setting>.<property>)
-f, --fields : specifica i campi da produrre.

```

## Note

Questo suggerimento mostra come modificare un profilo di connessione NetworkManager esistente. Questo è utile quando l'interfaccia di rete non viene attivata automaticamente dopo una nuova installazione di Rocky Linux o dopo un aggiornamento del sistema.
Spesso il motivo è che il valore della proprietà autoconnect è impostato su `no`. È possibile utilizzare il comando `nmcli` per cambiare rapidamente il valore in `yes`.  
