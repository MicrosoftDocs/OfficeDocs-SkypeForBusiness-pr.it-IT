---
title: Eseguire l'aggiornamento a teams da una distribuzione locale di Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Aggiornamento da Skype for Business a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8239d1fdbda10a61cd0846a0d56b1f1ffa62f597
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955903"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Implementare l'aggiornamento da Skype for business a teams &mdash; per gli amministratori IT

Questo articolo descrive come implementare l'aggiornamento. Questo articolo è il quinto di diversi che descrivono i concetti di aggiornamento e l'implementazione per gli amministratori IT.  

- [Panoramica](upgrade-to-teams-on-prem-overview.md)
- [Metodi di aggiornamento](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Strumenti per la gestione dell'aggiornamento](upgrade-to-teams-on-prem-tools.md)
- [Considerazioni aggiuntive per le organizzazioni con Skype for business locale](upgrade-to-teams-on-prem-considerations.md)
- **Implementare l'aggiornamento** (questo articolo)
- [Considerazioni su PSTN (Public Switched Telephone Network)](upgrade-to-teams-on-prem-pstn-considerations.md)

Gli articoli seguenti descrivono inoltre importanti concetti di aggiornamento e comportamenti di coesistenza:

- [Coesistenza di teams e Skype for business](upgrade-to-teams-on-prem-coexistence.md)
- [Modalità di coesistenza-riferimento](migration-interop-guidance-for-teams-with-skype.md)
- [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Opzioni di aggiornamento

Questa sezione descrive come implementare l'aggiornamento usando una delle opzioni di aggiornamento seguenti:

- [Aggiornamento delle funzionalità sovrapposte (utilizzo della modalità isole)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Aggiornamento delle funzionalità di selezione per un'organizzazione che non ha ancora iniziato a usare Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Aggiornamento delle funzionalità di selezione per un'organizzazione che usa già teams in modalità Islands](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Per altre informazioni sulle opzioni, verificare di avere già letto i [metodi di aggiornamento](upgrade-to-teams-on-prem-upgrade-methods.md).

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Aggiornamento delle funzionalità sovrapposte (utilizzo della modalità isole)

Per l'opzione di aggiornamento delle funzionalità sovrapposte:

- Considerare questa opzione se è possibile eseguire un aggiornamento rapido per l'organizzazione complessiva.  Poiché esiste un potenziale rischio di confusione per gli utenti finali che eseguono entrambi i client, è preferibile ridurre al minimo il periodo di tempo durante il quale gli utenti devono eseguire entrambi i client. Dovresti assicurarti che gli utenti sappiano di eseguire entrambi i client.

- Questa opzione è il modello box fuori sede e non richiede l'intervento dell'amministratore per iniziare a usare teams tranne che per assegnare la licenza Microsoft 365 o Office 365. Se gli utenti hanno già Skype for business online, è possibile che si trovi già in questo modello.

- Può essere difficile uscire dalla modalità di sovrapposizione delle funzionalità e passare a TeamsOnly. Poiché gli utenti aggiornati comunicano solo tramite Team, qualsiasi altro utente dell'organizzazione che comunica con l'utente deve usare teams.  Se si hanno utenti che non hanno iniziato a usare teams, verranno esposti a messaggi mancanti. Inoltre, non vedranno gli utenti di TeamsOnly online in Skype for business. Alcune organizzazioni scelgono di eseguire un aggiornamento a livello di tenant usando i criteri globali del tenant per evitare questo problema, ma richiede la pianificazione anticipata e l'attesa finché tutti gli utenti non saranno pronti per l'aggiornamento.


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Aggiornamento delle funzionalità di selezione per un'organizzazione che non ha ancora iniziato a usare Teams

Se l'organizzazione non ha ancora utenti attivi in teams, il primo passaggio consiste nell'impostare i criteri a livello di tenant predefiniti per TeamsUpgradePolicy in una delle modalità Skype for business, ad esempio SfbWithTeamsCollab.  Gli utenti che non hanno ancora iniziato a usare teams non notano alcuna differenza di comportamento. Tuttavia, impostando questo criterio a livello di tenant, è possibile avviare l'aggiornamento degli utenti alla modalità TeamsOnly e assicurarsi che gli utenti aggiornati possano ancora comunicare con utenti non aggiornati.  Dopo aver identificato gli utenti pilota, è possibile aggiornarli in TeamsOnly.  In caso di locale, usare Move-CsUser. Se sono online, assegna semplicemente la modalità TeamsOnly usando Grant-CsTeamsUpgradePolicy. Per impostazione predefinita, tutte le riunioni Skype for business programmate da questi utenti verranno migrate in teams.

Di seguito sono riportati i comandi principali:

1. Impostare l'impostazione predefinita a livello di tenant su modalità SfbWithTeamsCollab come indicato di seguito:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Aggiornare gli utenti pilota in TeamsOnly come indicato di seguito:

   - Per un utente online:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - Per un utente locale:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

Note
 
- Invece di impostare il criterio a livello di tenant su SfbWithTeamsCollab, è possibile impostarlo su SfbWithTeamsCollabAndMeetings. In questo modo tutti gli utenti possono pianificare tutte le nuove riunioni in teams.
- `Move-CsUser` è un cmdlet negli strumenti locali. Lo `MoveToTeams` Switch richiede Skype for Business server 2019 o Skype for Business server 2015 con CU8 o versioni successive. Se si usa una versione precedente, è possibile prima di tutto trasferire l'utente in Skype for business online e quindi concedere la modalità TeamsOnly a tale utente.
- Per impostazione predefinita, le riunioni di Skype for business vengono migrate in teams quando si esegue l'aggiornamento alla modalità TeamsOnly o quando si assegna la modalità SfbWithTeamsCollabAndMeetings.  

Il diagramma seguente mostra le fasi concettuali dell'aggiornamento delle funzionalità di selezione per un'organizzazione senza l'utilizzo preventivo di teams. L'altezza delle barre rappresenta il numero di utenti. Durante qualsiasi fase dell'aggiornamento, tutti gli utenti possono comunicare tra loro.  Gli utenti di Skype for business comunicano con gli utenti di TeamsOnly con l'interoperabilità e viceversa. Gli utenti in modalità isole devono assicurarsi di eseguire entrambi i client.

![Diagramma che mostra l'aggiornamento delle funzionalità di selezione senza un uso preventivo dei team](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Aggiornamento delle funzionalità di selezione per un'organizzazione che usa già teams in modalità Islands

Se alcuni utenti dell'organizzazione usano attivamente team in modalità isole, probabilmente non si vuole rimuovere la funzionalità dagli utenti esistenti. È pertanto necessario un passaggio aggiuntivo prima di modificare il criterio a livello di tenant. La soluzione consiste nel "nonno" di questi utenti di team attivi esistenti in modalità isole, prima di impostare i criteri a livello di tenant su SfbWithTeamsCollab.  Dopo aver eseguito questa operazione, è possibile procedere con la distribuzione come sopra, ma si avranno due gruppi di utenti che si spostano in TeamsOnly: gli utenti che erano attivi in teams saranno in modalità Islands e gli utenti rimanenti saranno in modalità SfbWithTeamsCollab. Puoi trasferire progressivamente questi utenti in modalità TeamsOnly.

1. Trovare gli utenti attivi in teams come indicato di seguito:

   1. Nell'interfaccia di amministrazione di Microsoft 365, nella barra di spostamento sinistra, vai a report e quindi utilizzo. 
   2. Nell'elenco a discesa "Seleziona un report" scegliere Microsoft teams e quindi attività utente. Verrà fornito un tavolo esportabile di utenti attivi in teams. 
   3. Fare clic su Esporta, Apri Excel e filtra per visualizzare solo gli utenti attivi in teams.

2. Per ogni utente di team attivi che si trova nel passaggio 1, assegnare la modalità isole in PowerShell remoto. In questo modo è possibile passare al passaggio successivo e verificare che l'esperienza utente non venga modificata.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Impostare i criteri a livello di tenant su SfbWithTeamsCollab:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Aggiornare gli utenti selezionati alla modalità TeamsOnly. È possibile scegliere di aggiornare gli utenti in modalità isole o in modalità SfbWithTeamsCollab, anche se è consigliabile assegnare priorità all'aggiornamento degli utenti in modalità isole per ridurre al minimo le potenzialità di confusione che possono verificarsi quando gli utenti si trovano in modalità isole.   

   Per gli utenti residenti in Skype for business online:  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Per gli utenti residenti in Skype for Business Server locale:  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

Il diagramma seguente mostra le fasi concettuali di una transizione di funzionalità di selezione in cui ci sono utenti di isole attive all'inizio. L'altezza delle barre rappresenta il numero di utenti. Durante qualsiasi fase dell'aggiornamento, tutti gli utenti possono comunicare tra loro.  Gli utenti di Skype for business comunicano con gli utenti di TeamsOnly con l'interoperabilità e viceversa. 


![Diagramma che mostra l'aggiornamento delle funzionalità di selezione con gli utenti attivi in modalità Isole](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>Collegamenti correlati

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio di migrazione delle riunioni (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

