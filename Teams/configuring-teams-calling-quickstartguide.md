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
description: Guida introduttiva per la configurazione di piani per chiamate in Microsoft Teams per consentire l'esecuzione di un set di utenti.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c43decd3b3f7d5e23e0e7937a93b4663a80aa583
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799766"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guida introduttiva: Configurazione dei piani di chiamata su Microsoft Teams
==============================================================

Questa guida ti aiuterà a far iniziare un set di utenti in modo che possano esplorare i Piani per chiamate in Teams.

Leggere l'annuncio dei piani per chiamate in Teams del 12 dicembre 2017: La comunicazione intelligente fa il passo successivo con [le chiamate in Teams](https://aka.ms/ipyqus)

> [!NOTE]
> Si consiglia di leggere, in parallelo, questa [](calling-plan-landing-page.md) guida introduttiva sistema telefonico con piani per chiamate e [FastTrack](https://aka.ms/cloudvoice) per pianificare e guidare un'implementazione corretta.

Con l'aggiunta di Piani per chiamate, una funzionalità di Microsoft 365 e Office 365 basata su Skype for Business, è ora possibile utilizzare Teams per effettuare e ricevere chiamate da e verso rete fissa e cellulari tramite la rete PSTN (Public Switched Telephone Network).

![Schermata che mostra la pagina Contatti in Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Prerequisiti per l'abilitazione **della scheda** Chiamate in Teams
Per abilitare la **scheda** Chiamate in Teams, gli utenti devono avere le chiamate 1:1 abilitate in Teams e l'uso di un client Teams che supporta le chiamate 1:1 Teams. Per informazioni su come gestire le chiamate 1:1 in Teams, leggi [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) Per informazioni sui client che supportano le chiamate, leggere [limiti e specifiche per Microsoft Teams.](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)

> [!NOTE]
> Attualmente, la segreteria telefonica non sarà disponibile nella scheda Chiamate a meno che l'utente non sia abilitato per le chiamate PSTN. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Prerequisiti per l'abilitazione della **tastiera del** telefono in Teams
Per abilitare la **scheda della tastiera** del telefono in Teams e consentire agli utenti di effettuare e ricevere chiamate PSTN, è necessario effettuare il provisioning degli utenti per Sistema telefonico e Piani per chiamate. Per informazioni su come configurare i Piani per chiamate, vedere [Configurare i Piani per chiamate.](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)
Inoltre, per gli utenti di Teams, è necessario assicurarsi che l'opzione "Consenti chiamate private" sia abilitata nel criterio di chiamata di Teams. Per [altre informazioni, vedere](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) Gestire Teams durante la transizione alla nuova interfaccia di amministrazione di Microsoft Teams.
> [!NOTE]
> È anche possibile usare l'instradamento diretto per consentire agli utenti di effettuare e ricevere chiamate PSTN. Per informazioni su come configurare il routing diretto, vedere [Configurare il routing diretto.](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Uso di TeamsUpgradePolicy per controllare l'arrivo delle chiamate
Per controllare se le chiamate in arrivo (e le chat) vengono effettuate in Teams o Skype for Business, gli amministratori usano TeamsUpgradePolicy, utilizzando l'interfaccia di amministrazione di [Microsoft Teams](https://aka.ms/teamsadmincenter) o una sessione di Windows PowerShell remota con i cmdlet di Skype [for Business.](https://docs.microsoft.com/powershell/module/skype)


La configurazione predefinita di TeamsUpgradePolicy è la modalità Isole, che è progettata per garantire che i flussi di lavoro aziendali esistenti non si interruppeno durante una distribuzione di Teams. Per impostazione predefinita, le chiamate VoIP, PSTN e federate agli utenti continueranno a essere instradate a Skype for Business fino a quando non si aggiorna il criterio per abilitare le chiamate in ingresso a Teams.  Quando i destinatari sono in modalità isole:

 - Le chiamate VOIP in arrivo provenienti da Skype for Business vengono sempre effettuate nel client Skype for Business del destinatario.
 - Le chiamate VOIP in arrivo provenienti da Teams vengono effettuate in Teams, se il mittente e il destinatario *sono nello stesso tenant.*
 - Le chiamate VOIP federate in arrivo (indipendentemente dal client di origine) e le chiamate PSTN vengono sempre effettuate nel client Skype for Business del destinatario.
 
Per fare in modo che le chiamate VOIP e PSTN in arrivo siano sempre effettuate nel client Teams di un utente, aggiornare la modalità di coesistenza dell'utente in modo che sia TeamsOnly (quindi assegnargli l'istanza "UpgradeToTeams" di TeamsUpgradePolicy).  Per ulteriori informazioni sulle modalità di coesistenza e su TeamsUpgradePolicy, consulta le indicazioni sulla migrazione e [l'interoperabilità](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype) per le organizzazioni che usano Teams insieme a Skype for Business

**NOTE**
 - I telefoni IP di Skype for Business riceveranno le chiamate, anche se l'utente è in modalità TeamsOnly.  
 - Gli utenti che hanno effettuato il provisioning con licenze Sistema telefonico e Piani per chiamate per l'uso con Skype for Business online (ad esempio, a cui è stato assegnato un valore OnlineVoiceRoutingPolicy), avranno la scheda Chiamate abilitata in Teams e possono effettuare chiamate PSTN in uscita da Teams senza che gli amministratori devono eseguire alcuna azione amministrativa.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Come configurare gli utenti per la ricezione di tutte le chiamate VOIP e PSTN in arrivo in Teams
Per assicurare che gli utenti ricevano tutte le chiamate VOIP e PSTN in arrivo in Teams, impostare la modalità di coesistenza dell'utente su TeamsOnly nell'interfaccia di amministrazione di Microsoft Teams oppure usare la sessione di Windows PowerShell remota di Skype for Business per aggiornare TeamsUpgradePolicy come segue:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Vedere anche
[Configurare i piani per chiamate](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Phone System e Piani di Chiamata](calling-plan-landing-page.md)

[Informazioni di riferimento per i cmdlet di PowerShell per Skype for Business](https://docs.microsoft.com/powershell/module/skype)

