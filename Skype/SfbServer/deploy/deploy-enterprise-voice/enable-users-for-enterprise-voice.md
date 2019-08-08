---
title: Consentire agli utenti di VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Riepilogo: informazioni su come consentire agli utenti di effettuare e ricevere chiamate tramite VoIP aziendale in Skype for Business Server.'
ms.openlocfilehash: cf9aab0f104582c57e745c95ae5cf8f24f07b3a5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240611"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Consentire agli utenti di VoIP aziendale in Skype for Business Server
 
**Riepilogo:** Informazioni su come consentire agli utenti di effettuare e ricevere chiamate tramite VoIP aziendale in Skype for Business Server.
  
Dopo aver distribuito VoIP aziendale o chiamata tramite lavoro, è possibile usare le procedure seguenti per consentire a un utente di effettuare chiamate tramite VoIP aziendale:
  
> [!NOTE]
> Delle procedure seguenti, solo il primo può essere eseguito usando il pannello di controllo di Skype for Business Server. Per le procedure rimanenti, è possibile usare solo Skype for Business Server Management Shell. 
  
- Abilitare l'account utente per VoIP aziendale.
    
- Opzionale Assegnare l'account utente a un criterio vocale specifico per l'utente.
    
- Opzionale Assegna l'account utente a un dial plan specifico per l'utente.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>Per abilitare un account utente per VoIP aziendale

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo di amministratore di **CsVoiceAdministrator**, **CsServerAdministrator**o **CsAdministrator** .
    
2. Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **utenti**.
    
4. Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si vuole abilitare e quindi fare clic su **Trovare**.
    
5. Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.
    
6. Nel menu **modifica** fare clic su **Mostra dettagli**.
    
7. Nella pagina **modifica utenti di Skype for Business Server** , in **telefonia**, fare clic su **VoIP aziendale**.
    
8. Fare clic su **URI linea**e quindi digitare un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200.
    
9. Fare clic su **Commit**.
    
Per completare l'abilitazione di un utente per VoIP aziendale, assicurati che all'utente sia assegnato un criterio vocale e un dial plan, sia globale (assegnato per impostazione predefinita) che specifico per l'utente. Per impostazione predefinita, a tutti gli utenti viene assegnato un criterio vocale globale e un dial plan. Se un criterio vocale o un dial plan esiste a livello di sito per il sito in cui si trova l'account utente, i criteri del sito verranno applicati automaticamente all'utente. Per applicare un criterio vocale per utente o un dial plan a un utente, è necessario eseguire i cmdlet **Grant-CsVoicePolicy** e **Grant-CsDialPlan** . Per informazioni dettagliate, vedere le procedure seguenti in questo argomento.
## <a name="voice-policy-assignment"></a>Assegnazione dei criteri vocali

I criteri vocali globali e a livello di sito vengono assegnati automaticamente a tutti gli account utente abilitati per VoIP aziendale. È anche possibile creare criteri vocali applicabili a utenti o gruppi specifici. Questi criteri per utente devono essere assegnati in modo esplicito agli utenti o ai gruppi. Se si vuole usare il criterio vocale globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione e continuare la sezione [assegnazione di dial plan](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) più avanti in questo argomento.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>Per assegnare un criterio vocale specifico per l'utente

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Per assegnare un criterio vocale utente esistente a un utente, eseguire le operazioni seguenti al prompt dei comandi:
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Ad esempio:
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    In questo esempio l'utente con il nome visualizzato Bob Kelly viene assegnato il criterio vocale con il nome **VoicePolicyJapan**.
    
## <a name="dial-plan-assignment"></a>Assegnazione di dial plan
<a name="BKMK_DialPlanAssignment"> </a>

Per completare la configurazione dell'account utente per gli utenti di VoIP aziendale o per gli utenti di servizi di conferenza telefonica con accesso esterno, l'utente deve essere assegnato a un dial plan. Gli account utente useranno automaticamente il dial plan globale o, se disponibile, il dial plan a livello di sito, quando non si assegna esplicitamente un dial plan per utente esistente. Se si vuole usare il dial plan globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>Per assegnare un dial plan specifico dell'utente

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Per assegnare un dial plan specifico per l'utente, eseguire la procedura seguente al prompt dei comandi:
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    Ad esempio:
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    In questo esempio l'utente con il nome visualizzato Bob Kelly viene assegnato al dial plan utente con il nome **DialPlanJapan**.
    

