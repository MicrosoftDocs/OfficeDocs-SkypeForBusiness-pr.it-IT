---
title: Eseguire l'aggiornamento a teams da una distribuzione locale di Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Aggiornamento da Skype for Business a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 075960ef47f5d708a72cabc8e3c492786c2a5112
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940688"
---
# <a name="pstn-considerations-when-upgrading-to-teams-mdash-for-it-administrators"></a>Considerazioni PSTN quando si esegue l'aggiornamento ai team &mdash; per gli amministratori IT

Questo articolo descrive le considerazioni PSTN (Public Switched Telephone Network) durante l'aggiornamento ai team. Questo articolo è il sesto di diversi che descrivono i concetti di aggiornamento e l'implementazione per gli amministratori IT.  

- [Panoramica](upgrade-to-teams-on-prem-overview.md)
- [Metodi di aggiornamento](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Strumenti per la gestione dell'aggiornamento](upgrade-to-teams-on-prem-tools.md)
- [Considerazioni aggiuntive per le organizzazioni con Skype for business locale](upgrade-to-teams-on-prem-considerations.md)
- [Implementare l'aggiornamento](upgrade-to-teams-on-prem-implement.md)
- **Considerazioni PSTN (Public Switched Telephone Network)** (questo articolo)

Gli articoli seguenti descrivono inoltre importanti concetti di aggiornamento e comportamenti di coesistenza:

- [Coesistenza di teams e Skype for business](upgrade-to-teams-on-prem-coexistence.md)
- [Modalità di coesistenza-riferimento](migration-interop-guidance-for-teams-with-skype.md)
- [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > L'uso del sistema telefonico con teams è supportato solo quando l'utente è in modalità TeamsOnly.  Se l'utente è in modalità isole, il sistema telefonico è supportato solo con Skype for business. 


## <a name="pstn-calling-scenarios"></a>Scenari di chiamate PSTN

Quando si passa alla modalità TeamsOnly sono disponibili quattro possibili scenari di chiamata:

- [Un utente in Skype for business online con un piano di chiamata Microsoft](#from-skype-for-business-online-with-microsoft-calling-plans). Dopo l'aggiornamento, questo utente continuerà ad avere un piano per le chiamate Microsoft.

- [Un utente in Skype for business online con funzionalità vocali locali](#from-skype-for-business-online-with-on-premises-voice) tramite Skype for business locale o Cloud Connector Edition. L'aggiornamento dell'utente ai team deve essere coordinato con la migrazione dell'utente per indirizzare il routing per garantire che l'utente di TeamsOnly abbia funzionalità PSTN.

- [Un utente in Skype for business locale con Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), che si sposterà in online e continuerà a mantenere la connettività PSTN locale.  La migrazione di questo utente a teams richiede lo spostamento dell'account Skype for business locale dell'utente nel cloud e il coordinamento di tale spostamento con la migrazione dell'utente al routing diretto. 

- [Un utente in Skype for business locale con Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), che si sposterà in online e userà un piano di chiamata Microsoft.  La migrazione di questo utente a teams richiede lo spostamento dell'account Skype for business locale dell'utente nel cloud e il coordinamento di tale spostamento con una a) la porta del numero di telefono di tale utente in un piano di chiamata Microsoft o B) che assegna un nuovo numero di abbonato dalle aree disponibili.

Questo articolo fornisce solo una panoramica di alto livello. Per altre informazioni, Vedi piani di routing e [chiamate](calling-plan-landing-page.md) [dirette del sistema telefonico](direct-routing-landing-page.md) . 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Da Skype for business online con i piani per le chiamate Microsoft 

Questo è lo scenario di aggiornamento più semplice che include la voce. 

1. Assicurarsi che agli utenti sia stata assegnata una licenza teams. Per impostazione predefinita, quando si assegna una licenza Microsoft 365 o Office 365, teams è abilitato, quindi, a meno che non sia stata disabilitata in precedenza la licenza teams, non è necessario eseguire alcuna azione.

2.  Se gli utenti hanno già un piano di chiamata Microsoft con un numero di telefono, l'unica modifica necessaria consiste nell'assegnare la modalità di TeamsOnly utente in TeamsUpgradePolicy.  Prima di assegnare la modalità TeamsOnly, le chiamate PSTN in arrivo sbarcheranno nel client Skype for business dell'utente. Dopo l'aggiornamento alla modalità TeamsOnly, le chiamate PSTN in arrivo sbarcheranno nel client Teams dell'utente.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Da Skype for business online con la voce locale

In questo scenario l'utente è già in Skype for business online, ma la connettività PSTN è locale, usando Skype for Business Server in modalità ibrida o Cloud Connector Edition. La migrazione di questi utenti alla modalità TeamsOnly con funzionalità PSTN significa consentire loro il routing diretto, in cui i trunk PSTN si connettono direttamente al servizio di routing diretto nel cloud, tramite il controller di bordo della sessione locale (SBC).

I passaggi di base sono elencati di seguito.  I passaggi 1-4 sono elencati nella sequenza suggerita, ma possono essere eseguiti in qualsiasi ordine. La chiave è che tutti questi devono essere completati prima del passaggio 5.

1. Se si stanno impostando i criteri a livello di tenant in una delle modalità Skype for business, assicurarsi di avere un nonno per gli utenti delle isole esistenti assegnando esplicitamente la modalità isole, come descritto in precedenza.

2. Configurare il tenant per il routing diretto. Vedere [Riepilogo della configurazione per tenant di routing diretto](#summary-of-per-tenant-configuration-of-direct-routing).

3. Se lo si desidera, configurare i diversi criteri di team per questi utenti, ad esempio TeamsMessagingPolicy, TeamsMeetingPolicy e così via. Questa operazione può essere eseguita in qualsiasi momento, ma se si vuole garantire che gli utenti abbiano la configurazione corretta quando vengono aggiornati, è consigliabile eseguire questa operazione prima che l'utente venga aggiornato alla modalità TeamsOnly.

4. Preparare Seleziona utenti per la migrazione vocale: 
   - Se necessario, assegnare la licenza teams.  Supponendo che l'utente sia già funzionante in Skype for business online Voice locale, l'utente ha già Skype for Business Plan 2 e Microsoft Phone System. Lascia entrambi i piani abilitati, inclusa la licenza di Skype for business online Plan 2.  
   - Assegnare il OnlineVoiceRoutingPolicy desiderato. 

5. Aggiornare l'utente: questi passaggi devono essere coordinati. 

   - In Microsoft 365 o Office 365 aggiornare l'utente alla modalità TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - In SBC configurare il routing vocale per abilitare le chiamate in arrivo inviando le chiamate al routing diretto anziché al server di mediazione locale.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Da Skype for Business Server locale, con VoIP aziendale, per indirizzare il routing

In questo scenario l'utente è ancora ospitato in Skype for business locale e la connettività PSTN è anche locale. La migrazione di questi utenti alla modalità TeamsOnly con funzionalità PSTN significa consentire loro il routing diretto e quindi spostare l'utente nel cloud. 
 
I passaggi di base sono elencati di seguito.  I passaggi 1-5 sono elencati nella sequenza suggerita, ma possono essere eseguiti in qualsiasi ordine. La chiave è che tutti questi elementi devono essere completati prima del passaggio 6.

1. Se si vuole impostare il criterio a livello di tenant su una delle modalità Skype for business, assicurarsi che gli utenti delle isole esistenti vengano esplicitamente assegnati alla modalità isole, come descritto in precedenza.

2. Se non lo hai ancora fatto, [Configura l'organizzazione per Skype for business Hybrid](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Configurare il tenant per il routing diretto. Vedere [Riepilogo della configurazione per tenant di routing diretto](#summary-of-per-tenant-configuration-of-direct-routing).

4. Se lo si desidera, configurare i diversi criteri di team per questi utenti (ad esempio TeamsMessagingPolicy, TeamsMeetingPolicy e così via). Questa operazione può essere eseguita in qualsiasi momento, ma se si vuole garantire che gli utenti abbiano la configurazione corretta quando vengono aggiornati, è consigliabile eseguire questa operazione prima che l'utente venga aggiornato a TeamsOnly.

5. Assegnare le licenze Microsoft 365 o Office 365, se necessario.  L'utente dovrebbe avere sia teams che Skype for business online Plan 2, oltre a un sistema telefonico. Se il piano 2 di Skype for business online è disabilitato, riattivarlo.  

6. Aggiornare l'utente: questi passaggi devono essere coordinati. 

   - Usando gli strumenti di Skype for business locali, Esegui Move-CsUser con-MoveToTeams switch. Se si usa una versione di Skype for Business Server che non supporta l'opzione-MoveToTeams, eseguire prima di tutto Move-CsUser e quindi assegnare la modalità TeamsOnly nella console di amministrazione remota di PowerShell o teams.

   - In SBC configurare il routing vocale per abilitare le chiamate in arrivo inviando le chiamate al routing diretto anziché al server di mediazione locale. 

   - In Microsoft 365 o Office 365: assegnare il OnlineVoiceRoutingPolicy pertinente per abilitare le chiamate in uscita. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Da Skype for Business Server locale, con Enterprise Voice, al piano per le chiamate Microsoft

In questo scenario l'utente è ancora ospitato in Skype for business locale e la connettività PSTN è anche locale. La migrazione di questi utenti alla modalità TeamsOnly con funzionalità PSTN significa spostare l'utente nel cloud e trasferire il proprio numero dal vecchio gestore a un piano di chiamata Microsoft o assegnare un nuovo numero all'utente. 

I passaggi di base sono elencati di seguito.I passaggi 1-5 sono elencati nella sequenza suggerita, ma possono essere eseguiti in qualsiasi ordine. La chiave è che tutti questi elementi devono essere completati prima del passaggio 6. 

1. Se si vuole impostare il criterio a livello di tenant su una delle modalità Skype for business, assicurarsi che gli utenti delle isole esistenti vengano esplicitamente assegnati alla modalità isole, come descritto in precedenza. 

2. Se non lo hai ancora fatto, [Configura l'organizzazione per Skype for business Hybrid](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity). 

3. Se lo si desidera, configurare i diversi criteri di team per questi utenti, ad esempio TeamsMessagingPolicy, TeamsMeetingPolicy e così via. Questa operazione può essere eseguita in qualsiasi momento, ma se si vuole garantire che gli utenti abbiano la configurazione corretta quando vengono aggiornati, è consigliabile eseguire questa operazione prima che l'utente venga aggiornato a TeamsOnly. 

4. Assegnare le licenze Microsoft 365 o Office 365, se necessario.L'utente dovrebbe avere sia teams che Skype for business online Plan 2, oltre a un sistema telefonico. Se il piano 2 di Skype for business online è disabilitato, riattivarlo.  

5. Ottenere i numeri di telefono per gli utenti. Per informazioni dettagliate, vedere [gestire i numeri di telefono per l'organizzazione](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

   - Se si riutilizzeranno i numeri, inviare una richiesta di conversione al gestore.  
   - In alternativa, è possibile acquisire nuovi numeri direttamente da Microsoft. 

6. Aggiornare l'utente e, se necessario, assegnare LineUri. Usando gli strumenti di Skype for business locali, Esegui Move-CsUser con l'opzione-MoveToTeams.  

    - Se si trasferiscono i numeri in Microsoft, è consigliabile coordinare l'intervallo di questa operazione quando si verifica la porta. 

    - Se si usano nuovi numeri da Microsoft, è necessario modificare il LineUri per l'utente. Questa operazione deve essere eseguita dopo che l'utente è stato spostato online usando set-CsOnlineVoiceUser.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Riepilogo della configurazione per tenant del routing diretto 

1. Verificare che il controller di bordo della sessione (SBC) sia supportato con il routing diretto rivedendo [questo elenco](direct-routing-border-controllers.md). Devi anche assicurarti di avere la versione corretta del firmware.  

2. Associare il proprio SBC locale al servizio di routing diretto di teams. Per informazioni dettagliate, vedere [associare il SBC al servizio di routing diretto del sistema telefonico](direct-routing-configure.md). 

3. Questa configurazione è essenzialmente uno specchio della configurazione locale. La configurazione online è costituita da: 
   - OnlineVoiceRoutingPolicy (basato sul VoiceRoutingPolicy locale se si esegue la migrazione degli utenti da Skype for business online e basato su VoicePolicy se la migrazione degli utenti è locale con Enterprise Voice).
   - Oggetti OnlinePSTNUsage (basati sull'utilizzo PSTN locale). 
   - Oggetti OnlineVoiceRoute (basati VoiceRoute locale). 

Per altre informazioni, vedere [configurare il routing diretto](direct-routing-configure.md). 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Gestire la proprietà EnterpriseVoiceEnabled durante la migrazione 

Se si usa il routing diretto o un piano di chiamata Microsoft, un utente deve avere EnterpriseVoiceEnabled = true in Azure AD affinché l'utente abbia funzionalità PSTN.  EnterpriseVoiceEnabled ("EV-Enabled") è una proprietà (non un criterio) che esiste sia in una directory locale che nel cloud. Il valore nel cloud è importante per i team.  La logica esatta per il modo in cui l'abilitazione EV viene impostata su true dipende dallo scenario seguente: 

- Se l'utente è abilitato per l'abilitazione EV in Skype for Business Server locale e viene assegnata una licenza di sistema telefonico all'utente prima di spostare l'utente nel cloud con Move-CsUser, verrà eseguito il provisioning dell'utente online con EV-Enabled = true. 

- Se a un utente esistente di TeamsOnly o Skype for business online viene assegnata una licenza di sistema telefonico, EV-Enabled non è impostato su true per impostazione predefinita.  Questo accade anche se un utente locale viene spostato nel cloud prima di assegnare la licenza per il sistema telefonico. In entrambi i casi, l'amministratore deve specificare il cmdlet seguente: 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>Collegamenti correlati

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio di migrazione delle riunioni (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

