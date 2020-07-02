---
title: Gestire teams con Microsoft teams PowerShell
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
description: Informazioni su come gestire Microsoft teams con teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c217cea4a9ad800c1f31f8dcfae9c88ee281188c
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944127"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Gestire teams con Microsoft teams PowerShell

Questo articolo illustra come usare Microsoft teams PowerShell per gestire team e Skype for business. 

Usare queste linee guida in combinazione con il riferimento ai cmdlet [Microsoft teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps) e i [riferimenti ai cmdlet di Skype for business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

## <a name="create-and-manage-teams-using-powershell"></a>Creare e gestire teams tramite PowerShell

I cmdlet per la creazione e la gestione dei team si trovano nel [modulo PowerShell di Microsoft teams](https://www.powershellgallery.com/packages/MicrosoftTeams/).

I team sono supportate da gruppi di Office 365, quindi quando crei un team crei un gruppo. Sono disponibili un set di cmdlet per l'uso del team di base e delle relative impostazioni ( ``new-team`` , ``get-team`` ,, ``set-team`` ), la gestione degli utenti del team ( ``add-teamuser`` ,) e i ``remove-teamuser`` cmdlet per la gestione dei canali del team ( ``new-teamchannel`` , ``remove-teamchannel`` ). Tutti questi cmdlet possono essere eseguiti come utenti finali, ma lavoreranno solo sui team di cui si è proprietari o membri. Gli amministratori globali o gli amministratori del servizio teams saranno in grado di agire in tutti i team dell'organizzazione.

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department
```

> Il **GroupID** usato nei cmdlet del modulo di PowerShell per Microsoft teams è uguale alla proprietà **Identity** restituita dal ``Get-UnifiedGroup`` modulo di PowerShell di Exchange.

## <a name="manage-policies-via-powershell"></a>Gestire i criteri tramite PowerShell

> [!NOTE]
> - Il connettore di Skype for business online viene consolidato in teams PowerShell. È attualmente disponibile in anteprima pubblica. In tempo, i cmdlet di Skype for business online che si applicano ai team saranno disponibili nativamente nel modulo di PowerShell teams. I passaggi di installazione sono disponibili nell'articolo [Install teams PowerShell](teams-powershell-install.md) .
>
> - I cmdlet saranno disponibili nella sessione di PowerShell quando ci si connette a Skype for business online. Per altre informazioni, vedere [gestire Skype for business online con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Trovare i cmdlet per la gestione dei criteri nel [modulo cmdlet di Skype for business](https://www.microsoft.com/download/details.aspx?id=39366).

Un criterio è un gruppo di impostazioni che possono essere applicate in maniera granulare ai singoli utenti. Ogni tipo di criterio ha un proprio set di cmdlet per la creazione, la visualizzazione, l'eliminazione e l'aggiornamento dei criteri stessi e quindi l'assegnazione di tali criteri agli utenti. La struttura generale è:

- **Get** Commands (ad esempio, ``Get-CsTeamsMeetingPolicy`` ): restituisce i documenti dei criteri disponibili per l'assegnazione nell'organizzazione, inclusi i criteri creati da Microsoft per l'uso e i criteri personalizzati creati.
   - Per trovare solo i criteri personalizzati creati nell'organizzazione, USA ``-Filter "tag:*"`` .

- **Nuovi** comandi (ad esempio, ``New-CsTeamsMeetingPolicy`` ): crea nuovi criteri per l'organizzazione da assegnare agli utenti dell'organizzazione. Non tutti i criteri supportano la creazione di criteri personalizzati. Spesso si tratta di verificare che i criteri usati nell'organizzazione dispongano di una combinazione di impostazioni supportata.

- **Imposta comandi (** ad esempio ``Set-CsTeamsMeetingPolicy`` ): imposta valori specifici per un determinato criterio. In alcuni criteri non sono disponibili comandi impostati oppure contengono parametri che non possono essere personalizzati nel criterio. Le descrizioni di PowerShell indicano i parametri che non è possibile personalizzare. 
   - Per modificare i criteri che verranno assegnati per impostazione predefinita agli utenti dell'organizzazione che non dispongono di un criterio personalizzato assegnato, Esegui ``Set-Cs<PolicyName> -Identity Global`` .

- **Rimuovi** comandi (ad esempio, ``Remove-CsTeamsMeetingPolicy`` ): Elimina un criterio personalizzato creato nel tenant. Se si eliminano i criteri personalizzati assegnati ad almeno un utente dell'organizzazione, l'utente ritornerà al criterio globale.
   - Non è possibile rimuovere effettivamente il criterio globale nell'organizzazione, ma se si vuole reimpostare il criterio globale dell'organizzazione sulle impostazioni predefinite fornite da Microsoft, eseguire ``Remove-Cs<PolicyName> -Identity Global`` .

- Comando **Concedi** (ad esempio, ``Grant-CsTeamsMeetingPolicy`` ): assegna un criterio a un utente specifico.
   - Per rimuovere un'assegnazione di criteri personalizzata e far rientrare l'utente nei criteri predefiniti dell'organizzazione, eseguire ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` .

> [!TIP]
> Non tutti i criteri consentono la creazione di criteri personalizzati e alcuni criteri hanno impostazioni che non è possibile personalizzare (in modo che sia possibile visualizzare l'impostazione ma non impostare un valore personalizzato durante ``set-`` e ``new-`` ). La documentazione per ogni cmdlet chiama se i parametri sono disponibili per l'uso da parte dei clienti.

Parametri comuni:

- **Identity**: for ``Get-`` , ``Set-`` , ``New-`` e ``Remove-`` , il parametro **Identity** farà sempre riferimento a una specifica istanza di criteri. Per ``Grant`` il parametro **Identity** fa riferimento a un oggetto utente specifico a cui è applicato il criterio.

## <a name="manage-configurations-via-powershell"></a>Gestire le configurazioni tramite PowerShell

Trovare i cmdlet per la gestione della configurazione nel [modulo cmdlet di Skype for business](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Le configurazioni sono contenitori di impostazioni gestite nel servizio che non è possibile specificare a livello di utente. Le impostazioni vengono sempre applicate in tutta l'organizzazione. La configurazione globale è l'unica configurazione efficace dell'organizzazione. Ogni tipo di configurazione include due cmdlet principali:

- ``Get-Cs<ConfigurationName>``(ad esempio, ``Get-CsTeamsClientConfiguration`` ):

- IMPOSTA comandi (ad esempio, ``Set-CsTeamsClientConfiguration`` ): imposta le proprietà nella configurazione di quel tipo. Specificare i parametri che si desidera modificare.
   > È possibile fare riferimento alla configurazione che si sta modificando in uno dei due modi seguenti: specificando-**Identity global**oppure eseguendo ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` .

## <a name="what-can-each-admin-role-do"></a>Cosa può fare ogni ruolo di amministratore?

Leggere [usare i ruoli di amministratore di Microsoft teams per gestire i team](using-admin-roles.md) per capire quali ruoli di amministratore possono eseguire ogni cmdlet di PowerShell.

## <a name="related-topics"></a>Argomenti correlati

[Installazione di PowerShell per Teams](teams-powershell-install.md)

[Note sulla versione di PowerShell per Teams](teams-powershell-release-notes.md)

[Informazioni di riferimento sui cmdlet Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Informazioni di riferimento sui cmdlet di Skype for business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Usare i ruoli di amministratore per gestire Teams](using-admin-roles.md)