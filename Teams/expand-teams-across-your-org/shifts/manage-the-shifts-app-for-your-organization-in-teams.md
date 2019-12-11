---
title: Gestire l'app turni per l'organizzazione in Microsoft Teams
author: kenwith
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come configurare e gestire l'app turni in teams per gli operatori di I FIRSTLINE dell'organizzazione.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6bd65376be278a3d07e5a7a8c4ba69ccd5408090
ms.sourcegitcommit: a23f45ab3a2cb7b5c279356edddf61c4030c41bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "39961611"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gestire l'app turni per l'organizzazione in Microsoft Teams

> [!IMPORTANT]
> Efficace 31 dicembre 2019, Microsoft StaffHub sarà ritirato. Stiamo costruendo funzionalità di StaffHub in Microsoft teams. Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo. StaffHub smetterà di funzionare per tutti gli utenti il 31 dicembre 2019. Chiunque tenti di aprire StaffHub verrà visualizzato un messaggio che li indirizza a scaricare teams. Per altre informazioni, vedere [Microsoft StaffHub per ritirarsi](microsoft-staffhub-to-be-retired.md).  

## <a name="overview-of-shifts"></a>Panoramica dei turni
L'app turni in Microsoft teams mantiene i dipendenti di I FIRSTLINE connessi e sincronizzati. È stato costruito per la prima volta per la gestione e la comunicazione del tempo veloce ed efficace per i team. Turni consente ai dipendenti di I FIRSTLINE e ai loro manager di usare i loro dispositivi mobili per gestire le pianificazioni e tenersi in contatto. 

- I manager creano, aggiornano e gestiscono le pianificazioni di turno per i team. Possono inviare messaggi a una sola persona ("c'è una fuoriuscita sul pavimento") o all'intero team ("il GM regionale arriva in 20 minuti"). Possono anche inviare documenti di policy, notiziari e video. 
- I dipendenti visualizzano i loro turni imminenti, possono vedere chi altro è programmato per il giorno, richiedere di scambiare o offrire un turno e richiedere il tempo libero. 

È importante sapere che i turni attualmente non supportano gli utenti guest. Ciò significa che gli ospiti di un team non possono essere aggiunti o usare le pianificazioni di turni quando l'accesso Guest è attivato in teams. 

## <a name="availability-of-shifts"></a>Disponibilità di turni

Turni è disponibile in tutti gli SKU aziendali in cui è disponibile teams.

## <a name="location-of-shifts-data"></a>Posizione dei dati di turni

Turni i dati sono attualmente archiviati in Azure nei data center in Nord America, Europa occidentale e Asia Pacifico. Per altre informazioni sulla posizione di archiviazione dei dati, vedere [dove sono i dati](http://o365datacentermap.azurewebsites.net/)?

## <a name="set-up-shifts"></a>Configurare turni

### <a name="enable-or-disable-shifts-in-your-organization"></a>Abilitare o disabilitare i turni nell'organizzazione

Turni è abilitato per impostazione predefinita per tutti gli utenti di Teams dell'organizzazione. Puoi disattivare o attivare l'intera organizzazione delle app usando le impostazioni a livello di organizzazione nei criteri di autorizzazione dell'app nell'interfaccia di amministrazione di Microsoft teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai > **criteri di autorizzazione** delle **app teams**.
2. Fare clic su **impostazioni a livello di organizzazione**.
3. Nel pannello **impostazioni a livello di organizzazione** , in **app bloccate**, eseguire una delle operazioni seguenti:

    - Per disattivare i turni per l'organizzazione, cercare l'app turni e fare clic su **Aggiungi** per aggiungerla all'elenco delle app bloccate.
    - Per attivare i turni per l'organizzazione, Rimuovi l'app turni dall'elenco delle app bloccate.
4. Fai clic su **Salva**. 

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Abilitare o disabilitare turni per utenti specifici dell'organizzazione

Per consentire o bloccare gli utenti specifici dell'organizzazione dall'uso di turni, verificare che i turni siano attivati per l'organizzazione in impostazioni a livello di organigramma e quindi creare un criterio di autorizzazione dell'app personalizzato e assegnarlo a tali utenti. Per altre informazioni, vedere [gestire i criteri di autorizzazione delle app in teams](../../teams-app-permission-policies.md).

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Usare i criteri di configurazione dell'app FirstlineWorker per aggiungere i turni ai team

I criteri di configurazione delle app consentono di personalizzare i team per evidenziare le app più importanti per gli utenti dell'organizzazione. Le app impostate in un criterio sono bloccate alla barra&mdash;dell'app la barra sul lato del client desktop teams e nella parte inferiore dei client&mdash;per dispositivi mobili in cui gli utenti possono accedervi in modo rapido e semplice. 
 
Teams include un criterio di configurazione dell'app FirstlineWorker predefinito che puoi assegnare a dipendenti di I FIRSTLINE nell'organizzazione. Per impostazione predefinita, il criterio include le app attività, turni, chat e chiamate. 

Per visualizzare i criteri di FirstlineWorker, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai**criteri di configurazione**dell'app **Teams app** > .

![Screenshot dei criteri di configurazione dell'app FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Screenshot dei criteri di configurazione dell'app FirstlineWorker nell'interfaccia di amministrazione di Microsoft Teams")

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a>Assegnare i criteri di FirstlineWorker a singoli utenti

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**e quindi fai clic sull'utente.
2. Accanto a **criteri assegnati**scegliere **modifica**.
3. In **criteri di configurazione dell'app teams**selezionare **FirstlineWorker**e quindi scegliere **Salva**.

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a>Assegnare i criteri di configurazione dell'app FirstlineWorker agli utenti di un gruppo

Puoi assegnare i criteri di configurazione dell'app FirstlineWorker agli utenti di un gruppo, ad esempio un gruppo di sicurezza, connettendosi al modulo di PowerShell per il grafico di Azure Active Directory e al modulo di PowerShell di Skype for business. Per altre informazioni sull'uso di PowerShell per la gestione dei team, vedere [Cenni preliminari su teams PowerShell](../../teams-powershell-overview.md).

In questo esempio, assegniamo i criteri di configurazione dell'app FirstlineWorker a tutti gli utenti nel gruppo di team Contoso I FIRSTLINE.

> [!NOTE]
> Prima di tutto, assicurati di connetterti a Azure Active Directory PowerShell per modulo grafico e modulo di PowerShell per Skype for business seguendo la procedura descritta in [Connetti a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Ottenere il GroupObjectId del gruppo specifico.
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
Ottenere i membri del gruppo specificato.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Assegna tutti gli utenti del gruppo ai criteri di configurazione dell'app FirstlineWorker.
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.

## <a name="related-topics"></a>Argomenti correlati
- [Sposta la guida per gli operatori di I FIRSTLINE](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
