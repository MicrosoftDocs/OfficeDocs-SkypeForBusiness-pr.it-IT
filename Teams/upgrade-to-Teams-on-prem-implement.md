---
title: Strategie di aggiornamento per gli amministratori IT
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: L'articolo è rivolto agli amministratori IT e descrive le strategie per implementare l'aggiornamento da Skype for Business a Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f403b12ffc8cabbfebe8a30268eb3e6dad468f32
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681737"
---
# <a name="upgrade-strategies-for-it-administrators"></a>Strategie di aggiornamento per gli amministratori IT

![Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione.](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo è rivolto agli amministratori IT che vogliono implementare l'aggiornamento a Teams da Skype for Business.

Prima di implementare l'aggiornamento, sono consigliati gli articoli seguenti che descrivono importanti concetti di aggiornamento e comportamenti di coesistenza:

- [Comprendere la coesistenza e l'interoperabilità di Microsoft Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modalità di coesistenza - Riferimento](migration-interop-guidance-for-teams-with-skype.md)
- [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Opzioni di aggiornamento

In questa sezione viene descritto come implementare l'aggiornamento usando una delle opzioni seguenti:

- [Aggiornamento delle funzionalità sovrapposte (tramite la modalità Isole)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Aggiornamento delle funzionalità selezionate per un'organizzazione che non ha ancora iniziato a usare Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Aggiornamento delle funzionalità selezionate per un'organizzazione che usa già Teams in modalità Isole](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Per altre informazioni sulle opzioni, assicurarsi di aver già letto [Scegliere il percorso di aggiornamento da Skype for Business a Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Aggiornamento delle funzionalità sovrapposte (tramite la modalità Isole)

Per l'opzione di aggiornamento delle funzionalità sovrapposte:

- Prendere in considerazione questa opzione se è possibile eseguire un aggiornamento rapido per l'intera organizzazione.  Poiché esiste un potenziale rischio di confusione per gli utenti finali con l'esecuzione di entrambi i client, è consigliabile ridurre al minimo il periodo di tempo durante il quale gli utenti devono eseguire entrambi i client. Assicurarsi che gli utenti sappiano di eseguire entrambi i client.

- Questa opzione è il modello predefinito e non richiede l'intervento dell'amministratore per iniziare a usare Teams se non per assegnare la licenza Microsoft 365 o Office 365. Se gli utenti hanno già Skype for Business Online, è possibile che tu stia già facendo parte di questo modello.

- Può essere difficile uscire dalla modalità di funzionalità sovrapposte e passare a TeamsOnly. Poiché gli utenti aggiornati comunicano solo tramite Teams, qualsiasi altro utente dell'organizzazione che comunica con quell'utente deve usare Teams.  Se alcuni utenti non hanno iniziato a usare Teams, verranno esposti ai messaggi mancanti. Inoltre, non vedranno gli utenti di TeamsOnly online in Skype for Business. Alcune organizzazioni scelgono di eseguire un aggiornamento a livello di tenant usando i criteri globali tenant per evitarlo, tuttavia ciò richiede una pianificazione anticipata e un'attesa che tutti gli utenti siano pronti per l'aggiornamento.

## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Aggiornamento delle funzionalità selezionate per un'organizzazione che non ha ancora iniziato a usare Teams

Se l'organizzazione non ha ancora utenti attivi in Teams, il primo passaggio consiste nell'impostare il criterio predefinito a livello di tenant per TeamsUpgradePolicy su una delle modalità di Skype for Business, ad esempio SfbWithTeamsCollab.  Gli utenti che non hanno ancora iniziato a usare Teams non noteranno alcuna differenza di comportamento. Tuttavia, l'impostazione di questo criterio a livello di tenant consente di avviare l'aggiornamento degli utenti alla modalità TeamsOnly e assicura che gli utenti aggiornati possano comunque comunicare con utenti non aggiornati.  Dopo aver identificato gli utenti pilota, è possibile aggiornarli a TeamsOnly.  Se sono in locale, utilizza Move-CsUser. Se sono online, è sufficiente assegnargli la modalità TeamsOnly utilizzando Grant-CsTeamsUpgradePolicy. Per impostazione predefinita, tutte le riunioni Skype for Business pianificate da questi utenti verranno spostate in Teams.

Di seguito sono elencati i comandi principali:

1. Impostare la modalità predefinita a livello di tenant SfbWithTeamsCollab come indicato di seguito:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Aggiornare gli utenti pilota a TeamsOnly come segue:

   - Per un utente online:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username
     ```

   - Per un utente locale:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
     ```

**Note**:

- Invece di impostare il criterio a livello di tenant su SfbWithTeamsCollab, è possibile impostarlo su SfbWithTeamsCollabAndMeetings. In questo modo tutti gli utenti pianificare tutte le nuove riunioni in Teams.
- Per impostazione predefinita, la migrazione delle riunioni Skype for Business viene eseguita in Teams quando si esegue l'aggiornamento alla modalità TeamsOnly o quando si assegna la modalità SfbWithTeamsCollabAndMeetings.

> [!NOTE]
> In vista del ritiro imminente di Skype for Business Online, Microsoft ha semplificato il modo in cui le organizzazioni passano a Teams. Non è più necessario specificare il `-MoveToTeams` passaggio `Move-CsUser` per spostare gli utenti direttamente dall'ambiente locale direttamente a TeamsOnly. In precedenza, se questo parametro non era specificato, gli utenti passavano da Skype for Business Server locale a Skype for Business Online e la loro modalità rimaneva invariata. Ora, quando si sposta un utente dall'ambiente locale al cloud con `Move-CsUser`, agli utenti viene automaticamente assegnata la modalità TeamsOnly e le riunioni da locale vengono convertite automaticamente in riunioni Teams, proprio come se , `-MoveToTeams switch had been specified`indipendentemente dal fatto che l'opzione sia effettivamente specificata. Questo comportamento è disponibile in tutte le versioni di Skype For Business Server e Lync Server 2013, che non sono mai supportate.`-MoveToTeams`

Il diagramma seguente mostra le fasi concettuali dell'aggiornamento delle funzionalità selezionate per un'organizzazione senza un uso precedente di Teams. L'altezza delle barre rappresenta il numero di utenti. Durante qualsiasi fase dell'aggiornamento, tutti gli utenti possono comunicare tra loro.  Skype for Business gli utenti comunicano con TeamsSolo gli utenti che usano Interop e viceversa. Gli utenti in modalità Isole devono assicurarsi di eseguire entrambi i client.

![Diagramma che mostra l'aggiornamento delle funzionalità di selezione senza un uso precedente di Teams.](media/teams-upgrade-1.png)

## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Aggiornamento delle funzionalità selezionate per un'organizzazione che usa già Teams in modalità Isole

Se alcuni utenti dell'organizzazione usano attivamente Teams in modalità Isole, probabilmente non si vogliono rimuovere le funzionalità dagli utenti esistenti. Di conseguenza, è necessario un passaggio aggiuntivo prima di modificare i criteri a livello di tenant. La soluzione consiste nel "nonno" di questi utenti attivi Teams in modalità Isole, prima di impostare il criterio a livello di tenant su SfbWithTeamsCollab.  Una volta fatto questo, è possibile procedere con la distribuzione come sopra, tuttavia, si avranno due gruppi di utenti che si stanno trasferendo a TeamsOnly: gli utenti che erano attivi in Teams saranno in modalità Isole e gli altri utenti saranno in modalità SfbWithTeamsCollab. È possibile spostare progressivamente questi utenti in modalità TeamsOnly.

1. Per trovare gli utenti attivi in Teams, eseguire le operazioni seguenti:

   1. Dal interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento sinistro, passare a Report e quindi Uso.
   2. Nell'elenco a discesa "Seleziona un report" scegliere Microsoft Teams e quindi Attività utente. Verrà fornita una tabella esportabile di utenti che sono stati attivi in Teams.
   3. Fare clic su Esporta, aprire Excel e filtrare per visualizzare solo gli utenti attivi in Teams.

2. Per ogni utente attivo Teams individuato nel passaggio 1, assegnargli la modalità Isole in una modalità remota di PowerShell. In questo modo è possibile procedere con il passaggio successivo e assicurarsi di non modificare l'esperienza utente.

   ```PowerShell
   $users=get-content "C:\MyPath\users.txt"
    foreach ($user in $users){
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands}
   ```

3. Impostare i criteri a livello di tenant su SfbWithTeamsCollab:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab
   ```

4. Aggiorna gli utenti selezionati alla modalità TeamsOnly. È possibile scegliere di aggiornare gli utenti in modalità Isole o SfbWithTeamsCollab, anche se è consigliabile assegnare la priorità all'aggiornamento degli utenti in modalità Isole per ridurre al minimo il rischio di confusione che può verificarsi quando gli utenti sono in modalità Isole.

   Per gli utenti ospitati in Skype for Business Online:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams
   ```

   Per gli utenti ospitati in Skype for Business Server locale:

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
   ```

Il diagramma seguente mostra le fasi concettuali di una transizione di selezione delle funzionalità in cui all'inizio ci sono utenti di Isole attive. L'altezza delle barre rappresenta il numero di utenti. Durante qualsiasi fase dell'aggiornamento, tutti gli utenti possono comunicare tra loro.  Skype for Business gli utenti comunicano con TeamsSolo gli utenti che usano Interop e viceversa.

![Diagramma che mostra l'aggiornamento delle funzionalità selezionate con gli utenti attivi in modalità Isole.](media/teams-upgrade-2.png)

## <a name="related-links"></a>Collegamenti correlati

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Uso del servizio MMS (Meeting Migration Service)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
