---
title: Aggiornare il certificato Edge
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Questa appendice include i passaggi dettagliati per aggiornare il certificato Edge nell'ambito del consolidamento del cloud per Teams e Skype for business.
ms.openlocfilehash: 1c3aaa8859db530ceccbebc68ae76f21e8d4a77f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185501"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="d29bb-103">Aggiornare il certificato Edge</span><span class="sxs-lookup"><span data-stu-id="d29bb-103">Update the edge certificate</span></span>

<span data-ttu-id="d29bb-104">L'aggiornamento del certificato Edge è il passaggio chiave per garantire che un ambiente su Prem con SipDomain1 sia in grado di partecipare a un ambiente cloud con SipDomain2 e garantire un routing corretto in un ambiente di spazio di indirizzi condiviso tra i due domini SIP.</span><span class="sxs-lookup"><span data-stu-id="d29bb-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="d29bb-105">Vedere il passaggio 14 nel consolidamento del [cloud per Teams e Skype for business](cloud-consolidation.md) per il contesto in cui è possibile eseguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="d29bb-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="d29bb-106">In questo esempio SipDomain1 è AcquiredCompany. <span>com e SipDomain2 è OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="d29bb-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="d29bb-107">Il nome alternativo soggetto (SAN) del certificato in tutti i server perimetrali nell'ambiente locale deve essere aggiornato per includere tutti i domini SIP presenti nel tenant puro online (ad esclusione di qualsiasi onmicrosoft.<span> domini com), nel formato "SIP". \<Domain> ".</span><span class="sxs-lookup"><span data-stu-id="d29bb-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="d29bb-108">In questo esempio si tratta di SIP. OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="d29bb-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="d29bb-109">Questo passaggio è fondamentale per eseguire la migrazione degli utenti al cloud.</span><span class="sxs-lookup"><span data-stu-id="d29bb-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="d29bb-110">**Passaggi**</span><span class="sxs-lookup"><span data-stu-id="d29bb-110">**Steps:**</span></span>

1.  <span data-ttu-id="d29bb-111">Ottenere un nuovo certificato perimetrale esterno per il bordo che contiene tutte le voci esistenti e altre voci nella SAN per tutti i domini SIP nell'ambiente cloud (ad eccezione dei domini \*. onmicrosoft.com) nel modulo "SIP". <DomainName>".</span><span class="sxs-lookup"><span data-stu-id="d29bb-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="d29bb-112">Installare il certificato localmente in ogni Edge Server e assegnarlo a Skype Edge service in ogni servizio Edge.</span><span class="sxs-lookup"><span data-stu-id="d29bb-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="d29bb-113">Per la procedura dettagliata, vedere la sezione "certificati di interfaccia Edge esterni" in [Deploy Edge service in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span><span class="sxs-lookup"><span data-stu-id="d29bb-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="d29bb-114">Riavviare il servizio Edge in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d29bb-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="d29bb-115">Puoi eseguire questa operazione per una singola casella con i comandi di PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="d29bb-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="d29bb-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d29bb-116">See also</span></span>

[<span data-ttu-id="d29bb-117">Consolidamento cloud per Teams e Skype for business</span><span class="sxs-lookup"><span data-stu-id="d29bb-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)