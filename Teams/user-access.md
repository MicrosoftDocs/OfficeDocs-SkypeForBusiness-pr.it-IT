---
title: Gestire l'accesso degli utenti a Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1keywords: ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.reviewer: ritikag
search.appverid: MET150
description: Informazioni su come abilitare o disabilitare l'accesso a livello utente per singolo utente.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26abd2a69bc8097c4f74cbc85435cda4eec00887
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568596"
---
<a name="manage-user-access-to-microsoft-teams"></a>Gestire l'accesso degli utenti a Microsoft Teams
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

A livello di utente, l'accesso a Microsoft teams può essere abilitato o disabilitato per singolo utente assegnando o rimuovendo la licenza per il prodotto Microsoft teams.

Usare i criteri di messaggistica, gestiti dall'interfaccia di amministrazione di teams, per controllare quali funzionalità di messaggistica chat e canali sono disponibili per gli utenti in teams. È possibile usare i criteri predefiniti o creare uno o più criteri di messaggistica personalizzati per gli utenti dell'organizzazione. Per altre informazioni, leggere [gestire i criteri di messaggistica in teams](messaging-policies-in-teams.md).

> [!NOTE]
>Microsoft consiglia di attivare team per tutti gli utenti di un'azienda in modo che i team possano essere formati organicamente per progetti e altre iniziative dinamiche. Anche se decidi di pilotarlo, potrebbe essere comunque utile conservare i team abilitati per tutti gli utenti, ma solo le comunicazioni di destinazione per il gruppo di utenti pilota.

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a>Gestire i team tramite l'interfaccia di amministrazione di Microsoft 365

Le licenze a livello di utente di teams vengono gestite direttamente tramite le interfacce di gestione degli utenti di Microsoft 365. Un amministratore può assegnare licenze ai nuovi utenti quando vengono creati nuovi account utente o per gli utenti con account esistenti. Per gestire le licenze di Microsoft teams, l'amministratore deve disporre dei privilegi di amministratore globale o amministratore di Office 365.

Quando a un utente viene assegnata una licenza SKU come E3 o E5, viene automaticamente assegnata una licenza di Microsoft teams e l'utente è abilitato per Microsoft teams. Gli amministratori possono avere un controllo granulare su tutti i servizi e le licenze di Office 365 e la licenza di Microsoft teams per un utente specifico o un gruppo di utenti può essere abilitata o disabilitata.

![Screenshot della sezione licenze di prodotto nell'interfaccia di amministrazione.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Una licenza per gli utenti di teams può essere disabilitata in qualsiasi momento. Quando la licenza è disabilitata, gli utenti accedono a Microsoft teams verranno impediti e l'utente non sarà più in grado di visualizzare i team nell'icona di avvio delle app di Office 365 e nella Home page.

![Screenshot che mostra i team selezionati nella sezione licenze di prodotto.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>Gestire tramite PowerShell

> [!IMPORTANT]
> New-MsolLicenseOptions consentirà di abilitare tutti i servizi precedentemente disabilitati, a meno che explictitly non abbia una identità nello script personalizzato. Ad esempio, se si vuole abbandonare entrambi gli Exchange & Sway disabilitati durante la disattivazione dei team di Additonally, è necessario inlcude nello script o entrambi gli Exchange & Sway verranno abilitati per gli utenti identificati. Se si vuole usare una GUI per gestire questa funzionalità, vedere: [creazione di report e gestione delle licenze di Office 365-assegnazione di autorizzazioni di rimozione in blocco](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)

L'abilitazione e la disabilitazione dei team come licenza per il carico di lavoro tramite PowerShell viene eseguita come qualsiasi altro carico di lavoro. Il nome del piano di servizio è TEAMS1 per Microsoft teams. Per GCC il nome del piano di servizio è TEAMS_GOV. Per GCC High il nome del piano di servizio è TEAMS_GCCHIGH. Per DoD il nome del piano di servizio è TEAMS_DOD (vedere [disabilitare l'accesso ai servizi con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) per altre informazioni).

**Esempio:** Di seguito è riportato un semplice esempio di come disabilitare i team per tutti gli utenti in un determinato tipo di licenza. Prima di tutto è necessario eseguire questa operazione, quindi abilitarla individualmente per gli utenti che devono avere accesso per scopi di pilotaggio.

Per visualizzare i tipi di abbonamento presenti all'interno dell'organizzazione, usare il comando seguente:

      Get-MsolAccountSku

Immettere il nome del piano che include il nome dell'organizzazione e il piano per l'Istituto di istruzione (ad esempio ContosoSchool: ENTERPRISEPACK_STUDENT), quindi eseguire i comandi seguenti:

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
Per disabilitare team per tutti gli utenti con una licenza attiva per il piano denominato, eseguire il comando seguente:

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Icona che rappresenta un punto decisionale](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |Punto decisionale         |<ul><li>Qual è il piano dell'organizzazione per i team onboard in tutta l'organizzazione?  (Pilot o Open)</li></ul>         |
|![Icona che rappresenta i passaggi successivi](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Operazioni successive         |<ul><li>Se si esegue l'onboarding tramite un pilota chiuso, decidere se si vuole farlo tramite licenze o comunicazioni mirate.</li><li>A seconda della decisione, eseguire la procedura per assicurarsi che solo gli utenti pilota autorizzati ad accedere ai team (se necessario).</li><li>Documentare le linee guida per cui gli utenti (o meno) avranno accesso a teams.</li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a>Gestire Teams a livello di tenant di Office 365
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

