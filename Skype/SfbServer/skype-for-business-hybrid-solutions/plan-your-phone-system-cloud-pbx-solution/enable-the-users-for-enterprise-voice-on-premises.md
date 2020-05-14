---
title: Abilitare gli utenti per VoIP aziendale in locale
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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Per consentire a un utente di utilizzare il sistema telefonico (cloud PBX), è necessario innanzitutto abilitarli per VoIP aziendale e assegnare loro un numero di telefono. A tale scopo, è possibile utilizzare la distribuzione locale mentre l'utente è ancora ospitato nella distribuzione locale.
ms.openlocfilehash: f02638f618b32190fafcded66550b5c3dcc52f2d
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221700"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Abilitare gli utenti per VoIP aziendale in locale
 
Per consentire a un utente di utilizzare il sistema telefonico (cloud PBX), è necessario innanzitutto abilitarli per VoIP aziendale e assegnare loro un numero di telefono. A tale scopo, è possibile utilizzare la distribuzione locale mentre l'utente è ancora ospitato nella distribuzione locale.
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Per abilitare un utente per VoIP aziendale in locale e assegnare un numero di telefono

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Usare il menu Start o il collegamento sul desktop per aprire il pannello di controllo di Skype for Business Server.
    
    È inoltre possibile aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **Utenti**.
    
4. Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.
    
5. Nella tabella fare clic sull'account utente di Skype for business online che si desidera abilitare per VoIP aziendale.
    
6. Scegliere **Mostra dettagli**dal menu **modifica** .
    
7. In **telefonia**, fare clic su **VoIP aziendale**.
    
8. Fare clic su **URI linea**e digitare un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200. Quindi fare clic su **commit**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Considerazioni speciali quando si abilitano gli utenti per VoIP aziendale in locale

In alcuni casi, potrebbe essere necessario modificare il modo in cui si abilitano gli utenti per VoIP aziendale per assicurarsi che siano in grado di effettuare e ricevere correttamente le chiamate. Se nella distribuzione sono presenti utenti che soddisfano le condizioni seguenti, eseguire i passaggi inclusi per abilitare l'utente per VoIP aziendale.
  
- Se un utente viene creato nell'annuncio locale e quindi è sincronizzato con Skype for business online senza essere abilitato per Skype for business o VoIP aziendale e non dispone di un set di LineURI, eseguire i seguenti cmdlet per ogni utente in questione, sostituendo i valori in \< \> con i valori effettivi dell'ambiente:
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Se un utente è già abilitato per Skype for business in locale, ma non è stato abilitato per VoIP aziendale o assegnato a un LineURI prima di essere spostato in Skype for business online, eseguire il seguente cmdlet per ogni utente:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Se un utente è già abilitato in Skype for business in locale ma non abilitato per VoIP aziendale, anche se è già stato assegnato un LineURI, eseguire il cmdlet seguente per ogni utente coinvolto:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


