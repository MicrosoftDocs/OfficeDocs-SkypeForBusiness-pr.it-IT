---
title: Strategie di aggiornamento per gli amministratori IT
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: L'articolo è per gli amministratori IT e descrive le strategie per implementare l'aggiornamento da Skype for Business a Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c44d988bdcfbd08f462a99c76b4095bb01ac60c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619342"
---
# <a name="upgrade-strategies-for-it-administrators"></a>Strategie di aggiornamento per gli amministratori IT

![Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione")

Questo articolo è per gli amministratori IT che vogliono implementare l'aggiornamento a Teams da Skype for Business.

Prima di implementare l'aggiornamento, è consigliabile seguire gli articoli seguenti che descrivono i concetti importanti per l'aggiornamento e i comportamenti di coesistenza:

- [Comprendere Microsoft Teams e Skype for Business coesistenza e interoperabilità](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modalità di coesistenza - Riferimento](migration-interop-guidance-for-teams-with-skype.md)
- [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Opzioni di aggiornamento

Questa sezione descrive come implementare l'aggiornamento usando una delle opzioni di aggiornamento seguenti:

- [Aggiornamento delle funzionalità sovrapposte (con la modalità Isole)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Aggiornamento delle funzionalità di selezione per un'organizzazione che non ha ancora iniziato a usare Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Aggiornamento delle funzionalità di selezione per un'organizzazione che usa già Teams in modalità Isole](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Per altre informazioni sulle opzioni, verificare di aver già letto Scegliere il percorso di aggiornamento da [Skype for Business a Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Aggiornamento delle funzionalità sovrapposte (con la modalità Isole)

Per l'opzione di aggiornamento delle funzionalità sovrapposte:

- Considerare questa opzione se è possibile eseguire un aggiornamento rapido per l'intera organizzazione.  Poiché esiste un potenziale rischio di confusione per gli utenti finali che eseguono entrambi i client, è meglio ridurre al minimo il periodo di tempo durante il quale gli utenti devono eseguire entrambi i client. È consigliabile assicurarsi che gli utenti sappiano di eseguire entrambi i client.

- Questa opzione è il modello predefinito e non richiede l'azione dell'amministratore per iniziare a usare Teams se non per assegnare la licenza Microsoft 365 o Office 365. Se gli utenti hanno già Skype for Business Online, è possibile che si sia già in questo modello.

- Può essere difficile uscire dalla modalità di sovrapposizione delle funzionalità e passare a TeamsOnly. Poiché gli utenti aggiornati comunicano solo tramite Teams, qualsiasi altro utente dell'organizzazione che comunica con tale utente deve usare Teams.  Se si hanno utenti che non hanno iniziato a Teams, questi verranno esposti ai messaggi mancanti. Inoltre, non potranno vedere gli utenti di TeamsOnly online in Skype for Business. Alcune organizzazioni scelgono di eseguire un aggiornamento a livello di tenant usando i criteri globali tenant per evitare questo problema, tuttavia ciò richiede una pianificazione iniziale e attende che tutti gli utenti siano pronti per l'aggiornamento.


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Aggiornamento delle funzionalità di selezione per un'organizzazione che non ha ancora iniziato a usare Teams

Se l'organizzazione non ha ancora utenti attivi in Teams, il primo passaggio consiste nell'impostare i criteri predefiniti a livello di tenant per TeamsUpgradePolicy su una delle modalità di Skype for Business, ad esempio SfbWithTeamsCollab.  Gli utenti che non hanno ancora iniziato a Teams non noteranno alcuna differenza di comportamento. Tuttavia, l'impostazione di questo criterio a livello di tenant consente di avviare l'aggiornamento degli utenti alla modalità TeamsOnly e assicura che gli utenti aggiornati possano comunque comunicare con utenti non aggiornati.  Dopo aver identificato gli utenti pilota, è possibile aggiornarli a TeamsOnly.  Se sono locali, usare Move-CsUser. Se sono online, è sufficiente assegnare loro la modalità TeamsOnly usando Grant-CsTeamsUpgradePolicy. Per impostazione predefinita, Skype for Business le riunioni pianificate da questi utenti verranno migrate in Teams.

Di seguito sono riportati i comandi principali:

1. Impostare l'impostazione predefinita a livello di tenant sulla modalità SfbWithTeamsCollab nel modo seguente:

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
 
- Invece di impostare i criteri a livello di tenant su SfbWithTeamsCollab, è possibile impostarlo su SfbWithTeamsCollabAndMeetings. In questo modo tutti gli utenti pianificano tutte le nuove riunioni Teams.
- Per impostazione predefinita, Skype for Business le riunioni vengono migrate in Teams durante l'aggiornamento alla modalità TeamsOnly o quando si assegna la modalità SfbWithTeamsCollabAndMeetings.  

> [!NOTE]
> In preparazione del prossimo ritiro di Skype for Business Online, Microsoft ha semplificato il modo in cui le organizzazioni si spostano in Teams. Non è più necessario specificare il passaggio per spostare gli utenti direttamente `-MoveToTeams` dall'ambiente locale direttamente a `Move-CsUser` TeamsOnly. In precedenza, se questo parametro non è stato specificato, gli utenti passavano dall'abitazione Skype for Business Server locale a Skype for Business Online e la modalità rimaneva invariata. Ora quando si sposta un utente dall'ambiente locale al cloud con , agli utenti viene assegnata automaticamente la modalità TeamsOnly e le riunioni da locale vengono convertite automaticamente in riunioni Teams, come se fosse , indipendentemente dal fatto che l'opzione sia effettivamente `Move-CsUser` `-MoveToTeams switch had been specified` specificata. Questo comportamento è disponibile in tutte le versioni di Skype For Business Server e Lync Server 2013 (che non hanno mai avuto il supporto per `-MoveToTeams` ).

Il diagramma seguente mostra le fasi concettuali dell'aggiornamento delle funzionalità di selezione per un'organizzazione senza l'uso preventivo di Teams. L'altezza delle barre rappresenta il numero di utenti. Durante qualsiasi fase dell'aggiornamento, tutti gli utenti possono comunicare tra loro.  Skype for Business gli utenti comunicano con TeamsSolo gli utenti che usano l'interoperabilità e viceversa. Gli utenti in modalità Isole devono essere sicuri di eseguire entrambi i client.

![Diagramma che mostra l'aggiornamento delle funzionalità di selezione senza l'uso preventivo di Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Aggiornamento delle funzionalità di selezione per un'organizzazione che usa già Teams in modalità Isole

Se alcuni utenti dell'organizzazione usano attivamente Teams in modalità Isole, è probabile che non si voglia rimuovere la funzionalità dagli utenti esistenti. Pertanto, prima di modificare i criteri a livello di tenant è necessario un passaggio aggiuntivo. La soluzione consiste nel "nonno" di questi utenti attivi Teams in modalità Isole, prima di impostare i criteri a livello di tenant su SfbWithTeamsCollab.  Dopo aver eseguito questa operazione, è possibile procedere con la distribuzione come descritto sopra, tuttavia, si avranno due gruppi di utenti che si spostano in TeamsOnly: gli utenti che erano attivi in Teams saranno in modalità Isole e gli utenti rimanenti saranno in modalità SfbWithTeamsCollab. È possibile spostare progressivamente questi utenti in modalità TeamsOnly.

1. Trovare gli utenti attivi in Teams nel modo seguente:

   1. Nel riquadro interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento sinistro, passare a Report e quindi a Uso. 
   2. Nell'elenco a discesa "Seleziona un report" scegliere Microsoft Teams e quindi Attività utente. In questo modo verrà mostrata una tabella esportabile degli utenti che sono stati attivi in Teams. 
   3. Fare clic su Esporta, Excel e filtrare per visualizzare solo gli utenti attivi in Teams.

2. Per ogni utente Teams attivo trovato nel passaggio 1, assegnargli la modalità Isole in una sessione remota di PowerShell. In questo modo è possibile andare al passaggio successivo e assicurarsi di non modificare l'esperienza utente.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Impostare i criteri a livello di tenant su SfbWithTeamsCollab:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Aggiornare gli utenti selezionati alla modalità TeamsOnly. È possibile scegliere di aggiornare gli utenti in modalità Isole o SfbWithTeamsCollab, anche se è consigliabile assegnare priorità all'aggiornamento degli utenti in modalità Isole per ridurre al minimo il potenziale di confusione che può verificarsi quando gli utenti sono in modalità Isole.   

   Per gli utenti ospitati in Skype for Business Online:  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Per gli utenti ospitati in Skype for Business Server locale:  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

Il diagramma seguente mostra le fasi concettuali di una transizione di funzionalità selezionate in cui sono presenti utenti delle Isole attive all'inizio. L'altezza delle barre rappresenta il numero di utenti. Durante qualsiasi fase dell'aggiornamento, tutti gli utenti possono comunicare tra loro.  Skype for Business gli utenti comunicano con TeamsSolo gli utenti che usano l'interoperabilità e viceversa. 


![Diagramma che mostra l'aggiornamento delle funzionalità di selezione con gli utenti attivi in modalità Isole](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>Collegamenti correlati

[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio di migrazione delle riunioni (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
