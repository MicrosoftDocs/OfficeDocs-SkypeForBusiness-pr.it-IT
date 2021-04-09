---
title: Gestire l'accesso degli utenti a Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Informazioni su come gestire l'accesso degli utenti a Teams assegnando o rimuovendo una licenza di Teams agli utenti dell'organizzazione.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 770dcea62d6f3dc65f576a3d64a520dd4de2ecad
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637728"
---
# <a name="manage-user-access-to-teams"></a>Gestire l'accesso degli utenti a Teams

È possibile gestire l'accesso a Teams a livello utente assegnando o rimuovendo una licenza del prodotto Microsoft Teams. Ad eccezione di partecipare alle riunioni di Teams in forma anonima, ogni utente dell'organizzazione deve avere una licenza di Teams prima di poter usare Teams. È possibile assegnare una licenza di Teams per i nuovi utenti quando vengono creati nuovi account utente o per gli utenti con account esistenti.

Per impostazione predefinita, quando a un utente viene assegnato un piano di licenza, ad esempio Microsoft 365 Enterprise E3 o Microsoft 365 Business Premium, viene assegnata automaticamente una licenza di Teams e l'utente è abilitato per Teams. È possibile disabilitare o abilitare Teams per un utente rimuovendo o assegnando una licenza in qualsiasi momento.

Usare i criteri di messaggistica, gestiti dall'interfaccia di amministrazione di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams,</a>per controllare quali funzionalità di messaggistica di chat e canale sono disponibili per gli utenti in Teams. È possibile usare i criteri predefiniti o creare uno o più criteri di messaggistica personalizzati per gli utenti dell'organizzazione. Per altre informazioni, vedere [Gestire i criteri di messaggistica in Teams.](messaging-policies-in-teams.md)
Le licenze di Teams vengono gestite nell'interfaccia di amministrazione di Microsoft 365 o tramite PowerShell. Per gestire le licenze, è necessario essere un amministratore globale o un amministratore di gestione utenti.

> [!NOTE]
> È consigliabile abilitare Teams per tutti gli utenti in modo che i team possano essere formati organicamente per progetti e altre iniziative dinamiche. Anche se si esegue un progetto pilota, può essere comunque utile mantenere Teams abilitato per tutti gli utenti, ma solo per le comunicazioni mirate al gruppo pilota di utenti.

## <a name="using-the-microsoft-365-admin-center"></a>Uso dell'interfaccia di amministrazione di Microsoft 365

Le licenze a livello utente di Teams vengono gestite direttamente tramite le interfacce di gestione utente dell'interfaccia di amministrazione di Microsoft 365. Un amministratore può assegnare licenze ai nuovi utenti quando vengono creati nuovi account utente o agli utenti con account esistenti. 

> [!IMPORTANT]
> L'amministratore deve avere i privilegi di amministratore globale o amministratore di gestione utenti per gestire le licenze di Microsoft Teams.
Usare l'interfaccia di amministrazione di Microsoft 365 per gestire le licenze di Teams per singoli utenti o piccoli set di utenti alla volta. È possibile gestire le licenze di Teams nella **pagina Licenze** (per un massimo di 20 utenti contemporaneamente) o nella **pagina Utenti** attivi. Il metodo scelto varia a seconda che si vogliano gestire licenze di prodotto per utenti specifici o licenze utente per prodotti specifici.

Se è necessario gestire le licenze di Teams per un numero elevato di utenti, ad esempio centinaia o migliaia di utenti, usare [PowerShell](#using-powershell) o le licenze basate su gruppo [in Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign) 

### <a name="assign-a-teams-license"></a>Assegnare una licenza di Teams

I passaggi variano a seconda che si usi la **pagina Licenze** o la **pagina Utenti** attivi.  Per istruzioni dettagliate, vedere [Assegnare licenze agli utenti.](/microsoft-365/admin/manage/assign-licenses-to-users)

|||
|---------|---------|
|![Screenshot della licenza di Teams abilitata per un utente](media/assign-teams-licenses-1.png)    | ![Screenshot della licenza di Teams abilitata per un utente](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Rimuovere una licenza di Teams

> [!IMPORTANT]
> La disabilitazione di uno SKU di Teams richiede circa 24 ore.

Quando rimuovi una licenza di Teams da un utente, Teams viene disabilitato per quell'utente e non sarà più visualizzato nell'icona di avvio delle app o nella home page. Per la procedura dettagliata, vedere [Annullare l'assegnazione di licenze da parte degli utenti.](/microsoft-365/admin/manage/remove-licenses-from-users)

|||
|---------|---------|
|![Screenshot della licenza di Teams disabilitata per un utente](media/remove-teams-licenses-1.png)    | ![Screenshot della licenza di Teams disabilitata per un utente](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Utilizzo di PowerShell

Usare PowerShell per gestire le licenze di Teams per gli utenti in blocco. È possibile abilitare e disabilitare Teams tramite PowerShell nello stesso modo in cui si farebbe per qualsiasi altra licenza del piano di servizio. Sono necessari gli identificatori per i piani di servizio per Teams, che sono i seguenti:

- Microsoft Teams: TEAMS1
- Microsoft Teams per GCC: TEAMS_GOV
- Microsoft Teams per DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Assegnare licenze di Teams in blocco

Per la procedura dettagliata, vedere [Assegnare licenze agli account utente con PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)

### <a name="remove-teams-licenses-in-bulk"></a>Rimuovere le licenze di Teams in blocco

Per la procedura dettagliata, vedere [Disabilitare l'accesso](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) ai servizi con PowerShell e Disabilitare l'accesso ai [servizi durante l'assegnazione di licenze utente.](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)

#### <a name="example"></a>Esempio 

Di seguito è riportato un esempio di come usare i cmdlet [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) e [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) per disabilitare Teams per gli utenti che hanno un piano di licenza specifico. Ad esempio, seguire questa procedura per disabilitare prima Teams per tutti gli utenti che hanno un piano di licenza specifico. Abilita quindi Teams per ogni singolo utente che dovrebbe avere accesso a Teams.

> [!IMPORTANT]
> Il cmdlet [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) abiliterà tutti i servizi disabilitati in precedenza a meno che non siano stati identificati esplicitamente nello script personalizzato. Ad esempio, se si vuole lasciare sia Exchange che Sway disabilitati, disabilitando anche Teams, è necessario includerlo nello script oppure verranno abilitati sia Exchange che Sway per gli utenti identificati.

Eseguire il comando seguente per visualizzare tutti i piani di licenza disponibili nell'organizzazione. Per altre informazioni, vedere [Visualizzare licenze e servizi con PowerShell.](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)


```powershell
Get-MsolAccountSku
```

Eseguire i comandi seguenti, dove è il nome dell'organizzazione e l'identificatore del piano di licenza recuperato \<CompanyName:License> nel passaggio precedente. Ad esempio, ContosoSchool:ENTERPRISEPACK_STUDENT.

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

Eseguire il comando seguente per disabilitare Teams per tutti gli utenti che hanno una licenza attiva per il piano di licenza.

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>Argomenti correlati

- [Licenze per i componenti aggiuntivi di Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Assegnare licenze per i componenti aggiuntivi di Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Visualizzare licenze e servizi con PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nomi dei prodotti e identificatori dei piani di servizio per le licenze](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Informazioni di riferimento su SKU education](sku-reference-edu.md)
