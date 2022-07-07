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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: "Riepilogo: in una distribuzione locale di Skype for Business Server abilitata per l'ambiente ibrido, è possibile spostare gli utenti tra l'ambiente locale e il cloud."
ms.openlocfilehash: 93aea5e294bbaf8d6988e5bfdeaafb1340345bdf
ms.sourcegitcommit: d87991ed2d3e4d70edb048378763a17ff689b710
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2022
ms.locfileid: "66682655"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Spostare utenti tra ambiente locale e cloud

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In una distribuzione locale di Skype for Business Server, anche gli utenti di Skype for Business possono usare Teams, ma non tutte le funzionalità di Teams sono disponibili per tali utenti purché siano configurati per l'uso della distribuzione Skype for Business Server locale. Si dice che questi utenti siano "ospitati" in locale e alcune funzionalità di Teams non sono disponibili mentre questi utenti sono ospitati in locale, ad esempio:
- Le chiamate federate e le chat tramite il client Teams dell'utente con utenti di altre organizzazioni non sono disponibili
- Comunicazione di interoperabilità tramite il client Teams dell'utente con altri utenti dell'organizzazione che usano Skype for Business client.
- Funzionalità di chiamata PSTN (se all'utente viene assegnata una licenza di sistema telefonico).

Per ottenere funzionalità complete di Teams, questi utenti devono essere spostati da Skype for Business locale al cloud, a quel punto l'utente diventa TeamsOnly. L'atto di spostare un utente dall'ambiente locale al cloud imposterà la modalità di coesistenza dell'utente su TeamsOnly. Dopo lo spostamento degli utenti nel cloud e in TeamsOnly, tutte le chat e le chiamate in arrivo vengono spostate nel client di Teams. Per altre informazioni, vedere [Coesistenza di Teams con Skype for Business](/microsoftteams/coexistence-chat-calls-presence) e [Guida alla migrazione e all'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

Per spostare gli utenti dalla distribuzione Skype for Business Server locale al cloud è necessaria la [configurazione di Skype for Business ibrido](/skypeforbusiness/hybrid/plan-hybrid-connectivity).  Dopo aver abilitato la distribuzione per l'ambiente ibrido, è possibile spostare gli utenti dall'ambiente locale al cloud per renderli TeamsOnly come descritto di seguito. Se necessario, è anche possibile spostare di nuovo gli utenti di TeamsOnly nella distribuzione locale di Skype for Bsuiness. 



## <a name="prerequisites"></a>Prerequisiti

Prerequisiti per spostare un utente in modalità TeamsOnly:

- L'organizzazione deve avere Azure AD Connect configurato correttamente e sincronizzare tutti gli attributi pertinenti per l'utente, come descritto in [Configurare Azure AD Connect](configure-azure-ad-connect.md).
- Skype for Business ibrido deve essere configurato, come descritto in [Configurare Skype for Business ibrido](configure-federation-with-skype-for-business-online.md).
- All'utente deve essere assegnata una licenza per Teams e Skype for Business Online (piano 2). Anche dopo il ritiro di Skype for Business Online, è ancora necessaria la licenza Skype for Business Online.  Inoltre:
    - Se l'utente è abilitato per le conferenze telefoniche con accesso esterno in locale, l'utente deve avere anche una licenza di audioconferenza assegnata in Teams prima di spostare l'utente online. Dopo la migrazione al cloud l'utente dovrà eseguire il provisioning per le audioconferenze nel cloud. 
    - Se l'utente è abilitato per VoIP aziendale in locale, l'utente deve avere una licenza del sistema telefonico assegnata in Teams prima di spostare l'utente online. Dopo la migrazione al cloud, verrà effettuato il provisioning dell'utente per Sistema telefonico nel cloud. 
  
A partire dal 31 luglio 2022, per spostare gli utenti tra una distribuzione locale e il cloud, è necessario usare la versione minima seguente di Skype for Business Server o Lync Server:

</br>
</br>

|Prodotto locale|Versione minima richiesta|Compilazione minima richiesta|
|---|---|---|
|Skype for Business Server 2019| CU6 |7.0.2046.385|
|Skype for Business Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| CU10 con hotfix 7|5.0.8308.1182|
||||

</br>
</br>

## <a name="moving-users"></a>Spostamento degli utenti

Se un utente viene spostato da locale al cloud:

- Gli utenti di Teams diventano abilitati per l'interoperabilità con gli utenti Skype for Business e, se si tratta di TeamsOnly, possono anche eseguire la federazione con altre organizzazioni.
- I contatti locali vengono spostati in Teams.
- Le riunioni esistenti organizzate che verranno pianificate in futuro vengono convertite in riunioni di Teams. La migrazione delle riunioni avviene in modo asincrono e inizia circa 90 minuti dopo lo spostamento dell'utente.  Per determinare lo stato della migrazione di una riunione, è possibile usare [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Qualsiasi contenuto caricato prima della riunione non viene spostato.
- Gli utenti a cui viene assegnato sistema telefonico possono accedere alle funzionalità PSTN dopo aver configurato correttamente.
 
Per spostare gli utenti in Teams, usare il cmdlet Move-CsUser o il Skype for Business Amministrazione Pannello di controllo, entrambi strumenti locali. Questi strumenti supportano i percorsi di spostamento seguenti:

- [Da Skype for Business Server (locale) a Solo Teams](move-users-from-on-premises-to-teams.md).
- [Da online (solo Teams o meno) a locale](move-users-from-the-cloud-to-on-premises.md).


> [!NOTE] 
>  Il comportamento per passare direttamente dall'ambiente locale a Solo Teams è ora automatico, indipendentemente dalla versione di Skype for Business Server o Lync Server usata. Non è più necessario specificare l'opzione -MoveToTeams in Move-CsUser per spostare gli utenti direttamente dall'ambiente locale a TeamsOnly. In precedenza, se questa opzione non veniva specificata, gli utenti passavano dalla home page in Skype for Business Server locale a Skype for Business Online e la modalità rimaneva invariata. Ora, quando si sposta un utente dall'ambiente locale al cloud con Move-CsUser, agli utenti viene assegnata automaticamente la modalità TeamsOnly e le loro riunioni dall'ambiente locale vengono convertite automaticamente in riunioni di Teams, proprio come se fosse stato specificato il `-MoveToTeams` commutatore, indipendentemente dal fatto che l'opzione sia stata effettivamente specificata. 


## <a name="required-administrative-credentials"></a>Credenziali amministrative necessarie

Per spostare gli utenti tra l'ambiente locale e il cloud, è necessario usare un account con privilegi sufficienti sia nell'ambiente Skype for Business Server locale che nell'organizzazione Teams. È possibile usare un account con tutti i privilegi necessari oppure due account. Se si usano due account, si accede agli strumenti locali usando le credenziali locali e quindi in tali strumenti si forniscono credenziali aggiuntive per un account amministrativo di Teams.  

- Nell'ambiente locale, l'utente che esegue lo spostamento deve avere i ruoli CSServerAdministrator, CsUserAdministrator e RTCUniversalUserAdmins in Skype for Business Server.
- In Teams l'utente che esegue lo spostamento deve essere membro di almeno uno dei ruoli seguenti:
  - Ruolo amministratore globale
  - Ruolo di amministratore di Teams
  - Skype for Business ruolo Amministratore.  

    > [!Important]
    > - Se si usa il Skype for Business Amministrazione Pannello di controllo, verrà richiesto di fornire le credenziali per un account Microsoft 365 con i ruoli appropriati, come indicato in precedenza. È necessario fornire un account che termina con onmicrosoft.com. Se ciò non è possibile, usare il cmdlet Move-CsUser.
    >- Se si usa Move-CsUser in PowerShell, è possibile usare un account che termina con onmicrosoft.com oppure qualsiasi account locale sincronizzato in Azure AD, a condizione di specificare anche il parametro HostedMigrationOverrideUrl nel cmdlet. Il valore dell'URL di override della migrazione ospitata è una variante dell'URL seguente: https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Nell'URL precedente sostituire XX con due o tre caratteri, determinati come segue:
    >   - In una sessione di Teams PowerShell eseguire il cmdlet seguente:<br>`Get-CsTenant | ft ServiceInstance`
    >   - Il valore risultante sarà nel formato seguente:<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - Il codice a due o tre caratteri è il codice XX contenuto nella sezione AAAA-XX-ZZ. Se si tratta di un codice a due caratteri, sarà una cifra seguita da un numero (ad esempio 4A). Se si tratta di un codice di tre caratteri, saranno due lettere seguite da una cifra (ad esempio JP1). Un esempio è NOAM-4A-S7.


## <a name="voice-configuration-requirements"></a>Requisiti di configurazione della voce

Se gli utenti sono configurati per la voce aziendale in locale, è necessario coordinare l'aggiornamento della configurazione vocale quando si passa alla modalità online. In alternativa, è possibile eseguirne la migrazione senza funzionalità di telefonia. 
- È possibile aggiornare il provider di telefonia di un utente per usare un [piano per chiamate Microsoft](/microsoftteams/calling-plans-for-office-365). Si tratta di un'opzione che indica se gli utenti useranno Teams o Skype for Business client.
- È possibile continuare a usare il provider PSTN locale:
  - Gli utenti vocali che useranno Teams devono essere configurati per [l'instradamento diretto](/microsoftteams/direct-routing-plan). Il routing diretto è disponibile solo dopo lo spostamento dell'utente dall'ambiente locale a quello online.

Per altre informazioni sulle opzioni di telefonia negli ambienti ibridi, inclusa una matrice di supporto, vedere [Account utente in un ambiente ibrido con connettività PSTN](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Altre considerazioni

I criteri (come quelli relativi al controllo del comportamento della messaggistica, delle riunioni e delle chiamate) negli ambienti locali e online sono indipendenti. È consigliabile configurare eventuali criteri nell'ambiente e assegnarli all'utente prima di spostare l'utente dall'ambiente locale al cloud, in modo che dispongano della configurazione corretta non appena viene eseguita la migrazione online.

## <a name="see-also"></a>Vedere anche

[Spostare utenti da ambiente locale a Teams](move-users-from-on-premises-to-teams.md)

[Configurazione del servizio MMS (Meeting Migration Service)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Pianificare Instradamento diretto](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
