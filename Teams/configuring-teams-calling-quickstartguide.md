---
title: Guida introduttiva - Configurazione dei piani per chiamate
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guida introduttiva per la configurazione dei piani di chiamata in Microsoft Teams per consentire l'avvio di un set di utenti.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6420fdff102533c44bdd3ccb2ab503a646c354b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101182"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guida introduttiva: Configurazione dei piani di chiamata su Microsoft Teams
==============================================================

Questa guida ti aiuterà a far entrare in funzione un set di utenti in modo che possano esplorare i Piani per le chiamate in Teams.

Leggi l'annuncio del 12 dicembre 2017 dei piani per chiamate [in Teams: Intelligent Communications](https://aka.ms/ipyqus) fa il prossimo passo con le chiamate in Teams

> [!NOTE]
> In parallelo a questa guida introduttiva, è [](calling-plan-landing-page.md) consigliabile leggere Sistema telefonico con piani per chiamate e [FastTrack](https://aka.ms/cloudvoice) per pianificare e guidare un'implementazione corretta.

Con l'aggiunta di Piani per le chiamate, una funzionalità di Microsoft 365 e Office 365 basata su Skype for Business, è ora possibile usare Teams per effettuare e ricevere chiamate telefoniche da o verso linee di terra e telefoni cellulari tramite la rete PSTN (Public Switched Telephone Network).

![Schermata che mostra la pagina Contatti in Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Prerequisiti per l'abilitazione **della scheda** Chiamate in Teams
Per abilitare la **scheda** Chiamate in Teams, gli utenti devono avere le chiamate 1:1 abilitate in Teams e usare un client teams che supporta le chiamate 1:1 Teams. Per informazioni su come gestire le chiamate 1:1 in Teams, vedere [Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) Per informazioni sui client che supportano le chiamate, leggere [Limiti e specifiche per Microsoft Teams.](./limits-specifications-teams.md)

> [!NOTE]
> Attualmente, la segreteria telefonica non sarà disponibile nella scheda Chiamate a meno che l'utente non sia abilitato per le chiamate PSTN. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Prerequisiti per l'abilitazione della **tastiera del** telefono in Teams
Per abilitare la **scheda Tastiera** del telefono in Teams e consentire agli utenti di effettuare e ricevere chiamate PSTN, è necessario effettuare il provisioning degli utenti per Sistema telefonico e Piani di chiamata. Per informazioni su come configurare i piani per chiamate, vedere [Configurare i piani per chiamate.](./set-up-calling-plans.md)
Inoltre, per gli utenti di Teams, è necessario assicurarsi che "Consenti chiamate private" sia abilitato nei criteri di chiamata di Teams. Per [altre informazioni, vedere](./manage-teams-skypeforbusiness-admin-center.md) Gestire Teams durante la transizione alla nuova interfaccia di amministrazione di Microsoft Teams.
> [!NOTE]
> È anche possibile usare Il routing diretto per consentire agli utenti di effettuare e ricevere chiamate PSTN. Per informazioni su come configurare il routing diretto, vedere [Configurare il routing diretto.](./direct-routing-configure.md)

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Uso di TeamsUpgradePolicy per controllare dove atterrano le chiamate
Per controllare se le chiamate in arrivo (e le chat) atterrano in Teams o Skype for Business, gli amministratori usano TeamsUpgradePolicy, usando l'interfaccia di amministrazione di [Microsoft Teams](https://aka.ms/teamsadmincenter) o una sessione di Windows PowerShell remota con i cmdlet di Skype [for Business.](/powershell/module/skype)


La configurazione predefinita di TeamsUpgradePolicy è la modalità Isole, progettata per garantire che i flussi di lavoro aziendali esistenti non siano interrotti durante una distribuzione di Teams. Per impostazione predefinita, le chiamate VoIP, PSTN e federate agli utenti continueranno a essere instradate a Skype for Business finché non si aggiorna il criterio per abilitare le chiamate in ingresso a Teams.  Quando i destinatari sono in modalità isole:

 - Le chiamate VOIP in arrivo originate in Skype for Business vengono sempre effettuate nel client Skype for Business del destinatario.
 - Le chiamate VOIP in arrivo originate in Teams vengono effettuate in Teams, se il mittente e il destinatario sono *nello stesso tenant.*
 - Le chiamate VOIP federate in arrivo (indipendentemente dal client di origine) e le chiamate PSTN vengono sempre effettuate nel client Skype for Business del destinatario.
 
Per assicurarsi che le chiamate VOIP e PSTN in arrivo siano sempre presenti nel client Teams di un utente, aggiornare la modalità di coesistenza dell'utente in TeamsOnly, ovvero assegnarle l'istanza "UpgradeToTeams" di TeamsUpgradePolicy.  Per altre informazioni sulle modalità di coesistenza e TeamsUpgradePolicy, vedere Indicazioni sulla migrazione e [l'interoperabilità](./migration-interop-guidance-for-teams-with-skype.md) per le organizzazioni che usano Teams insieme a Skype for Business

**NOTE**
 - I telefoni IP Skype for Business riceveranno chiamate, anche se l'utente è in modalità TeamsOnly.  
 - Gli utenti a cui è stato eseguito il provisioning con licenze Sistema telefonico e Piani di chiamata per l'uso con Skype for Business Online (ad esempio, a cui è stato assegnato un valore di OnlineVoiceRoutingPolicy), avranno la scheda Chiamate abilitata in Teams e potranno effettuare chiamate PSTN in uscita da Teams senza che gli amministratori devono eseguire alcuna azione amministrativa.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Come configurare gli utenti per la ricezione di tutte le chiamate VOIP e PSTN in arrivo in Teams
Per assicurarsi che gli utenti ricevano tutte le chiamate VOIP e PSTN in arrivo in Teams, impostare la modalità di coesistenza dell'utente su TeamsOnly nell'interfaccia di amministrazione di Microsoft Teams oppure usare la sessione di Windows PowerShell remota di Skype for Business per aggiornare TeamsUpgradePolicy nel modo seguente:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Vedere anche
[Configurare i piani per chiamate](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guida alla migrazione e all'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)

[Phone System e Piani di Chiamata](calling-plan-landing-page.md)

[Informazioni di riferimento sul cmdlet di PowerShell per Skype for Business](/powershell/module/skype)