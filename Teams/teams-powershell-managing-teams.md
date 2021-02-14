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
description: Informazioni su come gestire Microsoft Teams con Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 09d11b2c697ba57ea161d0ce961cf5ba73794617
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852177"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Gestire Teams con Microsoft Teams PowerShell

Questo articolo illustra come usare Microsoft Teams PowerShell per gestire Teams e Skype for Business. 

Usare queste indicazioni insieme al riferimento ai [cmdlet di Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps) e ai cmdlet di Skype for [Business.](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

## <a name="create-and-manage-teams-using-powershell"></a>Creare e gestire team con PowerShell

I cmdlet per la creazione e la gestione dei team sono disponibili nel [modulo Microsoft Teams PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams/)

I team sono supportati da Gruppi di Office 365, quindi quando crei un team crei un gruppo. Sono disponibili set di cmdlet per l'uso nel team di base e nelle relative impostazioni (, , ), per la gestione degli utenti del team ( , ), nonché per la gestione dei canali del ``new-team`` ``get-team`` team ( ,  ``set-team`` ``add-teamuser`` ``remove-teamuser`` ``new-teamchannel`` ``remove-teamchannel`` ). Tutti questi cmdlet possono essere eseguiti come utenti finali, ma funzioneranno solo sui team di cui si è proprietari o di cui si è membri. Gli amministratori globali o gli amministratori dei servizi di Teams possono agire su tutti i team dell'organizzazione.

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> Il **valore GroupId** usato nei cmdlet del modulo di Microsoft Teams PowerShell è uguale alla proprietà **Identity** restituita dal ``Get-UnifiedGroup`` modulo PowerShell di Exchange.

## <a name="manage-policies-via-powershell"></a>Gestire i criteri con PowerShell

> [!NOTE]
> - Skype for Business Online Connector è in fase di consolidamento in PowerShell di Teams. Al momento è disponibile in anteprima pubblica. In tempo, i cmdlet di Skype for Business online applicabili a Teams saranno disponibili a livello nativo nel modulo PowerShell di Teams. I passaggi per l'installazione sono disponibili [nell'articolo installare Teams PowerShell.](teams-powershell-install.md)
>
> - I cmdlet saranno disponibili nella sessione di PowerShell dopo la connessione a Skype for Business online. Per ulteriori informazioni, consulta [Gestire Skype for Business online con PowerShell di Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Trova i cmdlet per la gestione dei criteri nel modulo [cmdlet di Skype for Business.](https://www.microsoft.com/download/details.aspx?id=39366)

Un criterio è un gruppo di impostazioni che può essere applicato in modo capillare a singoli utenti. Ogni tipo di criterio ha un proprio set di cmdlet per creare, visualizzare, eliminare e aggiornare i criteri e quindi assegnarli agli utenti. La struttura generale è:

- **Comandi** GET (ad esempio, ): restituisce i documenti dei criteri che possono essere assegnati all'utente nell'organizzazione, inclusi i criteri creati da Microsoft per l'uso, nonché i criteri personalizzati ``Get-CsTeamsMeetingPolicy`` creati.
   - Per trovare solo i criteri personalizzati creati nell'organizzazione, usare ``-Filter "tag:*"`` .

- **NUOVI** comandi (ad esempio, ``New-CsTeamsMeetingPolicy`` ): Crea nuovi criteri per l'organizzazione da assegnare agli utenti dell'organizzazione. Non tutti i criteri supportano la creazione di criteri personalizzati. In genere questo assicura che i criteri che usi nell'organizzazione hanno una combinazione di impostazioni supportata.

- **Comandi SET** (ad esempio): ``Set-CsTeamsMeetingPolicy`` imposta valori specifici in un determinato criterio. Alcuni criteri non hanno comandi SET disponibili o contengono parametri che non possono essere personalizzati nei criteri. Le descrizioni di PowerShell specificano quali parametri non possono essere personalizzati. 
   - Per modificare il criterio che verrà assegnato per impostazione predefinita agli utenti dell'organizzazione a cui non è assegnato un criterio personalizzato, eseguire ``Set-Cs<PolicyName> -Identity Global`` .

- **Comandi** REMOVE (ad esempio, ): Elimina un criterio personalizzato creato ``Remove-CsTeamsMeetingPolicy`` nel tenant. Se si eliminano criteri personalizzati assegnati ad almeno un utente dell'organizzazione, l'utente torna ai criteri globali.
   - Non è possibile rimuovere effettivamente i criteri globali nell'organizzazione, ma se si vogliono reimpostare i criteri globali dell'organizzazione alle impostazioni predefinite fornite da Microsoft, eseguire ``Remove-Cs<PolicyName> -Identity Global`` .

- **Comando GRANT** (ad esempio): ``Grant-CsTeamsMeetingPolicy`` assegna un criterio a un utente specifico.
   - Per rimuovere un'assegnazione di criteri personalizzata e fare in modo che l'utente torni ai criteri predefiniti dell'organizzazione, eseguire ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` .

> [!TIP]
> Non tutti i criteri consentono la creazione di criteri personalizzati e alcuni criteri hanno impostazioni che non è possibile personalizzare, quindi è possibile visualizzare l'impostazione ma non impostare un valore personalizzato durante e ``set-`` ``new-`` . La documentazione di ogni cmdlet indica se i parametri sono disponibili per l'uso da parte dei clienti.

Parametri comuni:

- **Identity:** ``Get-`` per, ``Set-`` , e , il parametro ``New-`` Identity fa sempre riferimento a una specifica istanza di ``Remove-`` criteri.  Per , il parametro Identity fa riferimento a un oggetto utente specifico ``Grant`` a cui viene applicato il criterio. 

## <a name="manage-configurations-via-powershell"></a>Gestire le configurazioni con PowerShell

Trova i cmdlet per la gestione della configurazione nel modulo [cmdlet di Skype for Business.](https://www.microsoft.com/en-us/download/details.aspx?id=39366)

Le configurazioni sono contenitori di impostazioni gestiti nel servizio che non possono essere specificati a livello di utente. Le impostazioni vengono sempre applicate all'intera organizzazione. La configurazione globale è l'unica configurazione efficace nell'organizzazione. Ogni tipo di configurazione include due cmdlet principali:

- ``Get-Cs<ConfigurationName>`` (ad ``Get-CsTeamsClientConfiguration`` esempio):

- Comandi SET( ad ``Set-CsTeamsClientConfiguration`` esempio): impostare le proprietà nella configurazione di quel tipo. Specificare i parametri da modificare.
   > È possibile fare riferimento alla configurazione da modificare in due modi: specificando Identity **Global** oppure eseguendo ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` .

## <a name="what-can-each-admin-role-do"></a>Cosa può fare ogni ruolo di amministratore?

Leggere [Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](using-admin-roles.md) e capire quali ruoli di amministratore possono eseguire ogni cmdlet di PowerShell.

## <a name="related-topics"></a>Argomenti correlati

[Installazione di Teams PowerShell](teams-powershell-install.md)

[Note sulla versione di PowerShell in Teams](teams-powershell-release-notes.md)

[Informazioni di riferimento per i cmdlet di Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Informazioni di riferimento per i cmdlet di Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Usare i ruoli di amministratore per gestire Teams](using-admin-roles.md)
