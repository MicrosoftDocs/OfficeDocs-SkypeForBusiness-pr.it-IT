---
title: Gestire l'accesso degli utenti a Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Informazioni su come gestire l'accesso degli utenti ai team assegnando o rimuovendo una licenza di teams agli utenti dell'organizzazione.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d877a4c6534c76b894583401dc5dba0936c3c75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521383"
---
# <a name="manage-user-access-to-teams"></a>Gestire l'accesso degli utenti a Teams

Puoi gestire l'accesso ai team a livello di utente assegnando o rimuovendo una licenza di prodotto Microsoft teams. Ogni utente dell'organizzazione deve avere una licenza di teams prima di poter usare teams. È possibile assegnare una licenza di teams per i nuovi utenti quando vengono creati nuovi account utente o per gli utenti con account esistenti.

Per impostazione predefinita, quando un piano di licenza (ad esempio Microsoft 365 Enterprise E3 o Microsoft 365 Business Premium) viene assegnato a un utente, viene automaticamente assegnata una licenza di teams e l'utente è abilitato per Teams. Puoi disabilitare o abilitare team per un utente rimuovendo o assegnando una licenza in qualsiasi momento.

Usare i criteri di messaggistica, gestiti dall'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di teams</a>, per controllare quali funzionalità di messaggistica chat e canali sono disponibili per gli utenti in teams. È possibile usare i criteri predefiniti o creare uno o più criteri di messaggistica personalizzati per gli utenti dell'organizzazione. Per altre informazioni, leggere [gestire i criteri di messaggistica in teams](messaging-policies-in-teams.md).
È possibile gestire le licenze teams nell'interfaccia di amministrazione di Microsoft 365 o tramite PowerShell. Per gestire le licenze, è necessario essere un amministratore globale o un amministratore di gestione utenti.

> [!NOTE]
> Ti consigliamo di abilitare teams per tutti gli utenti in modo che i team possano essere formati organicamente per progetti e altre iniziative dinamiche. Anche se si sta usando un pilota, può essere comunque utile conservare i team abilitati per tutti gli utenti, ma solo le comunicazioni di destinazione per il gruppo di utenti pilota.

## <a name="using-the-microsoft-365-admin-center"></a>Uso dell'interfaccia di amministrazione di Microsoft 365

Le licenze a livello di utente di teams vengono gestite direttamente tramite le interfacce di gestione degli utenti di Microsoft 365. Un amministratore può assegnare licenze ai nuovi utenti quando vengono creati nuovi account utente o per gli utenti con account esistenti. 

> [!IMPORTANT]
> Per gestire le licenze di Microsoft teams, l'amministratore deve avere i privilegi di amministratore globale o gestione utenti.
Usare l'interfaccia di amministrazione di Microsoft 365 per gestire le licenze di team per singoli utenti o piccoli set di utenti alla volta. È possibile gestire le licenze per i team nella pagina **licenze** (per un massimo di 20 utenti alla volta) o nella pagina **utenti attivi** . Il metodo scelto varia a seconda che si vogliano gestire le licenze di prodotto per utenti specifici o gestire le licenze utente per prodotti specifici.

Se è necessario gestire le licenze per i team per un numero elevato di utenti, ad esempio centinaia o migliaia di utenti, [usare PowerShell](#using-powershell) o le [licenze basate su gruppo in Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign). 

### <a name="assign-a-teams-license"></a>Assegnare una licenza per Teams

La procedura è diversa a seconda che si usi la pagina **licenze** o **gli utenti attivi** .  Per istruzioni dettagliate, vedere [assegnare licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

|||
|---------|---------|
|![Screenshot della licenza teams abilitata per un utente](media/assign-teams-licenses-1.png)    | ![Screenshot della licenza teams abilitata per un utente](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Rimuovere una licenza per Teams

Quando si rimuove una licenza di Teams da un utente, i team sono disabilitati per l'utente e non vedranno più i team nell'icona di avvio delle app o nella Home page. Per la procedura dettagliata, vedere [annullare l'assegnazione di licenze dagli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).

|||
|---------|---------|
|![Screenshot della licenza per i team disabilitata per un utente](media/remove-teams-licenses-1.png)    | ![Screenshot della licenza per i team disabilitata per un utente](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Utilizzo di PowerShell

Usare PowerShell per gestire le licenze per i team per gli utenti in blocco. Puoi abilitare e disabilitare teams tramite PowerShell nello stesso modo in cui vuoi per qualsiasi altra licenza per il piano di servizio. Sono necessari gli identificatori per i piani di servizio per i team, che sono i seguenti:

- Microsoft teams: TEAMS1
- Microsoft teams per GCC: TEAMS_GOV
- Microsoft teams per DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Assegnare licenze teams in blocco

Per la procedura dettagliata, vedere [assegnare licenze agli account utente con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="remove-teams-licenses-in-bulk"></a>Rimuovere le licenze teams in blocco

Per la procedura dettagliata, vedere [disabilitare l'accesso ai servizi con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) e [disabilitare l'accesso ai servizi durante l'assegnazione di licenze utente](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

#### <a name="example"></a>Esempio 

Di seguito è riportato un esempio di come usare i cmdlet [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) e [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) per disabilitare i team per gli utenti con un piano di licenze specifico. Ad esempio, seguire questa procedura per disabilitare prima i team per tutti gli utenti che hanno un particolare piano di licenze. Quindi Abilita teams per ogni singolo utente che dovrebbe avere accesso a teams.

> [!IMPORTANT]
> Il cmdlet [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) consentirà di abilitare tutti i servizi precedentemente disabilitati, a meno che non siano stati identificati esplicitamente nello script personalizzato. Ad esempio, se vuoi abbandonare sia Exchange che Sway disabled mentre disabilitano anche i team, dovrai includere questo nello script o sia Exchange che Sway saranno abilitati per gli utenti che hai identificato.

Eseguire il comando seguente per visualizzare tutti i piani di licenze disponibili nell'organizzazione. Per altre informazioni, vedere [visualizzare licenze e servizi con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).

      Get-MsolAccountSku

Eseguire i comandi seguenti, dove \<CompanyName:License> si trova il nome dell'organizzazione e l'identificatore per il piano di licenza recuperato nel passaggio precedente. Ad esempio, ContosoSchool: ENTERPRISEPACK_STUDENT.

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

Eseguire il comando seguente per disabilitare team per tutti gli utenti che hanno una licenza attiva per il piano di licenza.

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a>Gestire team a livello di organizzazione

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a>Argomenti correlati

- [Licenze per i componenti aggiuntivi Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Assegnare licenze per il componente aggiuntivo Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Visualizzare licenze e servizi con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nomi dei prodotti e identificatori dei piani di servizio per le licenze](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Riferimento SKU per l'istruzione](sku-reference-edu.md)