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
description: Configurare l'analisi delle chiamate per utente per identificare e risolvere i problemi di qualità delle chiamate di Microsoft Teams.
ms.openlocfilehash: f1ea46f275dfbbe5ea7f6cd40d8c06fba2b5e00f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581107"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="0bead-103">Configurare l'analisi delle chiamate per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0bead-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="0bead-104">Come amministratore di Microsoft Teams, puoi usare l'analisi delle chiamate per utente per risolvere i problemi di qualità delle chiamate e di connessione di Teams **per i singoli utenti.**</span><span class="sxs-lookup"><span data-stu-id="0bead-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="0bead-105">Per sfruttare al meglio i dati analitici delle chiamate, configura quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0bead-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="0bead-106">Assegnare ruoli speciali di supporto alle persone, ad esempio agenti helpdesk, per consentire loro di visualizzare i dati analitici delle chiamate per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0bead-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="0bead-107">Questi ruoli di supporto non possono accedere al resto dell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="0bead-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="0bead-108">Aggiungi informazioni a livello di edificio, sito e tenant all'analisi delle chiamate per utente caricando un file di dati .tsv o .csv.</span><span class="sxs-lookup"><span data-stu-id="0bead-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="0bead-109">Quando sei pronto a iniziare a usare l'analisi delle chiamate per utente, leggi Usa l'analisi delle chiamate per utente per risolvere i problemi di [bassa qualità delle chiamate.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="0bead-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="0bead-110">Concedere l'autorizzazione al personale del supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="0bead-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="0bead-111">Come amministratore di Teams, hai accesso completo alle informazioni di analisi delle chiamate per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0bead-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="0bead-112">Abbiamo creato alcuni ruoli speciali di Azure Active Directory che puoi assegnare al personale di supporto e agli agenti helpdesk in modo che possano anche accedere ai dati analitici delle chiamate per utente (senza avere accesso al resto dell'interfaccia di amministrazione di Teams).</span><span class="sxs-lookup"><span data-stu-id="0bead-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="0bead-113">Assegnare il **ruolo di esperto** del supporto per le comunicazioni di Teams agli utenti che devono avere una visualizzazione limitata dell'analisi delle chiamate per utente (supporto di Livello 1).</span><span class="sxs-lookup"><span data-stu-id="0bead-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="0bead-114">Assegnare il ruolo di tecnico **del supporto per le** comunicazioni di Teams agli utenti che hanno bisogno dell'accesso completo all'analisi delle chiamate per utente (supporto di Livello 2).</span><span class="sxs-lookup"><span data-stu-id="0bead-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="0bead-115">Nessuno dei due ruoli ha accesso al resto dell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="0bead-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="0bead-116">Per sapere cosa fa ciascuno di questi ruoli, leggere Cosa fa ogni ruolo di [supporto di Teams?](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)</span><span class="sxs-lookup"><span data-stu-id="0bead-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="0bead-117">Per altre informazioni sui ruoli di amministratore di Teams, vedere [Usare i ruoli di amministratore di Teams per gestire Teams.](using-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="0bead-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="0bead-118">Per informazioni su come assegnare ruoli di amministratore in Azure Active Directory, vedere Visualizzare e [assegnare ruoli in Azure Active Directory.](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)</span><span class="sxs-lookup"><span data-stu-id="0bead-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="0bead-119">Per informazioni su come assegnare ruoli amministrativi in Azure Active Directory, vedere Visualizzare e [assegnare ruoli in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)</span><span class="sxs-lookup"><span data-stu-id="0bead-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="0bead-120">Caricare un file con estensione tsv o csv per aggiungere informazioni relative a edifici, siti e tenant</span><span class="sxs-lookup"><span data-stu-id="0bead-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="0bead-121">Puoi aggiungere informazioni a livello di edificio, sito e tenant alle analisi delle chiamate per utente caricando un file CSV o TSV.</span><span class="sxs-lookup"><span data-stu-id="0bead-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="0bead-122">Con tutte queste informazioni, l'analisi delle chiamate può mappare gli indirizzi IP alle posizioni fisiche.</span><span class="sxs-lookup"><span data-stu-id="0bead-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="0bead-123">Amministratori e agenti helpdesk possono usare queste informazioni per individuare tendenze nei problemi di chiamata.</span><span class="sxs-lookup"><span data-stu-id="0bead-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="0bead-124">Ad esempio, perché gli utenti nello stesso edificio hanno problemi simili di qualità delle chiamate?</span><span class="sxs-lookup"><span data-stu-id="0bead-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="0bead-125">Se sei un amministratore di Teams o Skype for Business, puoi utilizzare un tenant esistente e creare un file di dati da Teams o Skype for Business Call Quality Dashboard (CQD).</span><span class="sxs-lookup"><span data-stu-id="0bead-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="0bead-126">Prima di tutto, scarica il file da Call Call Analytics, quindi caricalo nell'analisi delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="0bead-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="0bead-127">Per scaricare un file di dati esistente, vai all'interfaccia **di amministrazione di Microsoft Teams** Call Quality  >  **Dashboard**  >  **Carica ora.**</span><span class="sxs-lookup"><span data-stu-id="0bead-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="0bead-128">**Nell'elenco Caricamenti** fare clic su **Scarica** accanto al file desiderato.</span><span class="sxs-lookup"><span data-stu-id="0bead-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="0bead-129">Per caricare il nuovo file, passare a Percorsi dell'interfaccia di amministrazione di **Microsoft Teams** e quindi selezionare Carica dati posizione o Sostituisci dati  >  sulla **posizione.** </span><span class="sxs-lookup"><span data-stu-id="0bead-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="0bead-130">Se si sta creando il file TSV o CSV da zero, vedere [Caricare i dati del tenant e della creazione.](CQD-upload-tenant-building-data.md)</span><span class="sxs-lookup"><span data-stu-id="0bead-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0bead-131">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0bead-131">Related topics</span></span>

[<span data-ttu-id="0bead-132">Usare l'analisi delle chiamate per utente per risolvere i problemi di bassa qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="0bead-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="0bead-133">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="0bead-133">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
