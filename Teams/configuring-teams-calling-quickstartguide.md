---
title: Guida introduttiva - Configurazione dei piani per chiamate
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guida introduttiva per la configurazione dei piani di chiamata in Microsoft Teams per consentire l'avvio e l'esecuzione di un set di utenti.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aeb9fae94d186e841cdacbd05879ab2891b9ba2a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745692"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guida introduttiva: Configurazione dei piani di chiamata su Microsoft Teams

Questa guida ti aiuterà a far entrare in funzione un set di utenti in modo che possano esplorare i Piani per chiamate in Teams.

Leggi l'annuncio del 12 dicembre 2017 dei Piani per chiamate in Teams: Intelligent Communications fa il prossimo passo con [le chiamate in Teams](https://aka.ms/ipyqus)

> [!NOTE]
> In parallelo a questa guida introduttiva, è [](calling-plan-landing-page.md) consigliabile leggere Sistema telefonico [](https://aka.ms/cloudvoice) piani per chiamate e FastTrack per pianificare e guidare un'implementazione corretta.

Con l'aggiunta di Piani per le chiamate, una funzionalità di Microsoft 365 e Office 365 basata su Skype for Business, ora è possibile usare Teams per effettuare e ricevere chiamate telefoniche da o verso le linee di terra e i telefoni cellulari tramite la rete PSTN (Public Switched Telephone Network).

![Schermata che mostra la pagina Contatti in Teams.](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Prerequisiti per l'abilitazione **della scheda** Chiamate in Teams
Per abilitare  la scheda Chiamate in Teams gli utenti devono avere le chiamate 1:1 abilitate in Teams e usare un client Teams che supporta le chiamate 1:1 Teams telefonia. Per informazioni su come gestire le chiamate 1:1 in Teams, vedere [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy). Per informazioni sui client che supportano le chiamate, leggere [Limiti e specifiche per](./limits-specifications-teams.md)Microsoft Teams.

> [!NOTE]
> Attualmente, la segreteria telefonica non sarà disponibile nella scheda Chiamate a meno che l'utente non sia abilitato per le chiamate PSTN. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Prerequisiti per l'abilitazione **della tastiera del** telefono in Teams
Per abilitare la **scheda** Tastiera del telefono Teams e consentire agli utenti di effettuare e ricevere chiamate PSTN, è necessario effettuare il provisioning degli utenti per i piani Sistema telefonico chiamate. Per informazioni su come configurare i piani per chiamate, vedere [Configurare i piani per chiamate.](./set-up-calling-plans.md)
Inoltre, per Teams solo gli utenti, è necessario assicurarsi che "Consenti chiamate private" sia abilitato nel criterio Teams chiamate. Per altre Teams, vedere Gestire i Teams durante la transizione alla nuova [interfaccia Microsoft Teams di amministrazione.](./manage-teams-skypeforbusiness-admin-center.md)
> [!NOTE]
> È anche possibile usare Il routing diretto per consentire agli utenti di effettuare e ricevere chiamate PSTN. Per informazioni su come configurare il routing diretto, vedere [Configurare il routing diretto.](./direct-routing-configure.md)

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Uso di TeamsUpgradePolicy per controllare dove atterrano le chiamate
Per controllare se le chiamate in arrivo (e le chat) atterrano Teams o Skype for Business, gli amministratori usano TeamsUpgradePolicy, usando l'interfaccia di amministrazione di [Microsoft Teams](https://aka.ms/teamsadmincenter) o una sessione di Windows PowerShell remota con il [Skype for Business ](/powershell/module/skype)cmdlet.


La configurazione predefinita di TeamsUpgradePolicy è la modalità Isole, progettata per garantire che i flussi di lavoro aziendali esistenti non siano interrotti durante Teams distribuzione. Per impostazione predefinita, le chiamate VoIP, PSTN e federate agli utenti continueranno a essere instradate a Skype for Business finché non si aggiorna il criterio per abilitare le chiamate in ingresso a Teams.  Quando i destinatari sono in modalità isole:

 - Le chiamate VOIP in arrivo originate Skype for Business sempre nel client Skype for Business destinatario.
 - Le chiamate VOIP in arrivo originate in Teams atterrano in Teams, se il mittente e il destinatario sono *nello stesso tenant.*
 - Le chiamate VOIP federate in arrivo (indipendentemente dal client di origine) e le chiamate PSTN vengono sempre effettuate nel client Skype for Business destinatario.
 
Per assicurarsi che le chiamate VOIP e PSTN in arrivo siano sempre presenti nel client Teams di un utente, aggiornare la modalità di coesistenza dell'utente in teamsOnly, ovvero assegnare loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy.  Per altre informazioni sulle modalità di coesistenza e TeamsUpgradePolicy, vedere Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams [con](./migration-interop-guidance-for-teams-with-skype.md) Skype for Business

**NOTE**
 - Skype for Business I telefoni IP riceveranno chiamate, anche se l'utente è in modalità TeamsOnly.  
 - Gli utenti a cui è stato eseguito il provisioning con licenze Sistema telefonico e Piani per chiamate per l'uso con Skype for Business Online (ad esempio, a cui è stato assegnato il valore OnlineVoiceRoutingPolicy) avranno la scheda Chiamate abilitata in Teams e potranno effettuare chiamate PSTN in uscita da Teams senza che gli amministratori eseere necessario eseguire alcuna azione amministrativa.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Come configurare gli utenti per la ricezione di tutte le chiamate VOIP e PSTN in Teams
Per assicurarsi che gli utenti ricevano tutte le chiamate VOIP e PSTN in arrivo in Teams, impostare la modalità di coesistenza dell'utente su TeamsOnly nell'interfaccia di amministrazione di Microsoft Teams oppure usare una sessione di Windows PowerShell Skype for Business remota per aggiornare TeamsUpgradePolicy nel modo seguente:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Vedere anche
[Configurare i piani per chiamate](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)

[Phone System e Piani di Chiamata](calling-plan-landing-page.md)

[Skype for Business Informazioni di riferimento sul cmdlet di PowerShell](/powershell/module/skype)
