---
title: Configurare l'analisi delle chiamate per Microsoft Teams
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
description: Configurare l'analisi delle chiamate per utente per identificare e risolvere i Microsoft Teams di qualità delle chiamate.
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117134"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="0af7d-103">Configurare l'analisi delle chiamate per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0af7d-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="0af7d-104">L'amministratore Microsoft Teams, è possibile usare l'analisi delle chiamate per utente per risolvere i problemi Teams di qualità delle chiamate e di connessione per **i singoli utenti.**</span><span class="sxs-lookup"><span data-stu-id="0af7d-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="0af7d-105">Per sfruttare al meglio l'analisi delle chiamate, configurare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0af7d-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="0af7d-106">Assegnare ruoli di supporto specializzati a persone, ad esempio agenti helpdesk, per consentire loro di visualizzare l'analisi delle chiamate per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0af7d-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="0af7d-107">Questi ruoli di supporto non possono accedere al resto dell'interfaccia Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="0af7d-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="0af7d-108">Aggiungere informazioni su edifici, siti e tenant all'analisi delle chiamate per utente caricando un file di dati con estensione tsv o .csv dati.</span><span class="sxs-lookup"><span data-stu-id="0af7d-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="0af7d-109">Quando si è pronti per iniziare a usare l'analisi delle chiamate per utente, vedere Usare l'analisi delle chiamate per utente per risolvere i problemi relativi alla [scarsa qualità delle chiamate.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="0af7d-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="0af7d-110">Concedere l'autorizzazione al personale del supporto tecnico e dell'helpdesk</span><span class="sxs-lookup"><span data-stu-id="0af7d-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="0af7d-111">L'Teams ha accesso completo alle informazioni di analisi per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0af7d-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="0af7d-112">Sono stati creati alcuni ruoli Azure Active Directory specializzati che è possibile assegnare al personale di supporto e agli agenti dell'helpdesk in modo che possano accedere anche all'analisi delle chiamate per utente (senza avere accesso al resto dell'interfaccia di amministrazione di Teams).</span><span class="sxs-lookup"><span data-stu-id="0af7d-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="0af7d-113">Assegnare **il Teams** di supporto per le comunicazioni a utenti che devono avere una visualizzazione limitata dell'analisi delle chiamate per utente (supporto di livello 1).</span><span class="sxs-lookup"><span data-stu-id="0af7d-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="0af7d-114">Assegnare il **Teams tecnico** del supporto per le comunicazioni a utenti che necessitano dell'accesso completo all'analisi delle chiamate per utente (supporto di livello 2).</span><span class="sxs-lookup"><span data-stu-id="0af7d-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="0af7d-115">Nessuno dei due ruoli ha accesso al resto dell'Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="0af7d-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="0af7d-116">Per informazioni sulle funzioni di ognuno di questi ruoli, vedere Che cosa fa ogni Teams [di supporto tecnico?](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)</span><span class="sxs-lookup"><span data-stu-id="0af7d-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="0af7d-117">Per altre informazioni sui ruoli Teams di amministratore, vedere Usare i ruoli di amministratore Teams [per gestire](using-admin-roles.md)Teams .</span><span class="sxs-lookup"><span data-stu-id="0af7d-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="0af7d-118">Per informazioni su come assegnare ruoli di amministratore in Azure Active Directory, vedere Visualizzare e [assegnare ruoli in Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="0af7d-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="0af7d-119">Per informazioni su come assegnare ruoli amministrativi in Azure Active Directory, vedere Visualizzare e [assegnare ruoli in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="0af7d-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="0af7d-120">Upload un file tsv o .csv per aggiungere informazioni su edificio, sito e tenant</span><span class="sxs-lookup"><span data-stu-id="0af7d-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="0af7d-121">È possibile aggiungere informazioni su edifici, siti e tenant all'analisi delle chiamate per utente caricando un file .csv o tsv.</span><span class="sxs-lookup"><span data-stu-id="0af7d-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="0af7d-122">Con tutte queste informazioni, l'analisi delle chiamate può mappare gli indirizzi IP alle posizioni fisiche.</span><span class="sxs-lookup"><span data-stu-id="0af7d-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="0af7d-123">Gli amministratori e gli agenti dell'helpdesk possono usare queste informazioni per individuare le tendenze nei problemi di chiamata.</span><span class="sxs-lookup"><span data-stu-id="0af7d-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="0af7d-124">Ad esempio, perché gli utenti dello stesso edificio hanno problemi simili di qualità delle chiamate?</span><span class="sxs-lookup"><span data-stu-id="0af7d-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="0af7d-125">Gli amministratori di Teams o Skype for Business, possono usare un tenant esistente e un file di dati di creazione dal Teams o Skype for Business Call Quality Dashboard (CQD).</span><span class="sxs-lookup"><span data-stu-id="0af7d-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="0af7d-126">Prima di tutto, si scarica il file da CQD, quindi lo si carica per chiamare analytics.</span><span class="sxs-lookup"><span data-stu-id="0af7d-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="0af7d-127">Per scaricare un file di dati esistente, passare a Microsoft Teams **di amministrazione** Call  >  **Quality Dashboard** Upload  >  **adesso**.</span><span class="sxs-lookup"><span data-stu-id="0af7d-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="0af7d-128">**Nell'elenco I miei caricamenti** fare clic **su Scarica** accanto al file desiderato.</span><span class="sxs-lookup"><span data-stu-id="0af7d-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="0af7d-129">Per caricare il nuovo file, passare Microsoft Teams percorsi **dell'interfaccia** di amministrazione e quindi selezionare Upload posizione o Sostituisci  >   **dati posizione**. </span><span class="sxs-lookup"><span data-stu-id="0af7d-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="0af7d-130">Se si sta creando il file tsv o .csv file da zero, vedere Upload [tenant e creazione di dati.](CQD-upload-tenant-building-data.md)</span><span class="sxs-lookup"><span data-stu-id="0af7d-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0af7d-131">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0af7d-131">Related topics</span></span>

[<span data-ttu-id="0af7d-132">Usare l'analisi delle chiamate per utente per risolvere i problemi relativi alla scarsa qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="0af7d-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="0af7d-133">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="0af7d-133">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)