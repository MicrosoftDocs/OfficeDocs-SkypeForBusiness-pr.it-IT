---
title: "Problemi noti di piani di chiamata"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0

description: "Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. "
---

# Problemi noti di piani di chiamata

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
Una nuova caratteristica di Skype for Business online sono i piani di chiamata in Office 365. Esistono problemi correnti che vengono rilevati, attivamente esaminati e verranno risolto potenzialmente quando la caratteristica viene aggiornato nella build futuri in Office 365 e Skype for Business online e sono elencate di seguito.
  
## Problemi noti di piani di chiamata

|**Problemi noti**|**Commenti**|
|:-----|:-----|
|Passaggio da Tech Preview licenze per le licenze di produzione per la chiamata plan di messaggistica unificata non vengono aggiornate automaticamente alla licenza.  <br/> |Acquistare le nuove licenze prima di tutto in modo che siano pronti per l'assegnazione agli utenti. Rimuovere la licenza promozionale (Tech Preview) da un utente e quindi assegnare **immediatamente** le nuove licenze **Chiamate nazionali pianificare** e/o **La chiamata a pianificare internazionale** all'utente. <br/> Se rimuovi e aggiungi licenze per più utenti, è estremamente importante revocare le licenze a tutti gli utenti con Windows PowerShell e assegnare **IMMEDIATAMENTE** le licenze per tutti gli utenti sempre con Windows PowerShell. Così facendo si ha la certezza che non si verifichino interruzioni del servizio quando si assegna un numero considerevole di licenze. Per ottenere script PowerShell di esempio, consulta la sezione[Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> > [!NOTE]> Se si utilizza la connettività PSTN locale per gli utenti ibrida, è  *solo*  necessario assegnare una licenza di **Sistema telefonico**. **Non** devono inoltre assegnare un piano tariffario vocali.> Tuttavia, se si attiva la chiamata plan di messaggistica unificata in Office 365 per gli utenti in Office 365, è necessario ancora assegnare una licenza **Chiamate nazionali pianificare** e/o **La chiamata a pianificare internazionale** per tali utenti. Vedere[Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).           |
   
## Argomenti correlati

[Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)
  
[Periodo di chiamata in uscita di conferenze audio](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

