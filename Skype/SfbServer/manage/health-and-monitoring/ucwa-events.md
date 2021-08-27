---
title: Eventi UCWA in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 'Riepilogo: informazioni su UNIFIED Communications Web API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: 9fb052e1494354bc62f097152704bec1888e6523
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598816"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Eventi UCWA in Skype for Business Server
 
**Riepilogo:** Informazioni su Unified Communications Web API (UCWA) in Skype for Business Server.
  
Skype for Business Server utilizza UCWA (Unified Communications Web API) per diversi scopi, dall'accesso a Microsoft Exchange per le ricerche di contatti all'aggiornamento della presenza per i client mobili.
  
UCWA scriverà i record del comportamento operativo come tipi di evento Informativo, Avviso ed Errore. Nella tabella seguente vengono descritti gli eventi che possono essere scritti dai componenti UCWA.
  
|**ID evento**|**Tipo evento**|**Riepilogo**|**Causa e risoluzione**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |Informativa  <br/> |UCWA inizializzato  <br/> |N/D  <br/> N/D  <br/> |
|20002  <br/> |Error  <br/> |UCWA ha rilevato un'eccezione imprevista durante l'inizializzazione  <br/> |Si è verificato un errore imprevisto durante l'inizializzazione  <br/> Esaminare i dettagli dell'eccezione nella voce del registro eventi associata per determinare la possibile causa  <br/> |
|20003  <br/> |Error  <br/> |UCWA ha rilevato un'eccezione non gestita  <br/> |Si è verificata un'eccezione non gestita  <br/> Riavviare il server. Se il problema persiste, contattare il supporto tecnico  <br/> |
|20004  <br/> |Error  <br/> |Impossibile accedere Exchange foto HD  <br/> |Connessione a Exchange non disponibile  <br/> Verificare che la connessione a Exchange sia disponibile  <br/> |
|20005  <br/> |Informativa  <br/> |È stato ripristinato dall'errore di accesso Exchange foto HD  <br/> |N/D  <br/> |
|20006  <br/> |Error  <br/> |Impossibile accedere Exchange ricerca contatti  <br/> |Connessione a Exchange non disponibile  <br/> Verificare che la connessione a Exchange sia disponibile  <br/> |
|20007  <br/> |Informativa  <br/> |È stato ripristinato dall'errore di ricerca del contatto in Exchange  <br/> |N/D  <br/> |
|20008  <br/> |Avviso  <br/> |Tentare di sottoscrivere più sottoscrizioni di presenza consentite per ogni applicazione  <br/> |Tentare di sottoscrivere più sottoscrizioni di presenza consentite per ogni applicazione  <br/> Verificare la presenza di sottoscrizioni non necessarie nei client  <br/> |
|20009  <br/> |Avviso  <br/> |Tentare di sottoscrivere più sottoscrizioni di presenza consentite per batch  <br/> |Tentare di sottoscrivere più sottoscrizioni di presenza consentite per batch  <br/> Verificare la presenza di sottoscrizioni non necessarie nei client  <br/> |
|20010  <br/> |Error  <br/> |Impossibile recuperare i dati inband  <br/> |Impossibile recuperare i dati inband  <br/> Se il problema persiste, contattare il supporto tecnico  <br/> |
|20011  <br/> |Error  <br/> |Impossibile sottoscrivere la presenza  <br/> |Impossibile sottoscrivere la presenza  <br/> Se il problema persiste, contattare il supporto tecnico  <br/> |
|20012  <br/> |Error  <br/> |Impossibile registrare l'endpoint  <br/> |Impossibile registrare l'endpoint  <br/> Se il problema persiste, contattare il supporto tecnico  <br/> |
|20013  <br/> |Error  <br/> |MCU di messaggistica istantanea non disponibile  <br/> |MCU di messaggistica istantanea non disponibile  <br/> Verificare se la MCU di messaggistica istantanea è in esecuzione  <br/> |
|20014  <br/> |Informativa  <br/> |Impossibile connettersi a MCU di messaggistica istantanea  <br/> |N/D  <br/> |
|20015  <br/> |Error  <br/> |AV MCU non disponibile  <br/> |AV MCU non disponibile  <br/> Verificare se AV MCU è in esecuzione  <br/> |
|20016  <br/> |Informativa  <br/> |Impossibile connettersi a AV MCU  <br/> |N/D  <br/> |
|20017  <br/> |Error  <br/> |AS MCU is unavailable  <br/> |AS MCU is unavailable  <br/> Vedere se AS MCU è in esecuzione  <br/> |
|20018  <br/> |Informativa  <br/> |Impossibile connettersi a AS MCU  <br/> |N/D  <br/> |
|20019  <br/> |Error  <br/> |MCU dati non disponibile  <br/> |MCU dati non disponibile  <br/> Verificare se MCU dati è in esecuzione  <br/> |
|20020  <br/> |Informativa  <br/> |Impossibile connettersi a MCU dati  <br/> |N/D  <br/> |
|20021  <br/> |Error  <br/> |Impossibile partecipare a MCU di messaggistica istantanea  <br/> |Impossibile partecipare a MCU di messaggistica istantanea  <br/> Verificare se la MCU di messaggistica istantanea è in esecuzione  <br/> |
|20022  <br/> |Error  <br/> |Impossibile partecipare a AV MCU  <br/> |Impossibile partecipare a AV MCU  <br/> Verificare se AV MCU è in esecuzione  <br/> |
|20023  <br/> |Error  <br/> |Impossibile aggiungere AS MCU  <br/> |Impossibile aggiungere AS MCU  <br/> Vedere se AS MCU è in esecuzione  <br/> |
|20024  <br/> |Error  <br/> |Impossibile partecipare a MCU dati  <br/> |Impossibile partecipare a MCU dati  <br/> Verificare se MCU dati è in esecuzione  <br/> |
|20025  <br/> |Error  <br/> |Impossibile accedere ad Active Directory per la foto  <br/> |Connessione ad Active Directory non disponibile  <br/> Verificare che la connessione ad Active Directory sia disponibile  <br/> |
|20026  <br/> |Informativa  <br/> |Ripristinato dall'errore di accesso ad Active Directory per la foto  <br/> |N/D  <br/> |
|20027  <br/> |Avviso  <br/> |Impossibile deserializzare  <br/> |Impossibile deserializzare  <br/> Se il problema persiste, contattare il supporto tecnico  <br/> |
   

