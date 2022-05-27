---
title: Considerazioni su PSTN quando si esegue l'aggiornamento a Teams da Skype for Business
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Considerazioni vocali per l'aggiornamento da Skype for Business a Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 130ff6164de3cae82902487f70dd6eaefb631c27
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681347"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>Considerazioni su PSTN per l'aggiornamento a Teams da Skype for Business locale

Questo articolo descrive le considerazioni su PSTN (Public Switched Telephone Network) quando si esegue l'aggiornamento a Teams.

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

Gli articoli seguenti descrivono importanti concetti di aggiornamento e comportamenti di coesistenza:

- [Coesistenza di Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modalità di coesistenza - Riferimento](migration-interop-guidance-for-teams-with-skype.md)
- [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)

> [!NOTE]
>
> - L'uso di Sistema telefonico con Teams è supportato solo quando all'account dell'utente viene assegnato un criterio di aggiornamento Teams con modalità solo Teams.
> - L'uso di Sistema telefonico con Skype for Business è supportato solo quando all'account dell'utente viene assegnato un criterio di aggiornamento Teams con una modalità SfB.
> - Sistema telefonico non è supportato quando all'account dell'utente viene assegnato un criterio di aggiornamento Teams con la modalità Isole.
> - Le impostazioni di inoltro di chiamata, di gruppo autorizzato alla risposta e di delega di Skype for Business non vengono trasferite e dovranno essere ricreate per Teams.
> - Per una panoramica generale delle funzionalità di Microsoft Teams voce cloud e per decidere quale soluzione Microsoft voice è adatta per la tua organizzazione, vedi [Pianificare la soluzione Teams voce](cloud-voice-landing-page.md).

## <a name="pstn-calling-scenarios"></a>Scenari di chiamate PSTN

Ci sono quattro possibili scenari di chiamata quando si passa alla modalità TeamsOnly:

- [Un utente in Skype for Business online, con un piano per chiamate Microsoft](#from-skype-for-business-online-with-microsoft-calling-plans). Al momento dell'aggiornamento, l'utente continuerà ad avere un piano per le chiamate Microsoft.

- [Un utente in Skype for Business Online, con funzionalità vocali locali](#from-skype-for-business-online-with-on-premises-voice) tramite Skype for Business locale o Cloud Connector Edition. Per garantire che l'utente TeamsOnly disponga di funzionalità PSTN, è necessario coordinare l'aggiornamento dell'utente a Teams con la migrazione dell'utente al routing diretto.

- [Un utente in Skype for Business locale con VoIP aziendale](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), che si sposterà online e manterrà la connettività PSTN locale.  Per eseguire la migrazione di questo utente a Teams, è necessario spostare l'account Skype for Business locale dell'utente nel cloud e coordinare lo spostamento con la migrazione dell'utente al routing diretto.

- [Un utente in Skype for Business locale con VoIP aziendale](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), che passa online e usa un piano per le chiamate Microsoft.  Per eseguire la migrazione di questo utente a Teams, è necessario spostare l'account Skype for Business locale dell'utente nel cloud. Devi coordinare lo spostamento con A) la porta del numero di telefono dell'utente a un Piano per chiamate Microsoft o B) assegnando un nuovo numero di abbonato dalle aree geografiche disponibili.

Questo articolo fornisce solo una panoramica generale. Per ulteriori informazioni, vedi [Sistema telefonico Routing diretto](direct-routing-landing-page.md) e [Piani per chiamate](calling-plan-landing-page.md).

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Da Skype for Business online con Piani per chiamate Microsoft

Questo scenario è lo scenario di aggiornamento più semplice che coinvolge la voce.

1. Verificare che agli utenti sia stata assegnata una licenza di Teams. Per impostazione predefinita, quando si assegna una licenza Microsoft 365 o Office 365, Teams è abilitato. A meno che la licenza Teams non sia stata disabilitata in precedenza, non dovrebbe essere necessario alcun intervento.

2. Se gli utenti hanno già un piano per chiamate Microsoft con un numero di telefono, l'unica modifica necessaria consiste nell'assegnare l'utente modalità TeamsOnly in TeamsUpgradePolicy. Prima di assegnare la modalità TeamsOnly, le chiamate PSTN in arrivo atterrano nel client Skype for Business dell'utente. Dopo l'aggiornamento alla modalità TeamsOnly, le chiamate PSTN in arrivo atterrano nel client Teams dell'utente.

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Da Skype for Business Online con la voce locale

In questo scenario l'utente è già in Skype for Business Online. La connettività PSTN dell'utente è locale, usando Skype for Business Server in modalità ibrida o Cloud Connector Edition. Per eseguire la migrazione di questi utenti alla modalità TeamsOnly con funzionalità PSTN, è necessario abilitare gli utenti per il routing diretto. Con l'instradamento diretto, i trunk PSTN si connettono direttamente al servizio di routing diretto tramite il session border controller (SBC) locale.

Di seguito sono elencati i passaggi di base.  I passaggi da 1 a 4 sono elencati nella sequenza suggerita, ma possono essere eseguiti in qualsiasi ordine. Questi passaggi devono essere completati prima del passaggio 5.

1. Se si impostano i criteri a livello di tenant su una delle modalità di Skype for Business, assicurarsi di assegnare esplicitamente la modalità Isole a tutti gli utenti delle isole esistenti, come descritto in precedenza.

2. Configurare il tenant per il routing diretto. Vedere [Riepilogo della configurazione per tenant del routing diretto](#summary-of-per-tenant-configuration-of-direct-routing).

3. Se lo si desidera, configurare vari criteri di Teams per questi utenti (ad esempio, TeamsMessagingPolicy, TeamsMeetingPolicy e così via). È possibile configurare le impostazioni in qualsiasi momento. Tuttavia, se si vuole assicurarsi che gli utenti abbiano la configurazione corretta quando vengono aggiornati, configurare questi criteri prima che l'utente venga aggiornato alla modalità TeamsOnly.

4. Preparare gli utenti selezionati per la migrazione vocale:
   - Se necessario, assegnare la licenza di Teams.  Supponendo che l'utente funzioni già in Skype for Business voce locale online, l'utente ha già Skype for Business Piano 2 e Telefono Microsoft Sistema. Lasciare entrambi i piani abilitati, inclusa la licenza Skype for Business Online Piano 2.
   - Assegnare il criterio OnlineVoiceRoutingPolicy desiderato.

5. Aggiornare l'utente: questi passaggi devono essere coordinati.

   - In Microsoft 365 o Office 365, aggiorna l'utente alla modalità TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - In SBC configurare il routing vocale per abilitare le chiamate in arrivo inviando le chiamate al routing diretto anziché al Mediation Server locale.

## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Da Skype for Business Server locale, con VoIP aziendale, a Routing diretto

In questo scenario, l'utente è ancora ospitato in Skype for Business locale. Anche la connettività PSTN dell'utente è locale. Per eseguire la migrazione di questo utente alla modalità TeamsOnly con funzionalità PSTN, è necessario abilitare l'utente per il routing diretto e quindi spostare l'utente nel cloud.

Di seguito sono elencati i passaggi di base. I passaggi da 1 a 5 sono elencati nella sequenza suggerita, ma possono essere eseguiti in qualsiasi ordine. È necessario completare i passaggi da 1 a 5 prima del passaggio 6.

1. Se il criterio a livello di tenant verrà impostato su una delle modalità Skype for Business, assicurarsi di assegnare esplicitamente la modalità Isole agli utenti delle Isole esistenti, come descritto in precedenza.

2. Se non è già stato fatto, [configurare l'organizzazione per Skype for Business ibrida](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Configurare il tenant per il routing diretto. Vedere [Riepilogo della configurazione per tenant del routing diretto](#summary-of-per-tenant-configuration-of-direct-routing).

4. Se lo si desidera, configurare vari criteri di Teams per questi utenti (ad esempio TeamsMessagingPolicy, TeamsMeetingPolicy). È possibile configurare i criteri in qualsiasi momento. Tuttavia, se si vuole assicurarsi che gli utenti abbiano la configurazione corretta al momento dell'aggiornamento, configurare questi criteri prima che l'utente venga aggiornato a TeamsOnly.

5. Assegnare le licenze Microsoft 365 o Office 365, se necessario.  L'utente deve avere sia Teams che Skype for Business Online Piano 2 e Sistema telefonico. Se il Skype for Business Online Piano 2 è disabilitato, riabilitarlo.

6. Aggiornare l'utente: questi passaggi devono essere coordinati.

   - Usando gli strumenti di Skype for Business locali, eseguire Move-CsUser con l'opzione -MoveToTeams. Se si usa una versione di Skype for Business Server che non supporta l'opzione -MoveToTeams, eseguire prima Move-CsUser quindi assegnare la modalità TeamsOnly in Una console di PowerShell o Teams Amministrazione remota tenant.

   - In SBC configurare il routing vocale per abilitare le chiamate in arrivo inviando le chiamate al routing diretto anziché al Mediation Server locale.

   - In Microsoft 365 o Office 365: assegnare il criterio OnlineVoiceRoutingPolicy pertinente per abilitare le chiamate in uscita.

## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Da Skype for Business Server locale, con VoIP aziendale, al piano per chiamate Microsoft

In questo scenario, l'utente è ancora ospitato in Skype for Business locale. Anche la connettività PSTN dell'utente è locale. Per eseguire la migrazione di questo utente alla modalità TeamsOnly con funzionalità PSTN, è necessario spostare l'utente nel cloud e trasferire il suo numero dal gestore precedente a un piano per le chiamate Microsoft oppure assegnare un nuovo numero all'utente.

Di seguito sono elencati i passaggi di base. I passaggi da 1 a 5 sono elencati nella sequenza suggerita, ma possono essere eseguiti in qualsiasi ordine. È necessario completare i passaggi da 1 a 5 prima del passaggio 6.

1. Se il criterio a livello di tenant verrà impostato su una delle modalità Skype for Business, assicurarsi di assegnare esplicitamente la modalità Isole agli utenti delle Isole esistenti, come descritto in precedenza.

2. Se non è già stato fatto, [configurare l'organizzazione per Skype for Business ibrida](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Se lo si desidera, configurare vari criteri di Teams per questi utenti (ad esempio, TeamsMessagingPolicy, TeamsMeetingPolicy e così via). È possibile configurare i criteri in qualsiasi momento. Tuttavia, se si vuole assicurarsi che gli utenti abbiano la configurazione corretta al momento dell'aggiornamento, configurare questi criteri prima che l'utente venga aggiornato a TeamsOnly.

4. Assegnare le licenze Microsoft 365 o Office 365, se necessario. L'utente deve avere sia Teams che Skype for Business Online Piano 2 e Sistema telefonico. Se il Skype for Business Online Piano 2 è disabilitato, riabilitarlo.

5. Ottenere i numeri di telefono per gli utenti. Per informazioni dettagliate, vedere [Gestire i numeri di telefono per l'organizzazione](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

   - Se riutilizzerai i numeri, invia una richiesta di trasferimento al tuo gestore telefonico.
   - In alternativa, puoi acquisire nuovi numeri direttamente da Microsoft.

6. Aggiorna l'utente e, se necessario, assegna LineUri. Usando gli strumenti di Skype for Business locali, eseguire Move-CsUser con l'opzione -MoveToTeams.

    - Se si stanno trasferindo numeri in Microsoft, è consigliabile coordinare l'intervallo di questa operazione in modo che si verifichi quando si verifica la porta.

    - Se usi nuovi numeri di Microsoft, dovrai modificare LineUri per l'utente dopo lo spostamento online dell'utente tramite Set-CsPhoneNumberAssignment.

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Riepilogo della configurazione per tenant del routing diretto

1. Verifica che il controller dei confini della sessione (SBC) sia supportato con il routing diretto esaminando [questo elenco](direct-routing-border-controllers.md). Assicurati anche di avere la versione corretta del firmware.

2. Associare il servizio SBC locale al servizio di routing diretto Teams. Per informazioni dettagliate, vedere [Associare SBC al servizio di routing diretto di Sistema telefonico](direct-routing-configure.md).

3. Questa configurazione è essenzialmente un mirror della configurazione locale. La configurazione online è costituita da:
   - OnlineVoiceRoutingPolicy (basato su VoiceRoutingPolicy locale se si esegue la migrazione di utenti da Skype for Business Online e in base a VoicePolicy se si esegue la migrazione di utenti da una distribuzione locale con VoIP aziendale).
   - Oggetti OnlinePSTNUsage (basati sull'utilizzo PSTN locale).
   - Oggetti OnlineVoiceRoute (basati su VoiceRoute locale).

Per altre informazioni, vedere [Configurare il routing diretto](direct-routing-configure.md).

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Gestire la proprietà EnterpriseVoiceEnabled durante la migrazione

Che si usi il routing diretto o un piano per le chiamate Microsoft, un utente deve avere EnterpriseVoiceEnabled=true in Azure AD affinché l'utente abbia la funzionalità PSTN.  EnterpriseVoiceEnabled ("abilitato per EV") è una proprietà (non un criterio) presente sia in una directory locale che nel cloud. Il valore nel cloud è ciò che conta per Teams.  La logica esatta per il modo in cui EV-enabled viene impostata su true dipende dallo scenario seguente:

- Se l'utente è abilitato per EV in Skype for Business Server locale e all'utente viene assegnata una licenza di Sistema telefonico prima di spostare l'utente nel cloud con Move-CsUser, all'utente online verrà eseguito il provisioning con EV-enabled=true.

- Se a un utente esistente di TeamsOnly o Skype for Business Online viene assegnata una licenza di Sistema telefonico, L'abilitazione per EV non è impostata su true per impostazione predefinita. Questo vale anche se un utente locale viene spostato nel cloud prima di assegnare la licenza Sistema telefonico. In entrambi i casi, l'amministratore deve specificare il cmdlet seguente:

  ```PowerShell
  Set-CsPhoneNumberAssignment -EnterpriseVoiceEnabled $True
  ```

## <a name="related-links"></a>Collegamenti correlati

[Pianificare la soluzione Teams voce](cloud-voice-landing-page.md)

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Uso del servizio MMS (Meeting Migration Service)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
