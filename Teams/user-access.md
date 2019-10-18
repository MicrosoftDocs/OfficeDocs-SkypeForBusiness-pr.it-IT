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
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="13aad-103">Gestire l'accesso degli utenti a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13aad-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="13aad-104">A livello di utente, l'accesso a Microsoft teams può essere abilitato o disabilitato per singolo utente assegnando o rimuovendo la licenza per il prodotto Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="13aad-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="13aad-105">Usare i criteri di messaggistica, gestiti dall'interfaccia di amministrazione di teams, per controllare quali funzionalità di messaggistica chat e canali sono disponibili per gli utenti in teams.</span><span class="sxs-lookup"><span data-stu-id="13aad-105">Use messaging policies, managed from the Teams Admin Center, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="13aad-106">È possibile usare i criteri predefiniti o creare uno o più criteri di messaggistica personalizzati per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="13aad-106">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="13aad-107">Per altre informazioni, leggere [gestire i criteri di messaggistica in teams](messaging-policies-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="13aad-107">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>

> [!NOTE]
><span data-ttu-id="13aad-108">Microsoft consiglia di attivare team per tutti gli utenti di un'azienda in modo che i team possano essere formati organicamente per progetti e altre iniziative dinamiche.</span><span class="sxs-lookup"><span data-stu-id="13aad-108">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="13aad-109">Anche se decidi di pilotarlo, potrebbe essere comunque utile conservare i team abilitati per tutti gli utenti, ma solo le comunicazioni di destinazione per il gruppo di utenti pilota.</span><span class="sxs-lookup"><span data-stu-id="13aad-109">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a><span data-ttu-id="13aad-110">Gestire i team tramite l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="13aad-110">Manage Teams through the Microsoft 365 admin center</span></span>

<span data-ttu-id="13aad-111">Le licenze a livello di utente di teams vengono gestite direttamente tramite le interfacce di gestione degli utenti di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13aad-111">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="13aad-112">Un amministratore può assegnare licenze ai nuovi utenti quando vengono creati nuovi account utente o per gli utenti con account esistenti.</span><span class="sxs-lookup"><span data-stu-id="13aad-112">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="13aad-113">Per gestire le licenze di Microsoft teams, l'amministratore deve disporre dei privilegi di amministratore globale o amministratore di Office 365.</span><span class="sxs-lookup"><span data-stu-id="13aad-113">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="13aad-114">Quando a un utente viene assegnata una licenza SKU come E3 o E5, viene automaticamente assegnata una licenza di Microsoft teams e l'utente è abilitato per Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="13aad-114">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="13aad-115">Gli amministratori possono avere un controllo granulare su tutti i servizi e le licenze di Office 365 e la licenza di Microsoft teams per un utente specifico o un gruppo di utenti può essere abilitata o disabilitata.</span><span class="sxs-lookup"><span data-stu-id="13aad-115">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Screenshot della sezione licenze di prodotto nell'interfaccia di amministrazione.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="13aad-117">Una licenza per gli utenti di teams può essere disabilitata in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="13aad-117">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="13aad-118">Quando la licenza è disabilitata, gli utenti accedono a Microsoft teams verranno impediti e l'utente non sarà più in grado di visualizzare i team nell'icona di avvio delle app di Office 365 e nella Home page.</span><span class="sxs-lookup"><span data-stu-id="13aad-118">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Screenshot che mostra i team selezionati nella sezione licenze di prodotto.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="13aad-120">Gestire tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="13aad-120">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13aad-121">New-MsolLicenseOptions consentirà di abilitare tutti i servizi precedentemente disabilitati, a meno che explictitly non abbia una identità nello script personalizzato.</span><span class="sxs-lookup"><span data-stu-id="13aad-121">New-MsolLicenseOptions will enable all services that were previously disabled unless explictitly identitied in your customized script.</span></span> <span data-ttu-id="13aad-122">Ad esempio, se si vuole abbandonare entrambi gli Exchange & Sway disabilitati durante la disattivazione dei team di Additonally, è necessario inlcude nello script o entrambi gli Exchange & Sway verranno abilitati per gli utenti identificati.</span><span class="sxs-lookup"><span data-stu-id="13aad-122">As an example, if you wanted to leave both Exchange & Sway disabled while additonally disabling Teams, you'd need to inlcude this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="13aad-123">Se si vuole usare una GUI per gestire questa funzionalità, vedere: [creazione di report e gestione delle licenze di Office 365-assegnazione di autorizzazioni di rimozione in blocco](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span><span class="sxs-lookup"><span data-stu-id="13aad-123">If you wish to do utilize a GUI to manage this functionality, See: [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span></span>

<span data-ttu-id="13aad-124">L'abilitazione e la disabilitazione dei team come licenza per il carico di lavoro tramite PowerShell viene eseguita come qualsiasi altro carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="13aad-124">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="13aad-125">Il nome del piano di servizio è TEAMS1 per Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="13aad-125">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="13aad-126">Per GCC il nome del piano di servizio è TEAMS_GOV.</span><span class="sxs-lookup"><span data-stu-id="13aad-126">For GCC the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="13aad-127">Per GCC High il nome del piano di servizio è TEAMS_GCCHIGH.</span><span class="sxs-lookup"><span data-stu-id="13aad-127">For GCC High the service plan name is TEAMS_GCCHIGH.</span></span> <span data-ttu-id="13aad-128">Per DoD il nome del piano di servizio è TEAMS_DOD (vedere [disabilitare l'accesso ai servizi con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) per altre informazioni).</span><span class="sxs-lookup"><span data-stu-id="13aad-128">For DoD the service plan name is TEAMS_DOD (See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="13aad-129">**Esempio:** Di seguito è riportato un semplice esempio di come disabilitare i team per tutti gli utenti in un determinato tipo di licenza.</span><span class="sxs-lookup"><span data-stu-id="13aad-129">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="13aad-130">Prima di tutto è necessario eseguire questa operazione, quindi abilitarla individualmente per gli utenti che devono avere accesso per scopi di pilotaggio.</span><span class="sxs-lookup"><span data-stu-id="13aad-130">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="13aad-131">Per visualizzare i tipi di abbonamento presenti all'interno dell'organizzazione, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="13aad-131">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="13aad-132">Immettere il nome del piano che include il nome dell'organizzazione e il piano per l'Istituto di istruzione (ad esempio ContosoSchool: ENTERPRISEPACK_STUDENT), quindi eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="13aad-132">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="13aad-133">Per disabilitare team per tutti gli utenti con una licenza attiva per il piano denominato, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="13aad-133">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Icona che rappresenta un punto decisionale](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="13aad-135">Punto decisionale</span><span class="sxs-lookup"><span data-stu-id="13aad-135">Decision Point</span></span>         |<ul><li><span data-ttu-id="13aad-136">Qual è il piano dell'organizzazione per i team onboard in tutta l'organizzazione?</span><span class="sxs-lookup"><span data-stu-id="13aad-136">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="13aad-137">(Pilot o Open)</span><span class="sxs-lookup"><span data-stu-id="13aad-137">(Pilot or Open)</span></span></li></ul>         |
|![Icona che rappresenta i passaggi successivi](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="13aad-139">Operazioni successive</span><span class="sxs-lookup"><span data-stu-id="13aad-139">Next Steps</span></span>         |<ul><li><span data-ttu-id="13aad-140">Se si esegue l'onboarding tramite un pilota chiuso, decidere se si vuole farlo tramite licenze o comunicazioni mirate.</span><span class="sxs-lookup"><span data-stu-id="13aad-140">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="13aad-141">A seconda della decisione, eseguire la procedura per assicurarsi che solo gli utenti pilota autorizzati ad accedere ai team (se necessario).</span><span class="sxs-lookup"><span data-stu-id="13aad-141">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="13aad-142">Documentare le linee guida per cui gli utenti (o meno) avranno accesso a teams.</span><span class="sxs-lookup"><span data-stu-id="13aad-142">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="13aad-143">Gestire Teams a livello di tenant di Office 365</span><span class="sxs-lookup"><span data-stu-id="13aad-143">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

