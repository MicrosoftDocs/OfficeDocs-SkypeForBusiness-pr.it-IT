---
title: Abilitare gli utenti per VoIP aziendale locale
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Per consentire a un utente di usare Sistema telefonico (Cloud PBX), è necessario prima abilitarlo per VoIP aziendale e assegnargli un numero di telefono. A tale scopo, è possibile utilizzare la distribuzione locale mentre l'utente è ancora presente nella distribuzione locale.
ms.openlocfilehash: 29fd1eff47a73c7e3469ab7967a1f7cb0a006a75
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012510"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Abilitare gli utenti per VoIP aziendale locale
 
Per consentire a un utente di usare Sistema telefonico (Cloud PBX), è necessario prima abilitarlo per VoIP aziendale e assegnargli un numero di telefono. A tale scopo, è possibile utilizzare la distribuzione locale mentre l'utente è ancora presente nella distribuzione locale.

> [!Important]
> Skype for Business Online verrà ritirato il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.  Inoltre, la connettività PSTN tra l'ambiente locale tramite Skype for Business Server o Cloud Connector Edition e Skype for Business Online non sarà più supportata.  Informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto.](/MicrosoftTeams/direct-routing-landing-page)
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Per abilitare un utente per VoIP aziendale locale e assegnare un numero di telefono

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Usa il menu Start o il desktop per aprire il pannello Skype for Business Server pannello di controllo.
    
    È inoltre possibile aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server Di controllo.
    
3. Sulla barra di spostamento sinistra fare clic su **Utenti**.
    
4. Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.
    
5. Nella tabella fare clic sull'account Skype for Business online che si desidera abilitare per VoIP aziendale.
    
6. Scegliere **Mostra** dettagli dal menu **Modifica**.
    
7. In **Telefonia** fare clic **su VoIP aziendale**.
    
8. Fare **clic su URI** linea e digitare un numero di telefono normalizzato univoco, ad esempio `tel:+14255550200` . Quindi fare clic su **Commit**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Considerazioni speciali per l'abilitazione degli utenti VoIP aziendale locale

In alcuni casi, potrebbe essere necessario modificare il modo in cui si abilitano gli utenti per VoIP aziendale per assicurarsi che possano effettuare e ricevere correttamente le chiamate. Se nella distribuzione sono presenti utenti che soddisfano le condizioni seguenti, eseguire i passaggi inclusi per abilitare l'utente per VoIP aziendale.
  
- Se un utente viene creato nell'ad locale e quindi sincronizzato con Skype for Business Online senza essere abilitato per Skype for Business o per VoIP aziendale e non dispone di un set LineURI, eseguire i cmdlet seguenti per ogni utente interessato, sostituendo i valori in con i valori effettivi per \< \> l'ambiente:
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Se un utente è già abilitato per Skype for Business locale, ma non è stato abilitato per VoIP aziendale o è stato assegnato un LineURI prima di essere spostato in Skype for Business Online, eseguire il cmdlet seguente per ogni utente:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Se un utente è già abilitato in Skype for Business locale ma non abilitato per VoIP aziendale, anche se è già stato assegnato un lineuri, eseguire il cmdlet seguente per ogni utente interessato:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```