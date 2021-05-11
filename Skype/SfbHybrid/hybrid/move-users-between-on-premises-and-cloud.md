---
title: Spostare utenti tra ambiente locale e cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: "Riepilogo: in una distribuzione locale di Skype for Business Server abilitata per la distribuzione ibrida, è possibile spostare gli utenti tra l'ambiente locale e il cloud (da Microsoft Teams a Skype for Business Online prima del ritiro)."
ms.openlocfilehash: 8fce1799ba3e10f2e96b8beab0fbde7805c7c229
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305958"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Spostare utenti tra ambiente locale e cloud

In una distribuzione locale di Skype for Business Server abilitata per la distribuzione ibrida, è possibile spostare gli utenti tra l'ambiente locale e il cloud (da Microsoft Teams a Skype for Business Online prima del ritiro). A prescindere dal fatto che un utente si trovi in locale o nel cloud, la sua posizione è nota come abitazione Skype for Business dell'utente:

- Gli utenti ospitati in locale interagiscono con i server Skype for Business locali.
- Gli utenti disponibili online possono interagire con il servizio Skype for Business Online.

*Teams utenti hanno intrinsecamente una casa Skype for Business, che usino Skype for Business o meno.* Se si dispone di utenti Skype for Business locali che usano anche Teams (affiancati), tali utenti sono ospitati in locale. Teams gli utenti con Skype for Business locale non hanno la possibilità di interagire con gli utenti di Skype for Business dal client Teams, né possono comunicare da Teams con gli utenti di un'organizzazione federata. Tale funzionalità è completamente disponibile solo dopo che l'utente è stato spostato da Skype for Business locale a online e reso TeamsOnly. Quando si sposta un utente in online, è possibile consentirgli di usare Skype for Business Online (e, facoltativamente, Teams) oppure è possibile renderlo Solo Teams. È consigliabile spostare gli utenti in modalità Solo Teams, in modo da garantire che il routing di tutte le chat e le chiamate in arrivo si sposti nel client Teams messaggi. Per ulteriori dettagli, vedere [Teams coesistenza](/microsoftteams/coexistence-chat-calls-presence) con Skype for Business e Guida alla migrazione e all'interoperabilità per le organizzazioni che utilizzano [Teams insieme](/microsoftteams/migration-interop-guidance-for-teams-with-skype)a Skype for Business .

## <a name="prerequisites"></a>Prerequisiti

Prerequisiti per spostare un utente nel cloud (se si Teams solo modalità o Skype for Business Online prima del ritiro):

- L'organizzazione deve avere Azure AD Connessione configurato correttamente e sincronizzare tutti gli attributi rilevanti per l'utente, come descritto in [Configure Azure AD Connessione](configure-azure-ad-connect.md).
- Skype for Business ibrido deve essere configurato, come descritto in [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).
- All'utente deve essere assegnata una licenza per Teams e Skype for Business Online (Piano 2). Anche dopo il ritiro di Skype for Business Online, la licenza Skype for Business online è ancora necessaria.  Inoltre:
    - Se l'utente è abilitato per le conferenze telefoniche con accesso esterno in locale, per impostazione predefinita l'utente deve disporre anche di una licenza di audioconferenza assegnata in Teams prima di spostare l'utente online. Dopo la migrazione al cloud l'utente dovrà eseguire il provisioning per le audioconferenze nel cloud. Se per qualche motivo si desidera spostare un utente nel cloud, ma non utilizzare la funzionalità di audioconferenza, è possibile ignorare questo controllo specificando il `BypassAudioConferencingCheck` parametro in `Move-CsUser` .
    - Se l'utente è abilitato per VoIP aziendale in locale, per impostazione predefinita l'utente deve disporre di una licenza Sistema telefonico assegnata in Teams prima di spostare l'utente online. Dopo la migrazione al cloud l'utente dovrà eseguire il provisioning per Sistema telefonico nel cloud. Se per qualche motivo si desidera spostare un utente nel cloud ma non utilizzare la funzionalità Sistema telefonico, è possibile ignorare questo controllo specificando il `BypassEnterpriseVoiceCheck` parametro in `Move-CsUser` .


## <a name="moving-users"></a>Spostamento degli utenti

Se un utente viene spostato da locale al cloud:

- Teams gli utenti diventano abilitati per l'interoperabilità con Skype for Business utenti e, se sono TeamsOnly, possono anche eseguire la federazione con altre organizzazioni.
- L'utente inizia a usare i servizi di Skype for Business Online nel cloud per qualsiasi funzionalità di Skype for Business.
- I contatti locali vengono spostati nel cloud (Teams o Skype for Business Online).
- Le riunioni esistenti organizzate e pianificate in futuro vengono migrate online: se gli utenti vengono spostati direttamente in TeamsOnly (vedere di seguito), le riunioni vengono convertite Teams riunioni, altrimenti le riunioni rimangono Skype for Business ma verranno migrate in modo che siano ospitate online anziché locali.  La migrazione delle riunioni avviene in modo asincrono e inizia circa 90 minuti dopo lo spostamento dell'utente.  Per determinare lo stato della migrazione di una riunione, è possibile usare [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Tenere presente che qualsiasi contenuto caricato prima della riunione non viene spostato.

Per spostare gli utenti tra l'ambiente locale e il cloud (da Teams a Skype for Business Online), utilizzare il cmdlet Move-CsUser o il Pannello di controllo di amministrazione di Skype for Business, entrambi strumenti locali. Questi strumenti supportano tre diversi percorsi di spostamento:

- [Da Skype for Business Server (locale)](move-users-from-on-premises-to-teams.md) direttamente a Teams Only (che li sposta anche in Skype for Business Online).  L'opzione per passare direttamente da locale a  Teams Only è attualmente disponibile in Skype for Business Server 2019 e nell'aggiornamento cumulativo 8 per Skype for Business Server 2015. Le organizzazioni che usano versioni precedenti di Skype for Business Server possono trasferire gli utenti a Solo Teams spostandoli prima in Skype for Business Online e quindi applicando la modalità di Solo Teams a questi utenti una volta che sono online. 

> [!NOTE] 
> Non sarà più necessario specificare l'opzione -MoveToTeams in Move-CsUser per spostare gli utenti direttamente da locale a TeamsOnly. Attualmente, se questa opzione non è specificata, gli utenti passano dall'abitazione Skype for Business Server locale a Skype for Business Online e la relativa modalità rimane invariata. Dopo il ritiro, quando si sposta un utente dall'ambiente locale al cloud con Move-CsUser, agli utenti verrà automaticamente assegnata la modalità TeamsOnly e le riunioni da locale verranno convertite automaticamente in riunioni Teams, come se fosse stato specificato l'opzione -MoveToTeams, indipendentemente dal fatto che l'opzione sia effettivamente specificata. Si prevede di rilasciare questa funzionalità prima del ritiro effettivo del 31 luglio 2021.

- [Da Skype for Business Server (locale) a Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md). Questa opzione non sarà più disponibile.
- [Da online (Teams solo o meno), a locale](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Credenziali amministrative necessarie

Per spostare gli utenti tra l'ambiente locale e il cloud, è necessario utilizzare un account con privilegi sufficienti sia nell'ambiente Skype for Business Server locale che nell'organizzazione Teams. È possibile utilizzare un solo account con tutti i privilegi necessari oppure due account, nel qual caso si accederà agli strumenti locali utilizzando le credenziali locali e quindi in tali strumenti verranno fornite credenziali aggiuntive per un account amministrativo di Teams.  

- Nell'ambiente locale l'utente che esegue lo spostamento deve avere il ruolo CSServerAdminstrator in Skype for Business Server.
- In Teams, l'utente che esegue lo spostamento deve soddisfare uno dei criteri seguenti:
  - L'utente è membro del ruolo Amministratore globale.
  - L'utente è membro dei ruoli amministratore Teams utente e Amministratore utente.
  - L'utente è membro dei ruoli amministratore Skype for Business utente e Amministratore utente.  

    > [!Important]
    > - Se si utilizza il Pannello di controllo di amministrazione di Skype for Business, verrà richiesto di fornire le credenziali per un account Microsoft 365 con i ruoli appropriati, come indicato in precedenza. È necessario specificare un account che termina con .onmicrosoft.com. Se non è possibile, utilizzare il cmdlet Move-CsUser.
    >- Se si usa Move-CsUser in PowerShell, è possibile utilizzare un account che termina con .onmicrosoft.com oppure qualsiasi account locale sincronizzato in Azure AD, purché sia stato specificato anche il parametro HostedMigrationOverrideUrl nel cmdlet. Il valore dell'URL di sostituzione della migrazione ospitata è una variante dell'URL seguente: https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Nell'URL precedente sostituire XX con due o tre caratteri, determinati come segue:
    >   - In una Teams PowerShell eseguire il cmdlet seguente:<br>`Get-CsTenant|ft identity`
    >   - Il valore risultante avrà il formato seguente:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >   - Il codice a due o tre cifre è il codice XX contenuto nella sezione DC=lyncXX001. Se si tratta di un codice a due caratteri, sarà una cifra seguita da un numero (ad esempio 0a). Se si tratta di un codice di tre caratteri, saranno due lettere seguite da una cifra (ad esempio jp1). In tutti i casi, vedrai 001 subito dopo il codice XX.


## <a name="voice-configuration-requirements"></a>Requisiti di configurazione vocale

Se gli utenti sono configurati per VoIP aziendale in locale, sarà necessario coordinare l'aggiornamento della configurazione vocale quando li si sposta in linea oppure, in alternativa, è possibile eseguirne la migrazione senza funzionalità di telefonia. Le opzioni disponibili dipendono dal fatto che l'utente utilizzi il Teams o Skype for Business client quando è online:

- È possibile aggiornare il provider di telefonia di un utente per l'utilizzo di [un piano di chiamata Microsoft.](/microsoftteams/calling-plans-for-office-365) Si tratta di un'opzione che consente agli utenti di Teams o Skype for Business client.
- È possibile continuare a utilizzare il provider PSTN locale:
  - Gli utenti vocali che utilizzeranno Teams devono essere configurati per [il routing diretto.](/microsoftteams/direct-routing-plan) Il routing diretto è disponibile solo dopo lo spostamento dell'utente da locale a online.
  - Gli utenti vocali che utilizzeranno il client Skype for Business dopo essere stati spostati online devono essere configurati per la Skype for Business Hybrid Voice.

Per ulteriori informazioni sulle opzioni di telefonia negli ambienti ibridi, oltre a una matrice di supporto, vedere Account utente in un ambiente ibrido [con connettività PSTN.](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)

## <a name="other-considerations"></a>Altre considerazioni

I criteri (come quelli relativi al controllo del comportamento della messaggistica, delle riunioni e delle chiamate) negli ambienti locali e online sono indipendenti. È consigliabile configurare i criteri nell'ambiente e assegnarli all'utente prima di spostare l'utente dall'ambiente locale al cloud, in modo che abbia la configurazione corretta non appena viene eseguita la migrazione in linea.

## <a name="see-also"></a>Vedere anche

[Spostare utenti da ambiente locale a Teams](move-users-from-on-premises-to-teams.md)

[Spostare utenti da ambiente locale a Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Configurazione del servizio MMS (Meeting Migration Service)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Pianificare Instradamento diretto](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
