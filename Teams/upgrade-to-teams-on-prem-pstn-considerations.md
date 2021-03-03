---
title: Considerazioni su PSTN durante l'aggiornamento a Teams da Skype for Business
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Considerazioni sulle funzionalità vocali per l'aggiornamento da Skype for Business a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9887eec2a99fec9a6f4964899c6e631046b28897
ms.sourcegitcommit: 54140f6f8f2279a0eaf2e9c79699d6cff306791c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50410573"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>Considerazioni su PSTN per l'aggiornamento a Teams dalla distribuzione locale di Skype for Business

Questo articolo descrive considerazioni sulla rete PSTN (Public Switched Telephone Network) durante l'aggiornamento a Teams.   


Gli articoli seguenti descrivono inoltre concetti importanti sull'aggiornamento e comportamenti di coesistenza:

- [Coesistenza di Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modalità di coesistenza - Riferimento](migration-interop-guidance-for-teams-with-skype.md)
- [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - L'uso di Sistema telefonico con Teams è supportato solo quando l'utente è in modalità TeamsOnly.  Se l'utente è in modalità Isole, Sistema telefonico è supportato solo con Skype for Business. 
 > - Le impostazioni di inoltro di chiamata, gruppo di chiamata di gruppo e delega di Skype for Business non vengono migrate e dovranno essere ricreate per Teams.
 > - Per una panoramica generale delle funzionalità vocali cloud di Microsoft Teams e per decidere quale soluzione vocale Di Microsoft è più efficace per la propria organizzazione, vedere Pianificare la soluzione vocale [di Teams.](cloud-voice-landing-page.md)


## <a name="pstn-calling-scenarios"></a>Scenari di chiamate PSTN

Quando si passare alla modalità TeamsOnly, è possibile che ci siano quattro scenari di chiamata possibili:

- [Un utente in Skype for Business online, con un Piano per chiamate Microsoft.](#from-skype-for-business-online-with-microsoft-calling-plans) Al momento dell'aggiornamento, l'utente continuerà a disporre di un piano per le chiamate Microsoft.

- [Un utente in Skype for Business online,](#from-skype-for-business-online-with-on-premises-voice) con funzionalità vocali locali tramite Skype for Business locale o Cloud Connector Edition. L'aggiornamento dell'utente a Teams deve essere coordinato con la migrazione dell'utente al routing diretto per garantire che l'utente TeamsOnly abbia funzionalità PSTN.

- [Un utente in Skype for Business](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)locale con VoIP aziendale , che si locerà online mantenendo la connettività PSTN locale.  La migrazione di questo utente a Teams richiede lo spostamento dell'account Skype for Business locale dell'utente nel cloud e il coordinamento del trasferimento con la migrazione dell'utente al routing diretto. 

- [Un utente in Skype for Business locale](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)con VoIP aziendale, che si locerà online e utilizzando un piano per le chiamate Microsoft.  La migrazione di questo utente a Teams richiede lo spostamento dell'account Skype for Business locale dell'utente nel cloud e il coordinamento del trasferimento con A) il trasferimento del numero di telefono dell'utente a un piano per chiamate Microsoft o B) l'assegnazione di un nuovo numero di abbonato dalle aree geografiche disponibili.

Questo articolo fornisce solo una panoramica generale. Per ulteriori informazioni, consulta [Routing diretto](direct-routing-landing-page.md) e Piani per chiamate del Sistema [telefonico.](calling-plan-landing-page.md) 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Da Skype for Business online con piani per chiamate Microsoft 

Questo è lo scenario di aggiornamento più semplice che implica la voce. 

1. Assicurarsi che agli utenti sia stata assegnata una licenza di Teams. Per impostazione predefinita, quando si assegna una licenza di Microsoft 365 o Office 365, Teams viene abilitato, quindi, a meno che in precedenza non sia stata disabilitata la licenza di Teams, non è necessario alcun intervento.

2.  Se gli utenti hanno già un Piano per chiamate Microsoft con un numero di telefono, l'unica modifica necessaria è assegnare la modalità TeamsOnly utente in TeamsUpgradePolicy.  Prima di assegnare la modalità TeamsOnly, le chiamate PSTN in arrivo verranno effettuate nel client Skype for Business dell'utente. Dopo l'aggiornamento alla modalità TeamsOnly, le chiamate PSTN in arrivo verranno effettuate nel client Teams dell'utente.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Da Skype for Business online con voce locale

In questo scenario, l'utente è già in Skype for Business online, ma la sua connettività PSTN è locale, usando Skype for Business Server in modalità ibrida o Cloud Connector Edition. La migrazione di questi utenti alla modalità TeamsOnly con funzionalità PSTN implica l'abilitazione per il routing diretto, in cui i trunk PSTN si connettono direttamente al servizio di instradamento diretto nel cloud, tramite il controller dei confini della sessione (SBC) locale.

I passaggi di base sono elencati di seguito.  I passaggi da 1 a 4 sono elencati nella sequenza suggerita, ma possono essere eati in qualsiasi ordine. È fondamentale completare tutte queste operazioni prima del passaggio 5.

1. Se si imposta il criterio a livello di tenant su una delle modalità di Skype for Business, assicurarsi di eliminare eventuali utenti di Isole esistenti assegnando esplicitamente la modalità Isole, come descritto in precedenza.

2. Configurare il tenant per il routing diretto. Vedere [il riepilogo della configurazione per tenant del routing diretto.](#summary-of-per-tenant-configuration-of-direct-routing)

3. Se si desidera, configurare vari criteri di Teams per questi utenti (ad esempio TeamsMessagingPolicy, TeamsMeetingPolicy, ecc.). Questa operazione può essere eseguita in qualsiasi momento, ma se vuoi assicurarti che gli utenti siano in grado di eseguire la configurazione corretta quando vengono aggiornati, è meglio farlo prima che l'utente venga aggiornato alla modalità TeamsOnly.

4. Preparare utenti selezionati per la migrazione vocale: 
   - Se necessario, assegnare la licenza di Teams.  Supponendo che l'utente sia già in funzione nella voce locale di Skype for Business online, l'utente dispone già di Skype for Business Piano 2 e del Sistema telefonico Microsoft. Lasciare abilitati entrambi i piani, inclusa la licenza di Skype for Business Online Piano 2.  
   - Assegnare il valore desiderato di OnlineVoiceRoutingPolicy. 

5. Aggiorna l'utente: questi passaggi devono essere coordinati. 

   - In Microsoft 365 o Office 365, aggiornare l'utente alla modalità TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - Su SBC, configurare il routing vocale per abilitare le chiamate in arrivo inviando chiamate a Direct Routing invece che a Mediation Server locale.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Da Skype for Business Server locale, con VoIP aziendale, al routing diretto

In questo scenario, l'utente è ancora presente in Skype for Business locale e anche la sua connettività PSTN è locale. La migrazione di questi utenti alla modalità TeamsOnly con funzionalità PSTN implica l'abilitazione per il routing diretto e quindi lo spostamento dell'utente nel cloud. 
 
I passaggi di base sono elencati di seguito.  I passaggi da 1 a 5 sono elencati nella sequenza suggerita, ma possono essere eati in qualsiasi ordine. È fondamentale completare tutte queste operazioni prima del passaggio 6.

1. Se il criterio a livello di tenant verrà impostato su una delle modalità di Skype for Business, assicurarsi di illustrare gli attuali utenti delle Isole assegnando esplicitamente la modalità Isole, come descritto in precedenza.

2. Se non lo hai già fatto, configura [l'organizzazione per Skype for Business ibrido.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

3. Configurare il tenant per il routing diretto. Vedere [il riepilogo della configurazione per tenant del routing diretto.](#summary-of-per-tenant-configuration-of-direct-routing)

4. Se si desidera, configurare vari criteri di Teams per questi utenti (ad esempio TeamsMessagingPolicy, TeamsMeetingPolicy, ecc.). Questa operazione può essere eseguita in qualsiasi momento, ma se si vuole assicurarsi che gli utenti siano in grado di eseguire la configurazione corretta quando vengono aggiornati, è meglio farlo prima che l'utente venga aggiornato a TeamsOnly.

5. Se necessario, assegnare le licenze di Microsoft 365 o Office 365.  L'utente deve disporre sia di Teams che di Skype for Business Online Piano 2, nonché del Sistema telefonico. Se Skype for Business online Piano 2 è disabilitato, ri enablerlo.  

6. Aggiorna l'utente: questi passaggi devono essere coordinati. 

   - Utilizzando gli strumenti locali di Skype for Business, esegui i Move-CsUser con l'opzione -MoveToTeams. Se si usa una versione di Skype for Business Server che non supporta l'opzione -MoveToTeams, eseguire prima Move-CsUser e quindi assegnare la modalità TeamsOnly nella sessione remota del tenant di PowerShell o nella console di amministrazione di Teams.

   - Su SBC, configurare il routing vocale per abilitare le chiamate in arrivo inviando chiamate a Direct Routing invece che a Mediation Server locale. 

   - In Microsoft 365 o Office 365: assegnare il relativo OnlineVoiceRoutingPolicy per abilitare le chiamate in uscita. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Da Skype for Business Server locale, con piano VoIP aziendale, al Piano per chiamate Microsoft

In questo scenario, l'utente è ancora presente in Skype for Business locale e anche la sua connettività PSTN è locale. La migrazione di questi utenti alla modalità TeamsOnly con funzionalità PSTN implica lo spostamento dell'utente nel cloud e la portabilità del numero dal gestore precedente a un piano per le chiamate Microsoft o l'assegnazione di un nuovo numero all'utente. 

I passaggi di base sono elencati di seguito.I passaggi da 1 a 5 sono elencati nella sequenza suggerita, ma possono essere eati in qualsiasi ordine. È fondamentale completare tutte queste operazioni prima del passaggio 6. 

1. Se il criterio a livello di tenant verrà impostato su una delle modalità di Skype for Business, assicurarsi di illustrare gli attuali utenti delle Isole assegnando esplicitamente la modalità Isole, come descritto in precedenza. 

2. Se non lo hai già fatto, configura [l'organizzazione per Skype for Business ibrido.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

3. Se si desidera, configurare vari criteri di Teams per questi utenti (ad esempio TeamsMessagingPolicy, TeamsMeetingPolicy, ecc.). Questa operazione può essere eseguita in qualsiasi momento, ma se si vuole assicurarsi che gli utenti siano in grado di eseguire la configurazione corretta quando vengono aggiornati, è meglio farlo prima che l'utente venga aggiornato a TeamsOnly. 

4. Se necessario, assegnare le licenze di Microsoft 365 o Office 365.L'utente deve disporre sia di Teams che di Skype for Business Online Piano 2, nonché del Sistema telefonico. Se Skype for Business online Piano 2 è disabilitato, ri enablerlo.  

5. Ottieni numeri di telefono per i tuoi utenti. Per informazioni dettagliate, vedere [Gestire i numeri di telefono per l'organizzazione.](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

   - Se utilizzi nuovamente i numeri, invia una richiesta di portabilità al tuo gestore.  
   - In alternativa, è possibile acquisire nuovi numeri direttamente da Microsoft. 

6. Aggiornare l'utente e, se necessario, assegnare LineUri. Utilizzando gli strumenti locali di Skype for Business, esegui i Move-CsUser con l'opzione -MoveToTeams.  

    - Se si esegue la portabilità dei numeri in Microsoft, è consigliabile coordinare l'intervallo dell'operazione in modo che si verifichi quando si verifica la porta. 

    - Se si usano nuovi numeri di Microsoft, è necessario modificare LineUri per l'utente. Questa operazione deve essere eseguita dopo lo spostamento online dell'utente tramite Set-CsOnlineVoiceUser.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Riepilogo della configurazione per tenant del routing diretto 

1. Esaminare questo elenco per verificare che il controller dei confini della sessione (SBC) sia supportato [con l'instradamento diretto.](direct-routing-border-controllers.md) È anche necessario verificare di avere la versione corretta del firmware.  

2. Associare il servizio SBC locale al servizio di instradamento diretto di Teams. Per informazioni dettagliate, vedere [Associare SBC al servizio di instradamento diretto del sistema telefonico.](direct-routing-configure.md) 

3. Questa configurazione è essenzialmente speculare alla configurazione locale. La configurazione online è costituita da: 
   - OnlineVoiceRoutingPolicy (basato sul valore VoiceRoutingPolicy locale se si esegue la migrazione degli utenti da Skype for Business Online e su VoicePolicy se si esegue la migrazione degli utenti dalla distribuzione locale con VoIP aziendale).
   - Oggetti OnlinePSTNUsage (in base all'utilizzo di PSTN locale). 
   - Oggetti OnlineVoiceRoute (basati su VoiceRoute locale). 

Per altre informazioni, vedere [Configurare l'instradamento diretto.](direct-routing-configure.md) 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Gestire la proprietà EnterpriseVoiceEnabled durante la migrazione 

Se si usa l'instradamento diretto o un piano per le chiamate Microsoft, è necessario che l'utente abbia EnterpriseVoiceEnabled=true in Azure AD per poter usare la funzionalità PSTN.  EnterpriseVoiceEnabled ("EV-enabled") è una proprietà (non un criterio) presente sia in una directory locale che nel cloud. Il valore nel cloud è ciò che conta per Teams.  La logica esatta per cui EV-enabled viene impostata su true dipende dallo scenario seguente: 

- Se l'utente è abilitato per EV in Skype for Business Server locale e all'utente viene assegnata una licenza Sistema telefonico prima di trasferire l'utente nel cloud con Move-CsUser, per l'utente online verrà eseguito il provisioning con EV-enabled=true. 

- Se a un utente Esistente TeamsOnly o Skype for Business online viene assegnata una licenza Sistema telefonico, EV-enabled non è impostato su true per impostazione predefinita.  Ciò si verifica anche se un utente locale viene spostato nel cloud prima di assegnare la licenza Sistema telefonico. In entrambi i casi, l'amministratore deve specificare il cmdlet seguente: 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>Collegamenti correlati

[Pianificare la soluzione vocale di Teams](cloud-voice-landing-page.md)

[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio MMS (Meeting Migration Service)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

