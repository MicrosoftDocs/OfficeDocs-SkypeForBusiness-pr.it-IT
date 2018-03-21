---
title: Conservazione dei file di grandi dimensioni collegati a un Skype per le riunioni aziendali
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "È possibile allegare file a un Skype per le riunioni aziendali, quali i partecipanti possono quindi aperta e download. File allegati a Skype per le riunioni aziendali vengono mantenuti nelle cassette postali di qualsiasi partecipante la cui cassetta postale viene messa in attesa di conservazione per controversia, è applicato un criterio di conservazione Office 365 o viene messa in attesa associata a un caso eDiscovery in Office 365 Security &amp; Centro conformità. Tale contenuto viene salvato nelle cassette postali di cartelle degli elementi recuperabili dei partecipanti."
ms.openlocfilehash: 59e1470d36aac988b1e0ff6ee40ebc1fb61967ed
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="7da66-105">Conservazione dei file di grandi dimensioni collegati a un Skype per le riunioni aziendali</span><span class="sxs-lookup"><span data-stu-id="7da66-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="7da66-106">È possibile allegare file a un Skype per le riunioni aziendali, quali i partecipanti possono quindi aperta e download.</span><span class="sxs-lookup"><span data-stu-id="7da66-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="7da66-107">File allegati a Skype per le riunioni aziendali vengono mantenuti nelle cassette postali di qualsiasi partecipante la cui cassetta postale viene messa in attesa di conservazione per controversia, è applicato un criterio di conservazione Office 365 o viene messa in attesa associata a un caso eDiscovery in Office 365 Security &amp; Centro conformità.</span><span class="sxs-lookup"><span data-stu-id="7da66-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has an Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="7da66-108">Tale contenuto viene salvato nelle cassette postali di cartelle **Degli elementi recuperabili** dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="7da66-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="7da66-109">I file che vengono mantenuti nelle cassette postali in attesa sono indicizzati e pertanto possono essere ricercati quando si esegue una ricerca di contenuto per la protezione &amp; centro conformità durante la ricerca delle cassette postali del partecipante.</span><span class="sxs-lookup"><span data-stu-id="7da66-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="7da66-110">Tuttavia, file allegati che superano MB 39 sono divisa in due o più file di dimensioni ridotte e salvati come file compresso (zip).</span><span class="sxs-lookup"><span data-stu-id="7da66-110">However, attached files that are larger than 39 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="7da66-111">Il *contenuto* di questi file di dimensioni ridotte non è indicizzato per la ricerca e potrebbe non essere restituito in una ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="7da66-111">The  *content*  of these smaller files is not indexed for search, and might not be returned in a Content Search.</span></span> <span data-ttu-id="7da66-112">Tuttavia, i *metadati* di questi file (ad esempio il nome di file e l'autore) sono indicizzato per la ricerca e potrebbero essere restituito in una ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="7da66-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search, and might be returned in a Content Search.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7da66-113">Se la cassetta postale è piena o amministratore tenant è configurato per essere minore del valore MB 39 MaxSendSize, caricamento file di dati non verranno mantenuti affatto.</span><span class="sxs-lookup"><span data-stu-id="7da66-113">If the mailbox is full or the tenant admin has configured MaxSendSize to be smaller than 39 MB, uploaded file data will not be retained at all.</span></span> <span data-ttu-id="7da66-114">Il valore predefinito MaxSendSize è 150 MB, ma gli amministratori tenant possono configurare MaxSendSize sia di circa 1 MB.</span><span class="sxs-lookup"><span data-stu-id="7da66-114">The default MaxSendSize is 150 MB, but tenant admins can configure MaxSendSize to be as small as 1 MB.</span></span> 
  
<span data-ttu-id="7da66-115">Cassette postali che non sono in attesa non avrà eventuali dati delle riunioni salvati.</span><span class="sxs-lookup"><span data-stu-id="7da66-115">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="7da66-116">Ad esempio, in una riunione di tre persone nelle cassette postali tra due partecipanti contrassegnate per la conservazione, vengono salvati i dati di riunione per le cassette postali tra i due partecipanti, ma non per la cassetta postale del terzo partecipante, la cui cassetta postale non è in attesa.</span><span class="sxs-lookup"><span data-stu-id="7da66-116">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7da66-117">See also</span><span class="sxs-lookup"><span data-stu-id="7da66-117">Related topics</span></span>
[<span data-ttu-id="7da66-118">Creare criteri di accesso esterno personalizzato</span><span class="sxs-lookup"><span data-stu-id="7da66-118">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="7da66-119">Trasferimenti di file bloccati punto-punto</span><span class="sxs-lookup"><span data-stu-id="7da66-119">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="7da66-120">Impostazione dei criteri client per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="7da66-120">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="7da66-121">Impostare i criteri relativi alle conferenze nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="7da66-121">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  