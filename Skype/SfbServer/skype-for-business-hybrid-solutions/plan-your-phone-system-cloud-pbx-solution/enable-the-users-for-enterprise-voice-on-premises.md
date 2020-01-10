---
title: Consentire agli utenti di VoIP aziendale in locale
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Per consentire a un utente di usare il sistema telefonico in Office 365 (cloud PBX), è necessario prima di tutto abilitare Enterprise Voice e assegnare loro un numero di telefono. A questo scopo, puoi usare la distribuzione locale mentre l'utente è ancora ospitato nella distribuzione locale.
ms.openlocfilehash: 8bf8720896aa8115cb24d3b632b4ae576f466bcc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003476"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Consentire agli utenti di VoIP aziendale in locale
 
Per consentire a un utente di usare il sistema telefonico in Office 365 (cloud PBX), è necessario prima di tutto abilitare Enterprise Voice e assegnare loro un numero di telefono. A questo scopo, puoi usare la distribuzione locale mentre l'utente è ancora ospitato nella distribuzione locale.
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Per consentire a un utente di VoIP aziendale locale e assegnare un numero di telefono

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Usare il menu Start o il collegamento sul desktop per aprire il pannello di controllo di Skype for Business Server.
    
    È anche possibile aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **utenti**.
    
4. Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si vuole abilitare e quindi fare clic su **trova**.
    
5. Nella tabella fare clic sull'account utente di Skype for business online che si vuole abilitare per VoIP aziendale.
    
6. Nel menu **modifica** fare clic su **Mostra dettagli**.
    
7. In **telefonia**fare clic su **VoIP aziendale**.
    
8. Fare clic su **URI linea**e digitare un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200. Quindi fare clic su **commit**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Considerazioni speciali per consentire agli utenti di VoIP aziendale in locale

In alcuni casi potrebbe essere necessario modificare il modo in cui gli utenti possono eseguire la chiamata a VoIP aziendale per assicurarsi che possano effettuare e ricevere chiamate. Se nella distribuzione sono presenti utenti che soddisfano le condizioni seguenti, eseguire i passaggi inclusi per abilitare l'utente per VoIP aziendale.
  
- Se un utente viene creato nell'annuncio locale e quindi sincronizzato con Skype for business online senza essere abilitato per Skype for business o per VoIP aziendale e non ha un set di LineUri, eseguire i cmdlet seguenti per ogni utente interessato, sostituendo i valori in \< \> con i valori effettivi per l'ambiente:
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Se un utente è già abilitato per Skype for business in locale, ma non è stato abilitato per VoIP aziendale o assegnato un LineURI prima di essere spostato in Skype for business online, eseguire il cmdlet seguente per ogni utente:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Se un utente è già abilitato in Skype for business in locale ma non abilitato per VoIP aziendale, anche se è già stato assegnato un LineURI, eseguire il cmdlet seguente per ogni utente interessato:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


