---
title: Guida introduttiva-configurazione di piani per le chiamate
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guida introduttiva per la configurazione dei piani per le chiamate in Microsoft teams in modo da poter ottenere un set di utenti in funzione.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eed9ec99445c2f632f1443343b7076aadfbb70a8
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739044"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guida introduttiva: configurazione di piani di chiamata in Microsoft Teams
==============================================================

Questa guida consentirà di velocizzare l'uso di un gruppo di utenti in modo che possano esplorare i piani di chiamata in teams.

Leggere il 12 dicembre 2017, annuncio dei piani di chiamata in teams: [le comunicazioni intelligenti richiedono il passaggio successivo con le chiamate in teams](https://aka.ms/ipyqus)

> [!NOTE]
> È consigliabile, in parallelo con questa Guida introduttiva, leggere il [sistema telefonico con i piani](calling-plan-landing-page.md) per le chiamate e [FastTrack](https://aka.ms/cloudvoice) per pianificare e guidare un implementazione di successo.

Con l'aggiunta di piani di chiamata: una caratteristica Microsoft 365 e Office 365 alimentata da Skype for business, ora è possibile usare team per effettuare e ricevere telefonate da o verso linee terrestri e telefoni cellulari tramite la rete PSTN (Public Switched Telephone Network).

![Screenshot che mostra la pagina dei contatti in teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Prerequisiti per l'abilitazione della scheda **chiamate** in teams
Per abilitare la scheda **chiamate** in teams gli utenti devono avere la chiamata di 1:1 abilitata in teams e l'uso di un client teams che supporta 1:1 Teams Calling. Per informazioni su come gestire la chiamata di 1:1 in teams, leggere [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). Per informazioni sui clienti che supportano la chiamata, leggere i [limiti e le specifiche per Microsoft teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).

> [!NOTE]
> Attualmente, la segreteria telefonica non sarà disponibile nella scheda chiamate, a meno che l'utente non sia abilitato per le chiamate PSTN. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Prerequisiti per l'abilitazione della **tastiera del telefono** in teams
Per abilitare la scheda **tastiera** del telefono in teams e consentire agli utenti di effettuare e ricevere chiamate PSTN, è necessario eseguire il provisioning degli utenti per il sistema telefonico e per i piani di chiamata. Per informazioni su come configurare i piani per le chiamate, vedere [configurare i piani](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)per le chiamate.
Inoltre, per gli utenti di teams only, devi assicurarti che "Consenti chiamate private" sia abilitato nei criteri di chiamata dei team. Per altre informazioni, vedere [gestire i team durante la transizione al nuovo centro di amministrazione di Microsoft teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) .
> [!NOTE]
> È anche possibile usare il routing diretto per consentire agli utenti di effettuare e ricevere chiamate PSTN. Per informazioni su come configurare il routing diretto, vedere [configurare il routing diretto](https://docs.microsoft.com/microsoftteams/direct-routing-configure).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Uso di TeamsUpgradePolicy per controllare la posizione delle chiamate
Per controllare se le chiamate in arrivo (e le chat) atterrano in teams o in Skype for business, gli amministratori usano TeamsUpgradePolicy, usando l'interfaccia di [amministrazione di Microsoft teams](https://aka.ms/teamsadmincenter) o usando una sessione remota di Windows PowerShell con i cmdlet di [Skype for business](https://docs.microsoft.com/powershell/module/skype) .


La configurazione predefinita di TeamsUpgradePolicy è la modalità Islands, progettata per garantire che i flussi di lavoro aziendali esistenti non vengano interrotti durante la distribuzione di team. Per impostazione predefinita, le chiamate VoIP, PSTN e federate agli utenti continueranno a essere instradate a Skype for business finché non si aggiorna il criterio per abilitare la chiamata in ingresso ai team.  Quando i destinatari sono in modalità isole:

 - Le chiamate VOIP in arrivo che sono state originate in Skype for business sempre atterrano nel client Skype for business del destinatario.
 - Le chiamate VOIP in arrivo originate in teams atterrano in teams, *se il mittente e il destinatario si trovano nello stesso tenant*.
 - VOIP federativo in arrivo (indipendentemente dal cliente che ha origine) e chiamate PSTN sempre atterrano nel client Skype for business del destinatario.
 
Per fare in modo che le chiamate VOIP e PSTN in arrivo siano sempre presenti nel client teams di un utente, aggiornare la modalità di coesistenza dell'utente in modo che sia TeamsOnly, assegnando loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy.  Per altre informazioni sulle modalità di coesistenza e TeamsUpgradePolicy, Vedi [linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

**Note**
 - I telefoni IP di Skype for Business riceveranno le chiamate, anche se l'utente è in modalità TeamsOnly.  
 - Gli utenti che hanno effettuato il provisioning con il sistema telefonico e le licenze per i piani di chiamata per l'uso con Skype for business online (ad esempio, hanno assegnato un valore di OnlineVoiceRoutingPolicy), la scheda chiamate è abilitata in teams e può inserire chiamate PSTN in uscita da team senza che gli amministratori debbano eseguire alcuna azione amministrativa.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Come configurare gli utenti per ricevere tutte le chiamate VOIP e PSTN in arrivo in teams
Per assicurarsi che gli utenti ricevano tutte le chiamate VOIP e PSTN in arrivo in teams, impostare la modalità di coesistenza dell'utente su TeamsOnly nell'interfaccia di amministrazione di Microsoft teams oppure usare la sessione remota di Windows PowerShell di Skype for business per aggiornare TeamsUpgradePolicy come segue:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Vedere anche
[Configurare i piani per chiamate](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Sistema telefonico con piani di chiamata](calling-plan-landing-page.md)

[Informazioni di riferimento sui cmdlet di PowerShell per Skype for business](https://docs.microsoft.com/powershell/module/skype)

