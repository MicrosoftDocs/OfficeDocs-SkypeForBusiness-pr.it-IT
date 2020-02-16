---
title: Panoramica di PowerShell Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
description: Informazioni su come usare i controlli di PowerShell per la gestione di Microsoft teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5eaf04a0244e35e7d9f7deb7d8afb135b3acb2c
ms.sourcegitcommit: c8d16d5e61d66d7b5e7391a800978b920612ea4d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42052523"
---
# <a name="teams-powershell-overview"></a>Panoramica di PowerShell Teams

Microsoft teams include un ricco set di strumenti per gli amministratori IT che gestiscono il prodotto tramite l'interfaccia di amministrazione di Microsoft teams, i controlli di PowerShell e le API del grafico. Questa guida illustra come strutturare i cmdlet di PowerShell per gli amministratori IT da usare e fornisce puntatori a ulteriori documentazioni. Tieni presente che i diversi ruoli di amministratore di teams hanno accesso a cmdlet diversi. Per altre informazioni, vedere [usare i ruoli di amministratore di Microsoft teams per gestire i team](using-admin-roles.md).

## <a name="which-modules-do-you-need-to-use"></a>Quali moduli è necessario usare?

I controlli di PowerShell per la gestione dei team si trovano in due diversi moduli di PowerShell: 
- [Modulo di PowerShell per Microsoft teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) : il modulo di PowerShell teams contiene tutti i cmdlet necessari per creare e gestire team.  
- [Modulo di PowerShell per Skype for business](https://www.microsoft.com/download/details.aspx?id=39366): il modulo di PowerShell per Skype for business contiene i cmdlet per la gestione di criteri, configurazioni e altri strumenti teams. 

La documentazione di riferimento per i controlli di PowerShell indica il modulo contenente il cmdlet che si sta esaminando. (Alla fine i due moduli verranno combinati.)

## <a name="what-can-each-admin-role-do"></a>Cosa può fare ogni ruolo di amministratore?

Leggere [usare i ruoli di amministratore di Microsoft teams per gestire i team](using-admin-roles.md) per comprendere quali cmdlet di PowerShell diversi ruoli di amministratore saranno in grado di sfruttare.

## <a name="creating-and-managing-teams-via-powershell"></a>Creazione e gestione di team tramite PowerShell

I cmdlet per la creazione e la gestione dei team si trovano nel [modulo PowerShell di Microsoft teams](https://www.powershellgallery.com/packages/MicrosoftTeams/). 

I team sono supportate da gruppi di Office 365, quindi quando crei un team crei un gruppo. Sono disponibili un set di cmdlet per l'uso del team di base e delle relative impostazioni (``new-team``, ``get-team``, ``set-team``,), la gestione degli``add-teamuser``utenti ``remove-teamuser``del team (,) e i cmdlet per la gestione dei canali del team``new-teamchannel``( ``remove-teamchannel``,). Tutti questi cmdlet possono essere eseguiti come utenti finali, ma lavoreranno solo sui team di cui si è proprietari o membri. Gli amministratori globali o gli amministratori del servizio teams saranno in grado di agire in tutti i team dell'organizzazione.

> Il **GroupID** usato nei cmdlet del modulo di PowerShell per Microsoft teams è uguale alla proprietà **Identity** restituita ``Get-UnifiedGroup`` dal modulo di PowerShell di Exchange.

### <a name="differences-between-preview-and-generally-available-microsoft-teams-powershell-module"></a>Differenze tra l'anteprima e il modulo di PowerShell Microsoft teams disponibile in generale

Quando è stata rilasciata la versione generalmente disponibile del modulo di PowerShell, alcuni cmdlet sono rimasti nel modulo beta-only, come descritto nella tabella seguente.

| Cmdlet | Disponibile in anteprima | Disponibile in 1,0 |
|------- | -------------------- | ------------------------------ |
| Add-TeamUser | Sì | Sì |
| Connect-MicrosoftTeams | Sì | Sì |
| Disconnetti-MicrosoftTeams | Sì | Sì |
| Get-team | Sì | Sì |
| Get-TeamChannel | Sì | Sì |
| Get-TeamFunSettings | Prima della versione di 1,0 | No |
| Get-TeamGuestSettings | Prima della versione di 1,0 | No |
| Get-TeamHelp | Sì | Sì |
| Get-TeamMemberSettings | Prima della versione di 1,0 | No |
| Get-TeamMessagingSettings | Prima della versione di 1,0 | No |
| Get-TeamUser | Sì | Sì |
| Nuovo team | Sì | Sì |
| New-TeamChannel | Sì | Sì |
| Rimuovi-Team | Sì | Sì |
| Remove-TeamChannel | Sì | Sì |
| Remove-TeamUser | Sì | Sì |
| Set-Team | Sì | Sì |
| Set-TeamChannel | Sì | Sì |
| Set-TeamFunSettings | Prima della versione di 1,0 | No |
| Set-TeamGuestSettings | Prima della versione di 1,0 | No |
| Set-TeamMemberSettings | Prima della versione di 1,0 | No |
| Set-TeamMessagingSettings | Prima della versione di 1,0 | No |
| Set-TeamPicture | Sì | No, pianificato |


## <a name="managing-policies-via-powershell"></a>Gestione dei criteri tramite PowerShell

Usare i cmdlet nel [modulo cmdlet di Skype for business](https://www.microsoft.com/download/details.aspx?id=39366) per gestire i criteri per singoli utenti.

> [!NOTE]
> I cmdlet saranno disponibili nella sessione di PowerShell quando ci si connette a Skype for business online. Per altre informazioni, vedere [gestire Skype for business online con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell). 

Un criterio è un gruppo di impostazioni che possono essere applicate in maniera granulare ai singoli utenti. Ogni tipo di criterio ha un proprio set di cmdlet per la creazione, la visualizzazione, l'eliminazione e l'aggiornamento dei criteri stessi e quindi l'assegnazione di tali criteri agli utenti. La struttura generale è:

- OTTENERE i comandi (ad esempio ``Get-CsTeamsMeetingPolicy``,): restituire i documenti dei criteri disponibili per l'assegnazione nell'organizzazione, i criteri creati da Microsoft per l'uso e i criteri personalizzati creati.
   > Se si vogliono trovare solo i criteri personalizzati creati nell'organizzazione, è possibile usarli ``-Filter "tag:*"``.

- NUOVI comandi (ad esempio, ``New-CsTeamsMeetingPolicy``): consentono di creare nuovi criteri per l'organizzazione che sono quindi disponibili per l'assegnazione agli utenti dell'organizzazione. Non tutti i criteri supportano la creazione di criteri personalizzati. Spesso si tratta di verificare che i criteri usati nell'organizzazione dispongano di una combinazione di impostazioni supportata.

- IMPOSTARE i comandi (ad esempio ``Set-CsTeamsMeetingPolicy``): consente di impostare valori specifici per un determinato criterio. Alcuni criteri non dispongono di comandi impostati o contengono parametri che non possono essere personalizzati nel criterio. Ogni descrizione di PowerShell chiamerà i parametri che non possono essere personalizzati. 
   > Per modificare i criteri che verranno assegnati per impostazione predefinita agli utenti dell'organizzazione che non dispongono di un criterio personalizzato assegnato, Esegui ``Set-Cs<PolicyName> -Identity Global``.

- Rimuovi comandi (ad esempio ``Remove-CsTeamsMeetingPolicy``): puoi usare questo cmdlet per eliminare un criterio personalizzato creato nel tenant. Se si eliminano i criteri personalizzati assegnati ad almeno un utente dell'organizzazione, l'utente ritornerà al criterio globale.
   > In realtà non è possibile rimuovere il criterio globale nell'organizzazione, ma se si vuole reimpostare il criterio globale dell'organizzazione con le impostazioni predefinite fornite da Microsoft, si può eseguire ``Remove-Cs<PolicyName> -Identity Global``.

- Comando Concedi (ad esempio ``Grant-CsTeamsMeetingPolicy``): consente di assegnare un criterio a un determinato utente.
   > Per rimuovere un'assegnazione di criteri personalizzata e far rientrare l'utente nei criteri predefiniti dell'organizzazione, eseguire ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.

> [!TIP]
> Non tutti i criteri consentono la creazione di criteri personalizzati e alcuni criteri hanno impostazioni che non è possibile personalizzare (in modo che sia possibile visualizzare l'impostazione ma non impostare un ``set-`` valore ``new-``personalizzato durante e). La documentazione del cmdlet specifico definirà se i parametri non sono disponibili per i clienti.

Parametri comuni:

- **Identity**: for ``Get-``, ``Set-``, ``New-``e ``Remove-``, il parametro **Identity** farà sempre riferimento a una specifica istanza di criteri. Per ``Grant``il parametro **Identity** fa riferimento a un oggetto utente specifico a cui è applicato il criterio.

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>Gestione delle configurazioni tramite PowerShell

I cmdlet per la gestione della configurazione si trovano nel [modulo cmdlet di Skype for business](https://www.microsoft.com/download/details.aspx?id=39366).

Le configurazioni sono contenitori di impostazioni gestite nel servizio che non è possibile specificare a livello di utente. Le impostazioni vengono sempre applicate in tutta l'organizzazione. La configurazione globale è l'unica configurazione efficace dell'organizzazione. Ogni tipo di configurazione include due cmdlet principali:

- ``Get-Cs<ConfigurationName>``(ad esempio, ``Get-CsTeamsClientConfiguration``): 

- IMPOSTA comandi (ad esempio, ``Set-CsTeamsClientConfiguration``): imposta le proprietà nella configurazione di quel tipo. Specificare i parametri che si desidera modificare.
   > È possibile fare riferimento alla configurazione che si sta modificando in uno dei due modi seguenti: specificando-**Identity global**oppure ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``eseguendo.

## <a name="other-powershell-tools"></a>Altri strumenti di PowerShell

Per informazioni dettagliate su come usare tutti i controlli di PowerShell per la gestione di Microsoft teams e Skype for business, incluse descrizioni dettagliate delle impostazioni di ogni criterio, nella Guida di riferimento ai cmdlet di [Microsoft teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps) e nella Guida [di riferimento a Skype for business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

## <a name="learn-more"></a>Ulteriori informazioni

- [Informazioni di riferimento sui cmdlet di Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)
- [Informazioni di riferimento sui cmdlet di Skype for business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
- [Usare i ruoli di amministratore di Microsoft teams per gestire Teams](using-admin-roles.md)
