---
title: Configurare le analisi delle chiamate per Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Configurare le analisi delle chiamate per utente per identificare e risolvere i problemi di qualità delle chiamate di Microsoft teams.
ms.openlocfilehash: f1ea46f275dfbbe5ea7f6cd40d8c06fba2b5e00f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581107"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="1b179-103">Configurare le analisi delle chiamate per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1b179-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="1b179-104">Come amministratore di Microsoft teams, puoi usare l'analisi delle chiamate per utente per risolvere i problemi di qualità delle chiamate dei team e per i **singoli utenti**.</span><span class="sxs-lookup"><span data-stu-id="1b179-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="1b179-105">Per sfruttare al meglio l'analisi delle chiamate, configurare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1b179-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="1b179-106">Assegnare ruoli di supporto specializzati alle persone, ad esempio gli agenti dell'helpdesk, per consentire loro di visualizzare le analisi delle chiamate per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1b179-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="1b179-107">Questi ruoli di supporto non possono accedere al resto dell'interfaccia di amministrazione di teams.</span><span class="sxs-lookup"><span data-stu-id="1b179-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="1b179-108">Aggiungere informazioni su edifici, siti e tenant a analisi delle chiamate per utente tramite il caricamento di un file di dati con estensione TSV o CSV.</span><span class="sxs-lookup"><span data-stu-id="1b179-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="1b179-109">Quando si è pronti per iniziare a usare l'analisi delle chiamate per utente, leggere [usare l'analisi delle chiamate per utente per risolvere i problemi di qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span><span class="sxs-lookup"><span data-stu-id="1b179-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="1b179-110">Concedere l'autorizzazione per il supporto e il personale dell'helpdesk</span><span class="sxs-lookup"><span data-stu-id="1b179-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="1b179-111">L'amministratore di Teams ha accesso completo alle informazioni di analisi delle chiamate per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1b179-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="1b179-112">È stato creato un certo ruolo di Azure Active Directory specializzato che è possibile assegnare al personale di supporto e agli agenti dell'helpdesk in modo che possano accedere anche all'analisi delle chiamate per utente (senza avere accesso al resto dell'interfaccia di amministrazione di Teams).</span><span class="sxs-lookup"><span data-stu-id="1b179-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="1b179-113">Assegna il ruolo di **specialista delle comunicazioni teams** agli utenti che dovrebbero avere una visione limitata dell'analisi delle chiamate per utente (supporto di Tier 1).</span><span class="sxs-lookup"><span data-stu-id="1b179-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="1b179-114">Assegnare il ruolo di **Assistente tecnico comunicazioni teams** agli utenti che hanno bisogno di un accesso completo all'analisi delle chiamate per utente (supporto di Tier 2).</span><span class="sxs-lookup"><span data-stu-id="1b179-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="1b179-115">Nessun ruolo ha accesso al resto dell'interfaccia di amministrazione di teams.</span><span class="sxs-lookup"><span data-stu-id="1b179-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="1b179-116">Per informazioni su cosa fa ognuno di questi ruoli, leggere [cosa fa il ruolo di supporto di ogni team](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span><span class="sxs-lookup"><span data-stu-id="1b179-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="1b179-117">Per altre informazioni sui ruoli di amministratore di teams, vedere [usare i ruoli di amministratore di teams per gestire teams](using-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1b179-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="1b179-118">Per informazioni su come assegnare ruoli di amministratore in Azure Active Directory, vedere [visualizzare e assegnare ruoli in Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="1b179-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="1b179-119">Per informazioni su come assegnare ruoli amministrativi in Azure Active Directory, vedere [visualizzare e assegnare ruoli in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="1b179-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="1b179-120">Caricare un file con estensione TSV o CSV per aggiungere informazioni su edifici, siti e tenant</span><span class="sxs-lookup"><span data-stu-id="1b179-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="1b179-121">È possibile aggiungere informazioni su edifici, siti e tenant a analisi delle chiamate per utente tramite il caricamento di un file CSV o TSV.</span><span class="sxs-lookup"><span data-stu-id="1b179-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="1b179-122">Con tutte queste informazioni, Call Analytics può eseguire il mapping degli indirizzi IP alle posizioni fisiche.</span><span class="sxs-lookup"><span data-stu-id="1b179-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="1b179-123">Gli amministratori e gli agenti dell'helpdesk possono usare queste informazioni per individuare le tendenze dei problemi di chiamata.</span><span class="sxs-lookup"><span data-stu-id="1b179-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="1b179-124">Ad esempio, perché gli utenti nello stesso edificio hanno problemi di qualità delle chiamate simili?</span><span class="sxs-lookup"><span data-stu-id="1b179-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="1b179-125">Se si è un team o un amministratore di Skype for business, è possibile usare un tenant e un file di dati di costruzione esistenti dal team o da Skype for business call Quality Dashboard (Call Quality Dashboard).</span><span class="sxs-lookup"><span data-stu-id="1b179-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="1b179-126">Prima di tutto, si Scarica il file da Call Quality dashboard, quindi lo si carica in analisi chiamata.</span><span class="sxs-lookup"><span data-stu-id="1b179-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="1b179-127">Per scaricare un file di dati esistente, passa a **Microsoft teams Admin Center**  >  **Call Quality dashboard**  >  **Upload Now**.</span><span class="sxs-lookup"><span data-stu-id="1b179-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="1b179-128">Nell'elenco **upload personali** fare clic su **Scarica** accanto al file desiderato.</span><span class="sxs-lookup"><span data-stu-id="1b179-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="1b179-129">Per caricare il nuovo file, accedere alle posizioni dell'interfaccia di **amministrazione di Microsoft teams**  >  **Locations**e quindi selezionare **Carica dati posizione** o **Sostituisci dati posizione**.</span><span class="sxs-lookup"><span data-stu-id="1b179-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="1b179-130">Se si sta creando il file TSV o CSV da zero, vedere caricare i [dati del tenant e della creazione](CQD-upload-tenant-building-data.md).</span><span class="sxs-lookup"><span data-stu-id="1b179-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1b179-131">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1b179-131">Related topics</span></span>

[<span data-ttu-id="1b179-132">Usare le analisi delle chiamate per utente per risolvere i problemi di qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="1b179-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="1b179-133">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="1b179-133">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
