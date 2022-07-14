---
title: Guida introduttiva - Configurazione dei piani per chiamate
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guida introduttiva per la configurazione dei piani di chiamata in Microsoft Teams, in modo da poter impostare e rendere operativo un gruppo di utenti.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0ff6c85e337e2a3fe226347fc0b0ef68710d3d18
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789581"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guida introduttiva: Configurazione dei piani di chiamata su Microsoft Teams

Questa guida ti aiuterà a configurare e rendere operativo un gruppo di utenti in modo che possano esplorare i piani per chiamate in Teams.

Leggi l'annuncio del 12 dicembre 2017 dei Piani per chiamate in Teams: [Intelligent Communications fa il passo successivo con le chiamate in Teams](https://aka.ms/ipyqus)

> [!NOTE]
> È consigliabile, in parallelo con questa guida introduttiva, leggere [Sistema telefonico con piani per chiamate](calling-plan-landing-page.md) e [FastTrack](https://aka.ms/cloudvoice) per pianificare e condurre un'implementazione corretta.

Aggiungendo Piani per chiamate, una funzionalità di Microsoft 365 e Office 365 con tecnologia Skype for Business, ora è possibile usare Teams per effettuare e ricevere chiamate telefoniche da o verso linee terrestri e telefoni cellulari tramite la rete PSTN (Public Switched Telephone Network).

![Screenshot che mostra la pagina Contatti in Teams.](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Prerequisiti per abilitare la scheda **Chiamate** in Teams
Per abilitare la scheda **Chiamate** in Teams, gli utenti devono avere abilitato le chiamate 1:1 in Teams e usare un client di Teams che supporta le chiamate teams 1:1. Per informazioni su come gestire le chiamate 1:1 in Teams, leggi [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy). Per informazioni su quali client supportano le chiamate, leggi [Limiti e specifiche per Microsoft Teams](./limits-specifications-teams.md).

> [!NOTE]
> Attualmente, la segreteria telefonica non sarà disponibile nella scheda Chiamate, a meno che l'utente non sia abilitato per le chiamate PSTN. 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>Prerequisiti per abilitare la **tastiera del telefono** in Teams
Per abilitare la scheda **Tastiera** del telefono in Teams e consentire agli utenti di effettuare e ricevere chiamate PSTN, è necessario effettuare il provisioning degli utenti per Sistema telefonico e Piani per chiamate. Per informazioni su come configurare i Piani per chiamate, leggi [Configurare i piani per chiamate](./set-up-calling-plans.md).
Inoltre, per gli utenti di Teams, è necessario verificare che l'opzione "Consenti chiamate private" sia abilitata nei criteri di chiamata di Teams. Per altre informazioni, vedere [Gestire Teams durante la transizione alla nuova interfaccia di amministrazione di Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md) .
> [!NOTE]
> È anche possibile usare l'instradamento diretto per consentire agli utenti di effettuare e ricevere chiamate PSTN. Per informazioni su come configurare il routing diretto, vedere [Configurare il routing diretto](./direct-routing-configure.md).

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>Uso di TeamsUpgradePolicy per controllare dove atterrano le chiamate
Per controllare se le chiamate in arrivo (e le chat) atterrano in Teams o in Skype for Business, gli amministratori usano TeamsUpgradePolicy, utilizzando [l'interfaccia di amministrazione di Microsoft Teams](https://aka.ms/teamsadmincenter) o una sessione di Windows PowerShell remota con i cmdlet [Skype for Business](/powershell/module/skype).


La configurazione predefinita di TeamsUpgradePolicy è la modalità Isole, progettata per garantire che i flussi di lavoro aziendali esistenti non vengano interrotti durante una distribuzione di Teams. Per impostazione predefinita, le chiamate VoIP, PSTN e federate agli utenti continueranno a essere instradate a Skype for Business finché non si aggiorna il criterio per abilitare le chiamate in ingresso a Teams.  Quando i destinatari sono in modalità isole:

 - Le chiamate VOIP in arrivo provenienti da Skype for Business atterrano sempre nel client Skype for Business del destinatario.
 - Le chiamate VOIP in arrivo che hanno avuto origine in Teams atterrano in Teams, *se il mittente e il destinatario si trovano nello stesso tenant*.
 - Le chiamate VOIP federate in ingresso (indipendentemente dal client di origine) e le chiamate PSTN vengono sempre effettuate nel client Skype for Business del destinatario.
 
Per garantire che le chiamate VOIP e PSTN in arrivo atterrano sempre nel client teams di un utente, aggiornare la modalità di coesistenza dell'utente su TeamsOnly (il che significa che assegnare loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy.  Per altre informazioni sulle modalità di coesistenza e su TeamsUpgradePolicy, vedere [Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)

**NOTE**
 - Skype for Business telefoni IP riceveranno chiamate, anche se l'utente è in modalità TeamsOnly.  
 - Gli utenti di cui è stato eseguito il provisioning con licenze Sistema telefonico e Piani per chiamate per l'uso con Skype for Business Online (ad esempio, a cui è stato assegnato un valore di OnlineVoiceRoutingPolicy), avrà la scheda Chiamate abilitata in Teams e può effettuare chiamate PSTN in uscita da Teams senza che gli amministratori abbiano l'esigenza di eseguire alcuna azione amministrativa.


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>Come configurare gli utenti per la ricezione di tutte le chiamate VOIP e PSTN in arrivo in Teams
Per garantire che gli utenti ricevano tutte le chiamate VOIP e PSTN in arrivo in Teams, impostare la modalità di coesistenza dell'utente su TeamsOnly nell'interfaccia di amministrazione di Microsoft Teams oppure usare Skype for Business sessione di Windows PowerShell remota per aggiornare TeamsUpgradePolicy come segue:

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>Vedere anche
[Configurare i piani per chiamate](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)

[Phone System e Piani di Chiamata](calling-plan-landing-page.md)

[riferimento ai cmdlet di Skype for Business PowerShell](/powershell/module/skype)
