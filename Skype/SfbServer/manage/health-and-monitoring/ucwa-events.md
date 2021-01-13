---
title: Eventi di UCWA in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 'Riepilogo: informazioni su Unified Communications Web API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: d8426418bf01954137a1bbed25d5fef93443dc5c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816666"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Eventi di UCWA in Skype for Business Server
 
**Riepilogo:** Informazioni su Unified Communications Web API (UCWA) in Skype for Business Server.
  
Skype for Business Server utilizza Unified Communications Web API (UCWA) per una serie di scopi, dall'accesso a Microsoft Exchange per le ricerche dei contatti per l'aggiornamento della presenza per i client mobili.
  
UCWA scriverà i record del comportamento operativo come tipi di evento informativi, di avviso e di errore. Nella tabella seguente vengono descritti gli eventi che possono essere scritti dai componenti di UCWA.
  
|**ID evento**|**Tipo evento**|**Riepilogo**|**Causa e risoluzione**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |Informativo  <br/> |UCWA inizializzato  <br/> |N/D  <br/> N/D  <br/> |
|20002  <br/> |Error  <br/> |UCWA ha rilevato un'eccezione imprevista durante l'inizializzazione  <br/> |Si è verificato un errore imprevisto durante l'inizializzazione  <br/> Esaminare i dettagli dell'eccezione nella voce del registro eventi associata per determinare la causa possibile  <br/> |
|20003  <br/> |Error  <br/> |UCWA ha rilevato un'eccezione non gestita  <br/> |Si è verificata un'eccezione non gestita  <br/> Riavviare il server. Se il problema persiste, contattare il supporto del prodotto  <br/> |
|20004  <br/> |Error  <br/> |Non è possibile accedere a Exchange per la foto HD  <br/> |La connessione a Exchange non è disponibile  <br/> Verificare che la connessione a Exchange sia disponibile  <br/> |
|20005  <br/> |Informativo  <br/> |Recuperato dalla mancata accesso a Exchange per la foto HD  <br/> |N/D  <br/> |
|20006  <br/> |Error  <br/> |Non è possibile accedere a Exchange per la ricerca dei contatti  <br/> |La connessione a Exchange non è disponibile  <br/> Verificare che la connessione a Exchange sia disponibile  <br/> |
|20007  <br/> |Informativo  <br/> |Recuperato dalla mancata ricerca del contatto in Exchange  <br/> |N/D  <br/> |
|20008  <br/> |Avviso  <br/> |Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per applicazione  <br/> |Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per applicazione  <br/> Controllare i client per le sottoscrizioni non necessarie  <br/> |
|20009  <br/> |Avviso  <br/> |Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per batch  <br/> |Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per batch  <br/> Controllare i client per le sottoscrizioni non necessarie  <br/> |
|20010  <br/> |Error  <br/> |Non è in grado di recuperare i dati inband  <br/> |Non è in grado di recuperare i dati inband  <br/> Se il problema persiste, contattare il supporto del prodotto  <br/> |
|20011  <br/> |Error  <br/> |Non è possibile sottoscrivere la presenza  <br/> |Non è possibile sottoscrivere la presenza  <br/> Se il problema persiste, contattare il supporto del prodotto  <br/> |
|20012  <br/> |Error  <br/> |Impossibile registrare l'endpoint  <br/> |Impossibile registrare l'endpoint  <br/> Se il problema persiste, contattare il supporto del prodotto  <br/> |
|20013  <br/> |Error  <br/> |La MCU di messaggistica istantanea non è disponibile  <br/> |La MCU di messaggistica istantanea non è disponibile  <br/> Vedere se è in esecuzione MCU di messaggistica istantanea  <br/> |
|20014  <br/> |Informativo  <br/> |Recuperato dalla mancata connessione a MCU IM  <br/> |N/D  <br/> |
|20015  <br/> |Error  <br/> |MCU AV non disponibile  <br/> |MCU AV non disponibile  <br/> Vedere se è in esecuzione MCU AV  <br/> |
|20016  <br/> |Informativo  <br/> |Recuperato dalla mancata connessione a MCU AV  <br/> |N/D  <br/> |
|20017  <br/> |Error  <br/> |Poiché MCU non è disponibile  <br/> |Poiché MCU non è disponibile  <br/> Vedere se è in esecuzione MCU  <br/> |
|20018  <br/> |Informativo  <br/> |Recuperato dalla mancata connessione a come MCU  <br/> |N/D  <br/> |
|20019  <br/> |Error  <br/> |MCU dei dati non disponibile  <br/> |MCU dei dati non disponibile  <br/> Controllare se è in esecuzione MCU dati  <br/> |
|20020  <br/> |Informativo  <br/> |Ripristino dalla mancata connessione a MCU dei dati  <br/> |N/D  <br/> |
|20021  <br/> |Error  <br/> |Non è possibile aggiungere MCU IM  <br/> |Non è possibile aggiungere MCU IM  <br/> Vedere se è in esecuzione MCU di messaggistica istantanea  <br/> |
|20022  <br/> |Error  <br/> |Non è possibile aggiungere MCU AV  <br/> |Non è possibile aggiungere MCU AV  <br/> Vedere se è in esecuzione MCU AV  <br/> |
|20023  <br/> |Error  <br/> |Non è possibile partecipare come MCU  <br/> |Non è possibile partecipare come MCU  <br/> Vedere se è in esecuzione MCU  <br/> |
|20024  <br/> |Error  <br/> |Non è possibile aggiungere MCU dati  <br/> |Non è possibile aggiungere MCU dati  <br/> Controllare se è in esecuzione MCU dati  <br/> |
|20025  <br/> |Error  <br/> |Non è possibile accedere ad Active Directory per la foto  <br/> |La connessione a Active Directory non è disponibile  <br/> Verificare che la connessione ad Active Directory sia disponibile  <br/> |
|20026  <br/> |Informativo  <br/> |Recuperato dalla mancata accesso ad Active Directory per la foto  <br/> |N/D  <br/> |
|20027  <br/> |Avviso  <br/> |Non può deserializzare  <br/> |Non può deserializzare  <br/> Se il problema persiste, contattare il supporto del prodotto  <br/> |
   

