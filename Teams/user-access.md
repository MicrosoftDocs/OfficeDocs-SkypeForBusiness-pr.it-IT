---
title: Gestire l'accesso degli utenti Microsoft Teams
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
description: Informazioni su come gestire l'accesso degli utenti ai Teams assegnando o rimuovendo una licenza Teams agli utenti dell'organizzazione.
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
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="4f498-103">Gestire l'accesso degli utenti a Teams</span><span class="sxs-lookup"><span data-stu-id="4f498-103">Manage user access to Teams</span></span>

<span data-ttu-id="4f498-104">È possibile gestire l'Teams a livello di utente assegnando o rimuovendo una licenza Microsoft Teams prodotto.</span><span class="sxs-lookup"><span data-stu-id="4f498-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="4f498-105">Ad eccezione della partecipazione Teams riunioni in forma anonima, ogni utente dell'organizzazione deve avere una licenza Teams per poter usare Teams.</span><span class="sxs-lookup"><span data-stu-id="4f498-105">Except for joining Teams meetings anonymously, each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="4f498-106">È possibile assegnare una Teams per i nuovi utenti quando vengono creati nuovi account utente o per gli utenti con account esistenti.</span><span class="sxs-lookup"><span data-stu-id="4f498-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="4f498-107">Per impostazione predefinita, quando a un utente viene assegnato un piano di licenza, ad esempio Microsoft 365 Enterprise E3 o Microsoft 365 Business Premium, viene assegnata automaticamente una licenza Teams e l'utente è abilitato per Teams.</span><span class="sxs-lookup"><span data-stu-id="4f498-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium) is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="4f498-108">È possibile disabilitare o abilitare Teams per un utente rimuovendo o assegnando una licenza in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="4f498-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="4f498-109">Usare i criteri di messaggistica, gestiti <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">dall'interfaccia</a>di amministrazione di Teams , per controllare quali funzionalità di messaggistica di chat e canale sono disponibili per gli utenti in Teams.</span><span class="sxs-lookup"><span data-stu-id="4f498-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="4f498-110">È possibile usare i criteri predefiniti o creare uno o più criteri di messaggistica personalizzati per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4f498-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="4f498-111">Per altre informazioni, vedere [Gestire i criteri di messaggistica in Teams](messaging-policies-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4f498-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="4f498-112">È possibile gestire Teams licenze nell'Microsoft 365 di amministrazione o usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f498-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="4f498-113">Per gestire le licenze, è necessario essere un amministratore globale o un amministratore di gestione utenti.</span><span class="sxs-lookup"><span data-stu-id="4f498-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="4f498-114">È consigliabile abilitare la Teams per tutti gli utenti in modo che i team possano essere formati organicamente per progetti e altre iniziative dinamiche.</span><span class="sxs-lookup"><span data-stu-id="4f498-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="4f498-115">Anche se si esegue un progetto pilota, può essere comunque utile mantenere abilitata l'Teams per tutti gli utenti, ma solo per le comunicazioni mirate al gruppo pilota di utenti.</span><span class="sxs-lookup"><span data-stu-id="4f498-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="4f498-116">Uso dell'Microsoft 365 di amministrazione</span><span class="sxs-lookup"><span data-stu-id="4f498-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="4f498-117">Teams le licenze a livello di utente vengono gestite direttamente tramite le interfacce di gestione Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="4f498-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="4f498-118">Un amministratore può assegnare licenze ai nuovi utenti quando vengono creati nuovi account utente o agli utenti con account esistenti.</span><span class="sxs-lookup"><span data-stu-id="4f498-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4f498-119">L'amministratore deve avere i privilegi di amministratore globale o di amministratore di gestione utenti per gestire Microsoft Teams licenze.</span><span class="sxs-lookup"><span data-stu-id="4f498-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="4f498-120">Usare l Microsoft 365 di amministrazione per gestire Teams licenze per singoli utenti o piccoli set di utenti alla volta.</span><span class="sxs-lookup"><span data-stu-id="4f498-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="4f498-121">È possibile gestire Teams licenze nella **pagina Licenze** (per un massimo di 20 utenti contemporaneamente) o nella **pagina Utenti** attivi.</span><span class="sxs-lookup"><span data-stu-id="4f498-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="4f498-122">Il metodo scelto varia a seconda che si vogliano gestire licenze di prodotto per utenti specifici o licenze utente per prodotti specifici.</span><span class="sxs-lookup"><span data-stu-id="4f498-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="4f498-123">Se è necessario gestire le licenze Teams per un numero elevato di utenti, ad esempio centinaia o migliaia di utenti, usare [PowerShell](#using-powershell) o le licenze basate su gruppo [in Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="4f498-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use PowerShell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="4f498-124">Assegnare una Teams licenza</span><span class="sxs-lookup"><span data-stu-id="4f498-124">Assign a Teams license</span></span>

<span data-ttu-id="4f498-125">I passaggi variano a seconda che si usi la **pagina Licenze** o la **pagina Utenti** attivi.</span><span class="sxs-lookup"><span data-stu-id="4f498-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="4f498-126">Per istruzioni dettagliate, vedere [Assegnare licenze agli utenti.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="4f498-126">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![Screenshot della Teams licenza abilitata per un utente](media/assign-teams-licenses-1.png)    | ![Screenshot della Teams licenza abilitata per un utente](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="4f498-129">Rimuovere una Teams licenza</span><span class="sxs-lookup"><span data-stu-id="4f498-129">Remove a Teams license</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f498-130">La disabilitazione di uno SKU Teams 24 ore.</span><span class="sxs-lookup"><span data-stu-id="4f498-130">It takes about 24 hours for disabling a Teams SKU to take effect.</span></span>

<span data-ttu-id="4f498-131">Quando si rimuove una licenza Teams da un utente, il Teams viene disabilitato per tale utente e non sarà più visualizzato Teams nell'icona di avvio delle app o nella home page.</span><span class="sxs-lookup"><span data-stu-id="4f498-131">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="4f498-132">Per la procedura dettagliata, vedere [Annullare l'assegnazione di licenze da parte degli utenti.](/microsoft-365/admin/manage/remove-licenses-from-users)</span><span class="sxs-lookup"><span data-stu-id="4f498-132">For detailed steps, see [Unassign licenses from users](/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![Screenshot della licenza Teams disabilitata per un utente](media/remove-teams-licenses-1.png)    | ![Screenshot della licenza Teams disabilitata per un utente](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="4f498-135">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f498-135">Using PowerShell</span></span>

<span data-ttu-id="4f498-136">Usare PowerShell per gestire le Teams per gli utenti in blocco.</span><span class="sxs-lookup"><span data-stu-id="4f498-136">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="4f498-137">È possibile abilitare e disabilitare Teams tramite PowerShell nello stesso modo in cui si farebbe per qualsiasi altra licenza del piano di servizio.</span><span class="sxs-lookup"><span data-stu-id="4f498-137">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="4f498-138">Sono necessari gli identificatori per i piani di servizio per Teams, che sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f498-138">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="4f498-139">Microsoft Teams: TEAMS1</span><span class="sxs-lookup"><span data-stu-id="4f498-139">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="4f498-140">Microsoft Teams per GCC: TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="4f498-140">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="4f498-141">Microsoft Teams per DoD: TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="4f498-141">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="4f498-142">Assegnare Teams licenze in blocco</span><span class="sxs-lookup"><span data-stu-id="4f498-142">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="4f498-143">Per la procedura dettagliata, vedere [Assegnare licenze agli account utente con PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="4f498-143">For detailed steps, see [Assign licenses to user accounts with PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="4f498-144">Rimuovere Teams licenze in blocco</span><span class="sxs-lookup"><span data-stu-id="4f498-144">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="4f498-145">Per la procedura dettagliata, vedere [Disabilitare l'accesso](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) ai servizi con PowerShell e Disabilitare l'accesso ai [servizi durante l'assegnazione di licenze utente.](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)</span><span class="sxs-lookup"><span data-stu-id="4f498-145">For detailed steps, see [Disable access to services with PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="4f498-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f498-146">Example</span></span> 

<span data-ttu-id="4f498-147">Di seguito è riportato un esempio di come usare i cmdlet [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) e [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) per disabilitare Teams per gli utenti che hanno un piano di licenza specifico.</span><span class="sxs-lookup"><span data-stu-id="4f498-147">The following is an example of how to use the [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="4f498-148">Ad esempio, seguire questa procedura per disabilitare prima Teams per tutti gli utenti che hanno un piano di licenza specifico.</span><span class="sxs-lookup"><span data-stu-id="4f498-148">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="4f498-149">Abilitare quindi Teams per ogni singolo utente che deve avere accesso a Teams.</span><span class="sxs-lookup"><span data-stu-id="4f498-149">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f498-150">Il cmdlet [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) abiliterà tutti i servizi disabilitati in precedenza a meno che non siano stati identificati esplicitamente nello script personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4f498-150">The [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="4f498-151">Ad esempio, se si vuole lasciare disabilitati sia Exchange che Sway, disabilitando anche Teams, è necessario includerlo nello script oppure sia Exchange che Sway verranno abilitati per gli utenti identificati.</span><span class="sxs-lookup"><span data-stu-id="4f498-151">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="4f498-152">Eseguire il comando seguente per visualizzare tutti i piani di licenza disponibili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4f498-152">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="4f498-153">Per altre informazioni, vedere [Visualizzare licenze e servizi con PowerShell.](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="4f498-153">To learn more, see [View licenses and services with PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>


```powershell
Get-MsolAccountSku
```

<span data-ttu-id="4f498-154">Eseguire i comandi seguenti, dove è il nome dell'organizzazione e l'identificatore del piano di licenza recuperato \<CompanyName:License> nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="4f498-154">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="4f498-155">Ad esempio, ContosoSchool:ENTERPRISEPACK_STUDENT.</span><span class="sxs-lookup"><span data-stu-id="4f498-155">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

<span data-ttu-id="4f498-156">Eseguire il comando seguente per disabilitare Teams per tutti gli utenti che hanno una licenza attiva per il piano di licenza.</span><span class="sxs-lookup"><span data-stu-id="4f498-156">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a><span data-ttu-id="4f498-157">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4f498-157">Related topics</span></span>

- [<span data-ttu-id="4f498-158">Teams licenze per i componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="4f498-158">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="4f498-159">Assegnare Teams licenze per i componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="4f498-159">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="4f498-160">Visualizzare licenze e servizi con PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f498-160">View licenses and services with PowerShell</span></span>](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="4f498-161">Nomi dei prodotti e identificatori dei piani di servizio per le licenze</span><span class="sxs-lookup"><span data-stu-id="4f498-161">Product names and service plan identifiers for licensing</span></span>](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="4f498-162">Informazioni di riferimento su SKU education</span><span class="sxs-lookup"><span data-stu-id="4f498-162">Education SKU reference</span></span>](sku-reference-edu.md)
