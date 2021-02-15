---
title: Abilitare gli utenti per VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Riepilogo: informazioni su come consentire agli utenti di effettuare e ricevere chiamate VoIP aziendale in Skype for Business Server.'
ms.openlocfilehash: 3c18836f1c2b03d2c6d50712f33d9e3a900b43b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830876"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Abilitare gli utenti per VoIP aziendale in Skype for Business Server
 
**Riepilogo:** Informazioni su come consentire agli utenti di effettuare e ricevere chiamate utilizzando VoIP aziendale in Skype for Business Server.
  
Dopo aver distribuito VoIP aziendale o Chiamata tramite lavoro, è possibile utilizzare le procedure seguenti per consentire a un utente di effettuare chiamate tramite VoIP aziendale:
  
> [!NOTE]
> Delle procedure seguenti, solo la prima può essere eseguita utilizzando il Pannello di controllo di Skype for Business Server. Per le procedure rimanenti, è possibile utilizzare solo Skype for Business Server Management Shell. 
  
- Abilitare l'account utente per VoIP aziendale.
    
- (Facoltativo) Assegnare all'account utente criteri vocali specifici dell'utente.
    
- (Facoltativo) Assegnare all'account utente un dial plan specifico dell'utente.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>Per abilitare un account utente per VoIP aziendale

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo amministrativo **CsVoiceAdministrator,** **CsServerAdministrator** o **CsAdministrator.**
    
2. Aprire il Pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **Utenti**.
    
4. Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.
    
5. Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.
    
6. Scegliere **Mostra dettagli** dal menu **Modifica**.
    
7. Nella pagina **Modifica utente di Skype for Business Server,** in **Telefonia,** fare clic **su VoIP aziendale**.
    
8. Fare clic su **URI linea** e quindi digitare un numero di telefono normalizzato univoco, ad esempio tel:+14255550200.
    
9. Fare clic su **Commit**.
    
Per completare l'abilitazione di un utente per VoIP aziendale, assicurarsi che all'utente siano assegnati un criterio vocale e un dial plan, globali (assegnati per impostazione predefinita) o specifici dell'utente. Per impostazione predefinita, a tutti gli utenti vengono assegnati un criterio vocale e un dial plan globali. Se nel sito principale dell'utente esistono criteri vocali o un dial plan a livello di sito, i criteri del sito verranno applicati automaticamente all'utente. Per applicare criteri vocali o un dial plan per utente, è necessario eseguire i cmdlet **Grant-CsVoicePolicy** e **Grant-CsDialPlan**. Per informazioni dettagliate, vedere le procedure seguenti in questo argomento.
## <a name="voice-policy-assignment"></a>Assegnazione di criteri vocali

I criteri vocali globali e a livello di sito vengono assegnati automaticamente a tutti gli account utente abilitati per VoIP aziendale. È inoltre possibile creare criteri vocali applicabili a utenti o gruppi specifici. Questi criteri per utente devono essere assegnati esplicitamente agli utenti o ai gruppi. Se si desidera utilizzare il criterio vocale globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione e passare alla sezione Assegnazione [dial plan](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) più avanti in questo argomento.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>Per assegnare criteri vocali specifici dell'utente

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**
    
3. Per assegnare un criterio vocale esistente a un utente, eseguire quanto segue al prompt dei comandi:
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Ad esempio:
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    In questo esempio, all'utente con il nome visualizzato Bob Kelly viene assegnato il criterio vocale denominato **VoicePolicyJapan.**
    
## <a name="dial-plan-assignment"></a>Assegnazione di dial plan
<a name="BKMK_DialPlanAssignment"> </a>

Per completare la configurazione degli account per gli utenti di VoIP aziendale o per gli utenti delle conferenze telefoniche con accesso esterno, è necessario che all'utente sia assegnato un dial plan. Gli account utente utilizzeranno automaticamente il dial plan globale oppure, se disponibile, il dial plan a livello di sito se non si assegna esplicitamente un dial plan per utente. Se si desidera utilizzare il dial plan globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>Per assegnare un dial plan specifico dell'utente

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**
    
3. Per assegnare un dial plan specifico dell'utente, al prompt dei comandi eseguire quanto segue:
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    Ad esempio:
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    In questo esempio, all'utente con il nome visualizzato Bob Kelly viene assegnato il dial plan utente con il nome **DialPlanJapan.**
    

