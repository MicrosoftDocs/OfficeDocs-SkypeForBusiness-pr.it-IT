---
title: Considerazioni su PSTN durante l'aggiornamento a Teams da Skype for Business
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Considerazioni vocali per l'aggiornamento da Skype for Business a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 72a12cf1dbcb69af7b71bf259568e4a53d1a3a33
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115544"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>Considerazioni su PSTN per l'aggiornamento a Teams da Skype for Business locale

Questo articolo descrive le considerazioni relative alla rete PSTN (Public Switched Telephone Network) durante l'aggiornamento a Teams.   


Gli articoli seguenti descrivono inoltre i concetti importanti per l'aggiornamento e i comportamenti di coesistenza:

- [Coesistenza di Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modalità di coesistenza - Riferimento](migration-interop-guidance-for-teams-with-skype.md)
- [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - L'uso di Sistema telefonico con Teams è supportato solo quando l'utente è in modalità TeamsOnly.  Se l'utente è in modalità Isole, Sistema telefonico è supportato solo con Skype for Business. 
 > - Le impostazioni di inoltro di chiamata, gruppo di chiamate del team e delega da Skype for Business non vengono migrate e dovranno essere ricreate per Teams.
 > - Per una panoramica generale delle funzionalità vocali cloud di Microsoft Teams e per decidere quale soluzione vocale Microsoft è più giusta per l'organizzazione, vedere Pianificare la [soluzione vocale di Teams.](cloud-voice-landing-page.md)


## <a name="pstn-calling-scenarios"></a>Scenari di chiamate PSTN

Esistono quattro possibili scenari di chiamata quando si attiva la modalità TeamsOnly:

- [Un utente in Skype for Business online, con un piano per chiamate Microsoft](#from-skype-for-business-online-with-microsoft-calling-plans). Al momento dell'aggiornamento, questo utente continuerà a avere un piano Per chiamate Microsoft.

- [Un utente in Skype for Business online,](#from-skype-for-business-online-with-on-premises-voice) con funzionalità vocali locali tramite Skype for Business locale o Cloud Connector Edition. L'aggiornamento dell'utente a Teams deve essere coordinato con la migrazione dell'utente al routing diretto per assicurarsi che l'utente TeamsOnly abbia la funzionalità PSTN.

- [Un utente in Skype for Business locale](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)con VoIP aziendale , che si trasferirà online e mantiene la connettività PSTN locale.  La migrazione di questo utente a Teams richiede lo spostamento dell'account Skype for Business locale dell'utente nel cloud e il coordinamento dello spostamento con la migrazione dell'utente al routing diretto. 

- [Un utente in Skype for Business locale](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)con VoIP aziendale , che si trasferirà online e usa un piano per chiamate Microsoft.  Per eseguire la migrazione di questo utente a Teams, è necessario spostare l'account Skype for Business locale dell'utente nel cloud e coordinare lo spostamento con A) la porta del numero di telefono dell'utente a un piano per chiamate Microsoft o B) assegnando un nuovo numero di abbonato dalle aree geografiche disponibili.

Questo articolo fornisce solo una panoramica generale. Per altre informazioni, vedere [Routing diretto del sistema](direct-routing-landing-page.md) telefonico e Piani per [chiamate.](calling-plan-landing-page.md) 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Da Skype for Business online con piani per chiamate Microsoft 

Questo è lo scenario di aggiornamento più semplice che coinvolge la voce. 

1. Assicurarsi che agli utenti sia stata assegnata una licenza di Teams. Per impostazione predefinita, quando si assegna una licenza di Microsoft 365 o Office 365, Teams è abilitato, quindi, a meno che in precedenza non sia stata disabilitata la licenza di Teams, non dovrebbe essere necessaria alcuna azione.

2.  Se gli utenti hanno già un piano per chiamate Microsoft con un numero di telefono, l'unica modifica richiesta è assegnare all'utente la modalità TeamsOnly in TeamsUpgradePolicy.  Prima di assegnare la modalità TeamsOnly, le chiamate PSTN in arrivo verranno effettuate nel client Skype for Business dell'utente. Dopo l'aggiornamento alla modalità TeamsOnly, le chiamate PSTN in arrivo verranno effettuate nel client Teams dell'utente.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Da Skype for Business online con voce locale

In questo scenario, l'utente è già in Skype for Business online, ma la sua connettività PSTN è locale, usando Skype for Business Server in modalità ibrida o Cloud Connector Edition. La migrazione di questi utenti alla modalità TeamsOnly con la funzionalità PSTN implica l'abilitazione per il routing diretto, in cui i trunk PSTN si connettono direttamente al servizio di routing diretto nel cloud, tramite il session border controller (SBC) locale.

Di seguito sono elencati i passaggi di base.  I passaggi da 1 a 4 sono elencati nella sequenza suggerita, ma possono essere evasi in qualsiasi ordine. La chiave è che tutte queste operazioni devono essere completate prima del passaggio 5.

1. Se si imposta il criterio a livello di tenant su una delle modalità Skype for Business, assicurarsi di assegnare esplicitamente la modalità Isole agli utenti delle Isole, come descritto in precedenza.

2. Configurare il tenant per il routing diretto. Vedere [Riepilogo della configurazione per tenant del routing diretto.](#summary-of-per-tenant-configuration-of-direct-routing)

3. Se si desidera, configurare vari criteri di Teams per questi utenti, ad esempio TeamsMessagingPolicy, TeamsMeetingPolicy e così via. Questa operazione può essere eseguita in qualsiasi momento, ma se si vuole verificare che gli utenti hanno la configurazione corretta quando vengono aggiornati, è meglio farlo prima che l'utente venga aggiornato alla modalità TeamsOnly.

4. Preparare gli utenti selezionati per la migrazione vocale: 
   - Se necessario, assegnare la licenza di Teams.  Presupponendo che l'utente sia già funzionante nella voce locale di Skype for Business Online, l'utente ha già Skype for Business Piano 2 e Microsoft Phone System. Lasciare entrambi i piani abilitati, inclusa la licenza Skype for Business Online Piano 2.  
   - Assegnare l'oggetto OnlineVoiceRoutingPolicy desiderato. 

5. Aggiornare l'utente: questi passaggi devono essere coordinati. 

   - In Microsoft 365 o Office 365 aggiornare l'utente alla modalità TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - In SBC configurare il routing vocale per abilitare le chiamate in arrivo inviando chiamate a Routing diretto invece che al Mediation Server locale.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Da Skype for Business Server locale, con VoIP aziendale, al routing diretto

In questo scenario, l'utente è ancora ospitata in Skype for Business locale e anche la connettività PSTN è locale. Eseguire la migrazione di questi utenti alla modalità TeamsOnly con la funzionalità PSTN significa abilitarli per il routing diretto e quindi spostare l'utente nel cloud. 
 
Di seguito sono elencati i passaggi di base.  I passaggi da 1 a 5 sono elencati nella sequenza suggerita, ma possono essere evasi in qualsiasi ordine. La chiave è che tutte queste operazioni devono essere completate prima del passaggio 6.

1. Se si imposta il criterio a livello di tenant su una delle modalità Skype for Business, assicurarsi di assegnare esplicitamente la modalità Isole agli utenti delle Isole, come descritto in precedenza.

2. Se non lo hai già fatto, [configura l'organizzazione per Skype for Business ibrido.](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

3. Configurare il tenant per il routing diretto. Vedere [Riepilogo della configurazione per tenant del routing diretto.](#summary-of-per-tenant-configuration-of-direct-routing)

4. Se si desidera, configurare vari criteri di Teams per questi utenti, ad esempio TeamsMessagingPolicy, TeamsMeetingPolicy e così via. Questa operazione può essere eseguita in qualsiasi momento, ma se si vuole verificare che gli utenti hanno la configurazione corretta quando vengono aggiornati, è meglio farlo prima che l'utente venga aggiornato a TeamsOnly.

5. Assegnare le licenze di Microsoft 365 o Office 365, se necessario.  L'utente deve avere sia Teams che Skype for Business Online Piano 2, oltre a Sistema telefonico. Se il Piano 2 di Skype for Business online è disabilitato, ri-abilitarlo.  

6. Aggiornare l'utente: questi passaggi devono essere coordinati. 

   - Usando gli strumenti locali di Skype for Business, esegui Move-CsUser con l'opzione -MoveToTeams. Se si usa una versione di Skype for Business Server che non supporta l'opzione -MoveToTeams, eseguire prima Move-CsUser e quindi assegnare la modalità TeamsOnly nella sessione remota di PowerShell del tenant o nella Console di amministrazione di Teams.

   - In SBC configurare il routing vocale per abilitare le chiamate in arrivo inviando chiamate a Routing diretto invece che al Mediation Server locale. 

   - In Microsoft 365 o Office 365: Assegnare il relativo OnlineVoiceRoutingPolicy per abilitare le chiamate in uscita. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Da Skype for Business Server locale, con VoIP aziendale, al piano chiamate Microsoft

In questo scenario, l'utente è ancora ospitata in Skype for Business locale e anche la connettività PSTN è locale. La migrazione di questi utenti alla modalità TeamsOnly con la funzionalità PSTN implica lo spostamento dell'utente nel cloud e il trasferimento del numero dal gestore precedente a un piano per chiamate Microsoft o l'assegnazione di un nuovo numero all'utente. 

Di seguito sono elencati i passaggi di base.I passaggi da 1 a 5 sono elencati nella sequenza suggerita, ma possono essere evasi in qualsiasi ordine. La chiave è che tutte queste operazioni devono essere completate prima del passaggio 6. 

1. Se si imposta il criterio a livello di tenant su una delle modalità Skype for Business, assicurarsi di assegnare esplicitamente la modalità Isole agli utenti delle Isole, come descritto in precedenza. 

2. Se non lo hai già fatto, [configura l'organizzazione per Skype for Business ibrido.](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

3. Se si desidera, configurare vari criteri di Teams per questi utenti, ad esempio TeamsMessagingPolicy, TeamsMeetingPolicy e così via. Questa operazione può essere eseguita in qualsiasi momento, ma se si vuole verificare che gli utenti hanno la configurazione corretta quando vengono aggiornati, è meglio farlo prima che l'utente venga aggiornato a TeamsOnly. 

4. Assegnare le licenze di Microsoft 365 o Office 365, se necessario.L'utente deve avere sia Teams che Skype for Business Online Piano 2, oltre a Sistema telefonico. Se il Piano 2 di Skype for Business online è disabilitato, ri-abilitarlo.  

5. Ottieni i numeri di telefono per gli utenti. Per informazioni dettagliate, vedere [Gestire i numeri di telefono per l'organizzazione.](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

   - Se si ri-usano di nuovo i numeri, inviare una richiesta di portabilità al gestore.  
   - In alternativa, è possibile acquisire nuovi numeri direttamente da Microsoft. 

6. Aggiornare l'utente e, se necessario, assegnare LineUri. Usando gli strumenti locali di Skype for Business, esegui Move-CsUser con l'opzione -MoveToTeams.  

    - Se si esegue il porting dei numeri in Microsoft, è consigliabile coordinare l'intervallo di esecuzione di questa operazione quando si verifica la porta. 

    - Se si usano nuovi numeri di Microsoft, è necessario modificare LineUri per l'utente. Questa operazione deve essere eseguita dopo che l'utente è stato spostato online con Set-CsOnlineVoiceUser.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Riepilogo della configurazione per tenant del routing diretto 

1. Verificare che il session border controller (SBC) sia supportato con Il routing diretto esaminando [questo elenco.](direct-routing-border-controllers.md) È anche necessario assicurarsi di avere la versione corretta del firmware.  

2. Associare il servizio SBC locale al servizio Teams Direct Routing. Per informazioni dettagliate, vedere [Associare SBC al servizio Routing diretto di Sistema telefonico.](direct-routing-configure.md) 

3. Questa configurazione è essenzialmente un mirror della configurazione locale. La configurazione online è costituita da: 
   - OnlineVoiceRoutingPolicy (in base al VoiceRoutingPolicy locale se si esegue la migrazione degli utenti da Skype for Business Online e in base a VoicePolicy se si esegue la migrazione degli utenti da utenti locali con VoIP aziendale).
   - OnlinePSTNUsage objects (based on-premises PSTN usage). 
   - Oggetti OnlineVoiceRoute (basati su VoiceRoute locale). 

Per altre informazioni, vedere [Configurare il routing diretto.](direct-routing-configure.md) 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Gestire la proprietà EnterpriseVoiceEnabled durante la migrazione 

Se si usa Il routing diretto o un piano per le chiamate Microsoft, un utente deve avere EnterpriseVoiceEnabled=true in Azure AD perché l'utente abbia la funzionalità PSTN.  EnterpriseVoiceEnabled ("Abilitato per Exchange") è una proprietà (non un criterio) presente sia in una directory locale che nel cloud. Il valore nel cloud è quello che conta per Teams.  La logica esatta per impostare EV-enabled su true dipende dallo scenario seguente: 

- Se l'utente è abilitato per EV in Skype for Business Server locale e all'utente viene assegnata una licenza sistema telefonico prima di spostare l'utente nel cloud con Move-CsUser, all'utente online verrà eseguito il provisioning con EV-enabled=true. 

- Se a un utente esistente di TeamsOnly o Skype for Business online viene assegnata una licenza Sistema telefonico, per impostazione predefinita l'opzione EV-enabled non è impostata su true.  Questo succede anche se un utente locale viene spostato nel cloud prima di assegnare la licenza sistema telefonico. In entrambi i casi, l'amministratore deve specificare il cmdlet seguente: 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>Collegamenti correlati

[Pianificare la soluzione vocale di Teams](cloud-voice-landing-page.md)

[Guida alla migrazione e all'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio di migrazione delle riunioni (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)