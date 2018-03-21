---
title: Confrontare i provider di servizi di conferenza telefonica con accesso esterno
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b0d2b50e-def3-4bd8-82d4-a27f4b6f205c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Quando si configurano conferenze telefoniche con accesso esterno o PSTN per Skype for Business, è necessario scegliere un provider di servizi di conferenza telefonica con accesso esterno. È possibile scegliere Microsoft o il proprio provider di conferenza telefonica con accesso esterno, oppure un terzo."
ms.openlocfilehash: e2b08b9d5db41cd9f6a0bff6d000c65ecbe6dfba
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2018
---
# <a name="compare-audio-conferencing-providers"></a>Confrontare i provider di servizi di conferenza telefonica con accesso esterno

[] Quando si configurano conferenze telefoniche con accesso esterno o PSTN per Skype for Business, è necessario scegliere un provider di servizi di conferenza telefonica con accesso esterno. È possibile scegliere Microsoft o il proprio provider di conferenza telefonica con accesso esterno, oppure un terzo. 
  
> [!IMPORTANT]
> Se Microsoft è il provider di conferenza telefonica con accesso esterno o fornitori terzi, in entrambi i casi il provider scelto: 
  
Audio conferencing providers do the following: 
  
- Fornire un *ponte per conferenze audio*. Bridge conferenza impostano i numeri di telefono di accesso esterno, pin e gli ID conferenza per le riunioni.
    
- Imposta la lingua che gli utenti ascolteranno quando accedono a una riunione tramite telefono.
    
- Crea ID conferenza riunione da utilizzare quando si partecipa a una riunione.
    
- Fornisce all'organizzatore i PIN per avviare riunioni tramite telefono.
    
- Usare la tabella sottostante per confrontare le differenze tra Microsoft e un fornitore terzo di conferenze telefoniche con accesso esterno.
    
Use the following table to compare what you get if you choose Microsoft or a third-party audio conferencing provider.
  
||||
|:-----|:-----|:-----|
|**Microsoft (Office 365)** <br/> |**Provider di terze parti** <br/> |Configurazione del provider <br/> |
|Facile da configurare. La maggior parte delle impostazioni è configurata automaticamente.  <br/> |Difficile da configurare. Richiede procedure manuali.  <br/> |Licenze  <br/> |
|Licensing  <br/> |È necessaria una licenza di **Conferenze Audio** . Vedi [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> |Gestione  <br/> |
|Integrata nell'interfaccia di amministrazione di Office 365.  <br/> |Gestione manuale con tecnici di terze parti.  <br/> |Configurazione degli utenti  <br/> |
|Facile  <br/> |Difficile  <br/> |Fatturazione  <br/> |
|Tramite Office 365.  <br/> |Anche tramite il provider di servizi di audioconferenza di terze parti.  <br/> | Assegnazione del bridge per i servizi di conferenza telefonica con accesso esterno <br/> |
|Automatica  <br/> |È necessario immettere manualmente il bridge di conferenza per ogni utente.  <br/> |Gestione ID conferenza  <br/> |
|Automatica  <br/> |Manuale  <br/> |Reimpostazione ID conferenza riunione  <br/> |
|Reset meeting conference ID  <br/> |Sì, ma è necessario immetterlo manualmente.<br/> |Numeri verdi  <br/> |
|Sì  <br/> |Sì  <br/> |Numeri a pagamento nazionali  <br/> |
|Sì  <br/> |Sì  <br/> |Numeri a pagamento internazionali  <br/> |
|Sì  <br/> |Sì  <br/> |Trasferimento dei numeri di telefono esistenti  <br/> |
|Sì  <br/> |No  <br/> |Chiamata esterna/Chiama - Nazionali  <br/> |
|Sì  <br/> |Sì  <br/> |Chiamata esterna/Chiama - Internazionali  <br/> |
|Dial-out / Call-me - International  <br/> |Sì, ma è disponibile solo in alcuni paesi. Per un elenco dei paesi supportati, vedere [disponibilità paese e alle aree per le conferenze Audio e la chiamata dei piani](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) . <br/> |L'organizzatore della riunione può eseguire l'autenticazione tramite un PIN  <br/> |
|Sì  <br/> |No  <br/> |Qualsiasi utente nell'organizzazione può eseguire l'autenticazione tramite un PIN  <br/> |
|No  <br/> |No  <br/> |Pagina della convocazione di riunione con numeri di telefono di accesso esterno predefiniti  <br/> |
|Sì  <br/> |Sì  <br/> |Pagina supplementare per accesso esterno con un elenco completo dei numeri di telefono di accesso esterno supportati  <br/> |
|Sì  <br/> |Sì  <br/> |Opzione per avviare una riunione con terze parti senza un PIN  <br/> |
|Sì  <br/> |No  <br/> |Supporto per più lingue  <br/> |
|Multiple language support  <br/> |Sì. Vedere [audioconferenze lingue supportate](audio-conferencing-supported-languages.md).  <br/> |Gestione delle lingue per l'operatore automatico delle riunioni  <br/> |
|Sì  <br/> |Sì  <br/> |Supporto per più paesi  <br/> |
|Multiple country/region support  <br/> |Sì. Vedere [disponibilità paese e alle aree per le conferenze Audio e la chiamata Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).  <br/> |Se la riunione non è ancora iniziata o se è stata bloccata, gli utenti ascoltano musica durante l'attesa  <br/> |
|Sì  <br/> |No  <br/> |Impostazione di un numero di accesso esterno internazionale come numero di accesso esterno predefinito, e quindi visualizzato nella convocazione di riunione, per un utente  <br/> |
|Sì  <br/> |No  <br/> |Esperienza integrata che consente agli utenti di Skype for Business online di reimpostare il PIN e l'ID conferenza della riunione  <br/> |
|Disponibile nelle versioni future.  <br/> |No  <br/> |Supporto per riunioni private con ID conferenza di riunione dinamici  <br/> |
|Disponibile nelle versioni future.  <br/> |No  <br/> |No  <br/> |
   
See also
  
## <a name="related-topics"></a>See also

[Servizi di conferenza telefonica con accesso esterno in Office 365](set-up-audio-conferencing.md)
