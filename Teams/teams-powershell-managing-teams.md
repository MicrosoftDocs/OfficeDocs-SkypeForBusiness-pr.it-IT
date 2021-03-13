---
title: Gestire Teams con Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni su come gestire Microsoft Teams usando Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4200c23f6320e67781353e62363d588c230fceb7
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756158"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Gestire Teams con Microsoft Teams PowerShell

Questo articolo illustra come usare Microsoft Teams PowerShell per gestire Teams e Skype for Business. 

Usare queste indicazioni in combinazione con il riferimento [al cmdlet di Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps) e il riferimento ai cmdlet di Skype for [Business.](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

## <a name="create-and-manage-teams-using-powershell"></a>Creare e gestire team con PowerShell

I cmdlet per la creazione e la gestione dei team sono disponibili nel [modulo di PowerShell di Microsoft Teams.](https://www.powershellgallery.com/packages/MicrosoftTeams/)

Teams è supportato da Gruppi di Office 365, quindi quando si crea un team si crea un gruppo. Sono disponibili un set di cmdlet per il funzionamento nel team di base e le relative impostazioni ( , , ), la gestione degli utenti del team ( , ), nonché i cmdlet per la gestione dei canali ``new-team`` del team ( , ``get-team``  ``set-team`` ``add-teamuser`` ``remove-teamuser`` ``new-teamchannel`` ``remove-teamchannel`` ). Tutti questi cmdlet possono essere eseguiti come utenti finali, ma funzionano solo nei team di cui si è proprietari o di cui si è membri. Gli amministratori globali o gli amministratori dei servizi di Teams possono agire su tutti i team dell'organizzazione.

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> Il **Valore GroupId** usato nei cmdlet del modulo di PowerShell di Microsoft Teams è uguale alla proprietà **Identity** restituita da nel modulo ``Get-UnifiedGroup`` di PowerShell di Exchange.

## <a name="manage-policies-via-powershell"></a>Gestire i criteri tramite PowerShell

> [!NOTE]
> - Skype for Business Online Connector è in fase di consolidamento in Teams PowerShell. Attualmente è disponibile in anteprima pubblica. Nel tempo, i cmdlet di Skype for Business Online che si applicano a Teams saranno disponibili in modo nativo nel modulo di PowerShell di Teams. I passaggi per l'installazione sono disponibili [nell'articolo installare Teams PowerShell.](teams-powershell-install.md)
>
> - I cmdlet saranno disponibili nella sessione di PowerShell dopo la connessione a Skype for Business online. Per altre informazioni, vedere [Gestire Skype for Business online con PowerShell di Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Trovare i cmdlet per la gestione dei criteri nel [modulo cmdlet di Skype for Business.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

Un criterio è un gruppo di impostazioni che possono essere applicate in modo granulare ai singoli utenti. Ogni tipo di criterio ha un proprio set di cmdlet per la creazione, la visualizzazione, l'eliminazione e l'aggiornamento dei criteri stessi e quindi l'assegnazione di tali criteri agli utenti. La struttura generale è:

- **Comandi GET** (ad esempio, ): restituisce i documenti dei criteri disponibili per ``Get-CsTeamsMeetingPolicy`` l'assegnazione all'interno dell'organizzazione, inclusi i criteri creati da Microsoft per l'uso e i criteri personalizzati creati.
   - Per trovare solo i criteri personalizzati creati nell'organizzazione, usare ``-Filter "tag:*"`` .

- **NUOVI** comandi (ad esempio, ``New-CsTeamsMeetingPolicy`` ): crea nuovi criteri per l'organizzazione da assegnare agli utenti dell'organizzazione. Non tutti i criteri supportano la creazione di criteri personalizzati. Spesso si tratta di verificare che i criteri utilizzati nell'organizzazione siano supportati da una combinazione di impostazioni.

- **Comandi SET** ,ad esempio ``Set-CsTeamsMeetingPolicy`` : imposta determinati valori in un determinato criterio. Alcuni criteri non hanno comandi SET disponibili o contengono parametri che non possono essere personalizzati nei criteri. Le descrizioni di PowerShell indicano quali parametri non possono essere personalizzati. 
   - Per modificare i criteri che verranno assegnati per impostazione predefinita agli utenti dell'organizzazione a cui non è assegnato un criterio personalizzato, eseguire ``Set-Cs<PolicyName> -Identity Global`` .

- **Comandi** REMOVE (ad esempio, ): elimina un criterio ``Remove-CsTeamsMeetingPolicy`` personalizzato creato nel tenant. Se si eliminano criteri personalizzati assegnati ad almeno un utente dell'organizzazione, l'utente verrà nuovamente assegnato ai criteri globali.
   - Non è possibile rimuovere effettivamente i criteri globali nell'organizzazione, ma se si vuole reimpostare i criteri globali dell'organizzazione alle impostazioni predefinite fornite da Microsoft, eseguire ``Remove-Cs<PolicyName> -Identity Global`` .

- **Comando GRANT** (ad ``Grant-CsTeamsMeetingPolicy`` esempio): assegna un criterio a un utente specifico.
   - Per rimuovere un'assegnazione di criteri personalizzati e fare in modo che l'utente torni ai criteri predefiniti dell'organizzazione, eseguire ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` .

> [!TIP]
> Non tutti i criteri consentono la creazione di criteri personalizzati e alcuni criteri hanno impostazioni che non è possibile personalizzare, quindi è possibile visualizzare l'impostazione ma non impostare un valore personalizzato durante ``set-`` e ``new-`` . La documentazione di ogni cmdlet indica se i parametri sono disponibili per l'uso da parte dei clienti.

Parametri comuni:

- **Identity:** per , , e , il parametro Identity farà sempre riferimento ``Get-`` ``Set-`` a ``New-`` ``Remove-`` un'istanza specifica dei criteri.  Per , il parametro Identity fa riferimento a un oggetto utente specifico a ``Grant`` cui viene applicato il criterio. 

## <a name="manage-configurations-via-powershell"></a>Gestire le configurazioni tramite PowerShell

Trovare i cmdlet per la gestione della configurazione nel [modulo cmdlet di Skype for Business.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

Le configurazioni sono contenitori di impostazioni gestite nel servizio che non possono essere specificate a livello di utente. Le impostazioni si applicano sempre all'intera organizzazione. La configurazione globale è l'unica configurazione efficace nell'organizzazione. Ogni tipo di configurazione include due cmdlet principali:

- ``Get-Cs<ConfigurationName>`` (ad ``Get-CsTeamsClientConfiguration`` esempio):

- Comandi SET (ad ``Set-CsTeamsClientConfiguration`` esempio, ): impostare le proprietà nella configurazione di quel tipo. Specificare i parametri da modificare.
   > È possibile fare riferimento alla configurazione che si sta modificando in due modi: specificando -**Identity Global** o eseguendo ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` .

## <a name="what-can-each-admin-role-do"></a>Cosa può fare ogni ruolo di amministratore?

Leggere [Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](using-admin-roles.md) per comprendere quali ruoli di amministratore possono eseguire ogni cmdlet di PowerShell.

## <a name="related-topics"></a>Argomenti correlati

[Installazione di Teams PowerShell](teams-powershell-install.md)

[Note sulla versione di PowerShell di Teams](teams-powershell-release-notes.md)

[Informazioni di riferimento sul cmdlet di Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Informazioni di riferimento sul cmdlet di Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Usare i ruoli di amministratore per gestire Teams](using-admin-roles.md)
