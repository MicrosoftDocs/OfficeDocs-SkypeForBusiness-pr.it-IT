---
title: Strategie di aggiornamento per gli amministratori IT
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: L'articolo è per gli amministratori IT e descrive le strategie per implementare l'aggiornamento da Skype for Business a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb884f26862466dcd70c9efe81e5293d277adbde
ms.sourcegitcommit: b0753baa55841a2c6c5dc006dcdd117704af3b42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2021
ms.locfileid: "50401347"
---
# <a name="upgrade-strategies-for-it-administrators"></a>Strategie di aggiornamento per gli amministratori IT

![Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo è per gli amministratori IT che vogliono implementare l'aggiornamento a Teams da Skype for Business.

Prima di implementare l'aggiornamento, è consigliabile vedere gli articoli seguenti che descrivono i concetti importanti per l'aggiornamento e i comportamenti di coesistenza:

- [Comprendere la coesistenza e l'interoperabilità di Microsoft Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modalità di coesistenza - Riferimento](migration-interop-guidance-for-teams-with-skype.md)
- [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Opzioni di aggiornamento

Questa sezione descrive come implementare l'aggiornamento usando una delle opzioni di aggiornamento seguenti:

- [Aggiornamento delle funzionalità di sovrapposizione (con la modalità Isole)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Aggiornamento delle funzionalità di selezione per un'organizzazione che non ha ancora iniziato a usare Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Aggiornamento delle funzionalità di selezione per un'organizzazione che usa già Teams in modalità Isole](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Se hai bisogno di maggiori informazioni sulle opzioni, assicurati di aver già letto Scegli il percorso di aggiornamento [da Skype for Business a Teams.](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Aggiornamento delle funzionalità di sovrapposizione (con la modalità Isole)

Per l'opzione di aggiornamento delle funzionalità sovrapposte:

- Considerare questa opzione se è possibile eseguire un aggiornamento rapido per l'intera organizzazione.  Dal momento che esiste il rischio di confusione per gli utenti finali che eseguono entrambi i client, è meglio se è possibile ridurre al minimo il periodo di tempo durante il quale gli utenti devono eseguire entrambi i client. Assicurarsi che gli utenti sappiano di eseguire entrambi i client.

- Questa opzione è il modello predefinito e non richiede l'intervento dell'amministratore per iniziare a usare Teams se non per assegnare la licenza di Microsoft 365 o Office 365. Se i tuoi utenti hanno già Skype for Business online, potresti già utilizzare questo modello.

- Può essere difficile uscire dalla modalità di sovrapposizione e passare alla modalità TeamsOnly. Poiché gli utenti aggiornati comunicano solo tramite Teams, qualsiasi altro utente dell'organizzazione che comunica con quell'utente deve usare Teams.  Se ci sono utenti che non hanno iniziato a usare Teams, verranno esposti a messaggi mancanti. Inoltre, non potranno vedere gli utenti TeamsOnly online in Skype for Business. Alcune organizzazioni scelgono di eseguire un aggiornamento a livello di tenant usando i criteri globali tenant per evitare questo problema, tuttavia questa operazione richiede una pianificazione anticipata e l'attesa che tutti gli utenti siano pronti per l'aggiornamento.


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Aggiornamento delle funzionalità di selezione per un'organizzazione che non ha ancora iniziato a usare Teams

Se l'organizzazione non ha ancora utenti attivi in Teams, il primo passaggio consiste nell'impostare il criterio predefinito a livello di tenant per TeamsUpgradePolicy su una delle modalità di Skype for Business, ad esempio SfbWithTeamsCollab.  Gli utenti che non hanno ancora iniziato a usare Teams non noteranno alcuna differenza di comportamento. Tuttavia, l'impostazione di questo criterio a livello di tenant consente di avviare l'aggiornamento degli utenti alla modalità TeamsOnly e assicura che gli utenti aggiornati possano comunque comunicare con gli utenti non aggiornati.  Dopo aver identificato gli utenti del programma pilota, è possibile aggiornarli a TeamsOnly.  Se sono locali, usa Move-CsUser. Se sono online, è sufficiente assegnare loro la modalità TeamsOnly utilizzando Grant-CsTeamsUpgradePolicy. Per impostazione predefinita, tutte le riunioni Skype for Business pianificate da questi utenti vengono trasferite a Teams.

Di seguito sono riportati i comandi principali:

1. Impostare l'impostazione predefinita a livello di tenant sulla modalità SfbWithTeamsCollab come segue:

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

Note
 
- Invece di impostare i criteri a livello di tenant su SfbWithTeamsCollab, è possibile impostarlo su SfbWithTeamsCollabAndMeetings. In questo modo tutti gli utenti possono pianificare tutte le nuove riunioni in Teams.
- `Move-CsUser` è un cmdlet negli strumenti locali. `MoveToTeams`L'aggiornamento richiede Skype for Business Server 2019 o Skype for Business Server 2015 con CU8 o versione successiva. Se si usa una versione precedente, è possibile spostare l'utente in Skype for Business online e quindi concedere la modalità TeamsOnly a tale utente.
- Per impostazione predefinita, le riunioni di Skype for Business vengono migrate in Teams quando si esegue l'aggiornamento alla modalità TeamsOnly o quando si assegna la modalità SfbWithTeamsCollabAndMeetings.  

Il diagramma seguente illustra le fasi concettuali dell'aggiornamento delle funzionalità di selezione per un'organizzazione senza utilizzo precedente di Teams. L'altezza delle barre rappresenta il numero di utenti. Durante qualsiasi fase dell'aggiornamento, tutti gli utenti possono comunicare tra loro.  Gli utenti di Skype for Business comunicano con gli utenti TeamsOnly utilizzando Interoperabilità e viceversa. Gli utenti in modalità Isole devono assicurarsi di eseguire entrambi i client.

![Diagramma che mostra l'aggiornamento delle funzionalità di selezione senza l'uso precedente di Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Aggiornamento delle funzionalità di selezione per un'organizzazione che usa già Teams in modalità Isole

Se alcuni utenti dell'organizzazione usano attivamente Teams in modalità Isole, probabilmente non si vorrà rimuovere la funzionalità dagli utenti esistenti. Pertanto, è necessario eseguire un passaggio aggiuntivo prima di modificare i criteri a livello di tenant. La soluzione consiste nel "sorreire" questi utenti di Teams attivi nella modalità Isole, prima di impostare i criteri a livello di tenant su SfbWithTeamsCollab.  Al termine, è possibile procedere con la distribuzione come descritto sopra, tuttavia, si avranno due gruppi di utenti che passano a TeamsOnly: gli utenti attivi in Teams saranno in modalità Isole, mentre gli utenti rimanenti saranno in modalità SfbWithTeamsCollab. È possibile spostare progressivamente questi utenti in modalità TeamsOnly.

1. Per trovare gli utenti attivi in Teams, seguire questa procedura:

   1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365 passare a Report e quindi Utilizzo. 
   2. Nell'elenco a discesa "Seleziona un report" scegliere Microsoft Teams e quindi Attività utente. Verrà fornito un sommario esportabile degli utenti che sono stati attivi in Teams. 
   3. Fare clic su Esporta, aprire Excel e filtrare per visualizzare solo gli utenti attivi in Teams.

2. Per ogni utente di Teams attivo individuato nel passaggio 1, assegnare la modalità Isole in una sessione remota di PowerShell. In questo modo è possibile andare al passaggio successivo e assicurarsi di non modificare l'esperienza utente.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Impostare i criteri a livello di tenant su SfbWithTeamsCollab:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Aggiornare gli utenti selezionati alla modalità TeamsOnly. È possibile scegliere di aggiornare gli utenti in modalità Isole o SfbWithTeamsCollab, anche se è consigliabile assegnare prima priorità all'aggiornamento degli utenti in modalità Isole per ridurre al minimo il rischio di confusione che possono verificarsi quando gli utenti sono in modalità Isole.   

   Per gli utenti ospitati in Skype for Business online:  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Per gli utenti ospitati in Skype for Business Server locale:  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

Il diagramma seguente illustra le fasi concettuali di una transizione delle funzionalità selezionate in cui all'inizio sono presenti utenti di isole attive. L'altezza delle barre rappresenta il numero di utenti. Durante qualsiasi fase dell'aggiornamento, tutti gli utenti possono comunicare tra loro.  Gli utenti di Skype for Business comunicano con gli utenti TeamsOnly usando l'interoperabilità e viceversa. 


![Diagramma che illustra l'aggiornamento delle funzionalità di selezione con gli utenti attivi in modalità Isole](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>Collegamenti correlati

[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio MMS (Meeting Migration Service)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

