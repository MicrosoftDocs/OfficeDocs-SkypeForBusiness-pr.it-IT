---
title: Criteri di conservazione in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: Informazioni su come gestire i criteri di conservazione e su come gestirli in teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6779e9b0fa236b1c239f9e6aa56d97e9437fb422
ms.sourcegitcommit: 0f6321d51b40f06855679c18f7313febfedd419a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793522"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="b9dac-103">Criteri di conservazione in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9dac-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="b9dac-104">Le conversazioni dei team sono permanenti e mantenute per sempre per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b9dac-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="b9dac-105">Con l'introduzione dei criteri di conservazione, gli amministratori possono configurare i criteri di conservazione (conservazione ed eliminazione) nel centro sicurezza & conformità per i messaggi di chat e canali di teams.</span><span class="sxs-lookup"><span data-stu-id="b9dac-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="b9dac-106">In questo modo le organizzazioni mantengono i dati per la conformità (ovvero i criteri di conservazione) per un determinato periodo o eliminano i dati (vale a dire i criteri di eliminazione) se considerati passività dopo un determinato periodo.</span><span class="sxs-lookup"><span data-stu-id="b9dac-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="b9dac-107">I criteri di conservazione dei team garantiscono che quando si eliminano i dati, questa viene rimossa da tutti i percorsi di archiviazione dati permanenti nel servizio teams.</span><span class="sxs-lookup"><span data-stu-id="b9dac-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span>

> [!NOTE]
> <span data-ttu-id="b9dac-108">Non è ancora supportata la configurazione per la conservazione dei messaggi del canale privato.</span><span class="sxs-lookup"><span data-stu-id="b9dac-108">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="b9dac-109">È supportata la conservazione dei file condivisi nei canali privati.</span><span class="sxs-lookup"><span data-stu-id="b9dac-109">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="b9dac-110">Per gestire i criteri di conservazione dei team, usare le impostazioni e i cmdlet nel centro conformità & sicurezza di Office 365 in > **conservazione**della **governance delle informazioni**.</span><span class="sxs-lookup"><span data-stu-id="b9dac-110">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Information governance** > **Retention**.</span></span>

<span data-ttu-id="b9dac-111">I criteri di conservazione dei team supportano:</span><span class="sxs-lookup"><span data-stu-id="b9dac-111">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="b9dac-112">Conservazione: mantenere i dati del team per una durata specifica e quindi non eseguire alcuna operazione</span><span class="sxs-lookup"><span data-stu-id="b9dac-112">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="b9dac-113">Conservazione e quindi eliminazione: mantenere i dati del team per una durata specifica e quindi eliminare</span><span class="sxs-lookup"><span data-stu-id="b9dac-113">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="b9dac-114">Eliminazione: eliminare i dati di teams dopo una durata specificata</span><span class="sxs-lookup"><span data-stu-id="b9dac-114">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="b9dac-115">I criteri di conservazione dei team non supportano ancora:</span><span class="sxs-lookup"><span data-stu-id="b9dac-115">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="b9dac-116">I criteri di conservazione avanzati non si applicano alle posizioni dei messaggi del canale chat teams e teams</span><span class="sxs-lookup"><span data-stu-id="b9dac-116">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>
- <span data-ttu-id="b9dac-117">Durata di meno di 30 giorni</span><span class="sxs-lookup"><span data-stu-id="b9dac-117">Duration of fewer than 30 days</span></span>

<span data-ttu-id="b9dac-118">Gli amministratori possono configurare criteri di conservazione separati per le chat private di Teams (1:1 o 1: molte chat) e i messaggi del canale teams.</span><span class="sxs-lookup"><span data-stu-id="b9dac-118">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="b9dac-119">In molti casi, le organizzazioni considerano i dati della chat privata come un numero maggiore di passività rispetto ai messaggi del canale, che in genere sono più conversazioni correlate al progetto.</span><span class="sxs-lookup"><span data-stu-id="b9dac-119">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="b9dac-120">Configurare questi criteri nel centro conformità & sicurezza, la > **conservazione**della **governance delle informazioni**.</span><span class="sxs-lookup"><span data-stu-id="b9dac-120">Set up these policies in the Security & Compliance Center, **Information governance** > **Retention**.</span></span> <span data-ttu-id="b9dac-121">Attivare **i messaggi del canale teams** e le **chat di teams** e quindi definire i criteri di conservazione per queste posizioni (anche illustrato nel diagramma seguente).</span><span class="sxs-lookup"><span data-stu-id="b9dac-121">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="b9dac-122">Quando si attivano **i messaggi del canale teams**, è possibile specificare i team a cui applicare i criteri.</span><span class="sxs-lookup"><span data-stu-id="b9dac-122">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="b9dac-123">Ad esempio, per i team X, Y e Z, l'amministratore può impostare i criteri di eliminazione per 1 anno (selezionando questi team singolarmente) e applicare un criterio di eliminazione di 3 anni al resto dei team.</span><span class="sxs-lookup"><span data-stu-id="b9dac-123">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="b9dac-124">Puoi eseguire la stessa operazione per le **chat di teams** selezionando utenti specifici e applicando criteri di conservazione univoci.</span><span class="sxs-lookup"><span data-stu-id="b9dac-124">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![Diagramma del flusso di lavoro dei dati di teams in Exchange e SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="b9dac-126">Le posizioni dei messaggi del canale teams e delle chat teams sono indirizzate solo alle conversazioni dei team archiviati nelle cassette postali di Exchange Online (cassette postali utente e gruppo).</span><span class="sxs-lookup"><span data-stu-id="b9dac-126">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="b9dac-127">I messaggi vengono eliminati da tutti i percorsi di archiviazione rilevanti, vale a dire le cassette postali, il substrato e il servizio chat.</span><span class="sxs-lookup"><span data-stu-id="b9dac-127">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="b9dac-128">Per gestire i criteri di conservazione per i file di Team, archiviati in OneDrive for business e SharePoint, usare i criteri di conservazione.</span><span class="sxs-lookup"><span data-stu-id="b9dac-128">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="b9dac-129">In base alla progettazione, i criteri di eliminazione per i file di team vengono configurati tramite SharePoint Online e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="b9dac-129">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="b9dac-130">Di conseguenza, è possibile che un criterio possa eliminare un file a cui si fa riferimento in una chat o un messaggio di canale di teams prima che i messaggi vengano eliminati.</span><span class="sxs-lookup"><span data-stu-id="b9dac-130">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="b9dac-131">In questo caso, il file verrà ancora visualizzato nel messaggio teams, ma se si fa clic sul file, viene visualizzato un errore "file non trovato" (ciò può verificarsi anche in assenza di un criterio, se un utente elimina manualmente un file da SharePoint Online o OneDrive for business).</span><span class="sxs-lookup"><span data-stu-id="b9dac-131">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="b9dac-132">Per informazioni dettagliate sulla configurazione dei criteri di conservazione per Office 365, vedere [Cenni preliminari sui criteri di conservazione](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="b9dac-132">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
