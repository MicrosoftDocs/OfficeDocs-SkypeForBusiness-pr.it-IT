---
title: Confronto tra i provider di servizi di conferenza audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: b0d2b50e-def3-4bd8-82d4-a27f4b6f205c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Quando configurare conferenze Audio per Skype per le aziende e Teams Microsoft, è necessario scegliere un provider di servizi di conferenza audio. È possibile scegliere Microsoft o terze parti, come il provider di servizi di conferenza audio."
ms.openlocfilehash: f46801ae58e2d7f955ee347e4bf1af9567b19b0b
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="compare-audio-conferencing-providers"></a>Confronto tra i provider di servizi di conferenza audio

Quando configurare conferenze Audio per Skype per le aziende e Teams Microsoft, è necessario scegliere un provider di servizi di conferenza audio. È possibile scegliere Microsoft o terze parti, come il provider di servizi di conferenza audio. 
  
> [!IMPORTANT]
> Microsoft Teams utenti non possono utilizzare un provider di servizi di conferenza audio di terze parti. 
  
Provider di servizi di conferenza audio procedere come segue: 
  
- Fornire un *ponte per conferenze audio*. Bridge conferenza impostano i numeri di telefono di accesso esterno, pin e gli ID conferenza per le riunioni.
    
- Fornire il numero a pagamento, il numero verde e numeri di telefono internazionale che gli utenti cui accederà alla. Questi sono i numeri di telefono inclusi nell'invito alla riunione.
    
- Impostare la lingua che gli utenti possano rispondere quando si effettua la chiamata a una riunione.
    
- Creare riunioni ID conferenza utilizzati quando gli utenti sono una riunione.
    
- Assegnare l'organizzatore PIN per l'avvio di riunioni tramite telefono.
    
Utilizzare la seguente tabella per confrontare viene visualizzato se si sceglie Microsoft o un provider di servizi di conferenza audio di terze parti.
  
||||
|:-----|:-----|:-----|
|**Funzionalità** <br/> |**Microsoft (Office 365)** <br/> |**Terze parti** <br/> |
|Impostazione provider  <br/> |Facile da configurare. La maggior parte delle impostazioni sono automatiche.  <br/> |Difficili da impostare; è necessario eseguire operazioni manuali  <br/> |
|Gestione delle licenze  <br/> |È necessaria una licenza di **Conferenze Audio** . Vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> |Nessuna licenza, ma è comunque pagamento per utente  <br/> |
|Gestione  <br/> |Integrato nell'interfaccia di amministrazione di Office 365.  <br/> |Gestione manuale con terze parti  <br/> |
|Impostazioni utente  <br/> |Semplice  <br/> |Difficile  <br/> |
|Fatturazione  <br/> |Tramite Office 365  <br/> | Ulteriori informazioni, a terze parti <br/> |
|Assegnazione di ponte conferenza  <br/> |Automatico  <br/> |Richiede un'immissione manuale di ponte conferenza per ogni utente  <br/> |
|Gestione di ID conferenza  <br/> |Automatico  <br/> |Manuale  <br/> |
|Reimpostare l'ID conferenza della riunione  <br/> |Sì. Vedere [reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user.md).  <br/> |Sì, ma è necessario immettere manualmente  <br/> |
|Numeri di telefono verde  <br/> |Sì  <br/> |Sì  <br/> |
|Numeri di telefono interno a pagamento  <br/> |Sì  <br/> |Sì  <br/> |
|Numeri di telefono a pagamento internazionale  <br/> |Sì  <br/> |Sì  <br/> |
|Trasferire i numeri di telefono esistente  <br/> |Sì  <br/> |No  <br/> |
|Chiamata esterna / chiamare-me - nazionale  <br/> |Sì  <br/> |Sì  <br/> |
|Chiamata esterna / chiamare-me - internazionale  <br/> |Sì, ma è disponibile solo in alcuni paesi. Per un elenco dei paesi supportati, vedere [disponibilità paese e alle aree per le conferenze Audio e la chiamata dei piani](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) . <br/> |Sì  <br/> |
|Organizzatore della riunione può eseguire l'autenticazione tramite un PIN  <br/> |Sì  <br/> |No  <br/> |
|Tutti gli utenti dell'organizzazione possono eseguire l'autenticazione tramite PIN  <br/> |No  <br/> |No  <br/> |
|Pagina invito della riunione con numeri di telefono di accesso esterno predefiniti  <br/> |Sì  <br/> |Sì  <br/> |
|Pagina aggiuntiva audio con un elenco completo dei numeri di telefono di accesso esterno supportato  <br/> |Sì  <br/> |Sì  <br/> |
|Opzione per l'avvio di una riunione di terze parti senza un PIN  <br/> |Sì  <br/> |No  <br/> |
|Supporto di più lingue  <br/> |Sì. Vedere [audioconferenze lingue supportate](audio-conferencing-supported-languages.md).  <br/> |Sì  <br/> |
|Gestire le lingue per l'operatore automatico di servizi di conferenza  <br/> |Sì  <br/> |Sì  <br/> |
|Supporto per più paese/area geografica  <br/> |Sì. Vedere [disponibilità paese e alle aree per le conferenze Audio e la chiamata Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).  <br/> |Sì  <br/> |
|Gli utenti ascoltare la musica di attesa se non è avviato riunione o se la riunione è stata bloccata  <br/> |Sì  <br/> |No  <br/> |
|Imposta numero internazionale come predefinito numero di accesso (che mostra nell'invito alla riunione) per un utente  <br/> |Sì  <br/> |No  <br/> |
|Integrato esperienza per Skype per utenti Business Online o Microsoft Teams reimpostare la riunione ID conferenza e il PIN  <br/> |Sì  <br/> |No  <br/> |
|Supporto per le riunioni private con gli ID conferenza riunione dinamico  <br/> |Sì  <br/> |No  <br/> |
   
Se si sceglie Microsoft come provider di servizi di conferenza audio, vedere inoltre [la risoluzione dei problemi di conferenze Audio e problemi noti](audio-conferencing-troubleshooting-and-known-issues.md).
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing.md)

