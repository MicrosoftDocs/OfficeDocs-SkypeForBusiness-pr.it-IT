---
title: Aggiornare il certificato del server perimetrale
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
description: In questa appendice sono riportati i passaggi dettagliati per l'aggiornamento del certificato Edge nell'ambito del consolidamento cloud per Teams e Skype for business.
ms.openlocfilehash: 52ab646387acb6901798f215f9677f16978e87fb
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963054"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="59b3b-103">Aggiornare il certificato del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="59b3b-103">Update the edge certificate</span></span>

<span data-ttu-id="59b3b-104">L'aggiornamento del certificato del server perimetrale è il passaggio fondamentale per garantire che un ambiente su Prem con SipDomain1 possa unirsi a un ambiente cloud con SipDomain2 e garantire il routing corretto in un ambiente di spazio degli indirizzi condiviso tra i due domini SIP.</span><span class="sxs-lookup"><span data-stu-id="59b3b-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="59b3b-105">Vedere il passaggio 14 nel [consolidamento del cloud per i team e Skype for business](cloud-consolidation.md) per il contesto in cui è possibile eseguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="59b3b-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="59b3b-106">Negli esempi riportati di seguito, SipDomain1 è AcquiredCompany. <span>com e SipDomain2 è OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="59b3b-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="59b3b-107">Il nome alternativo soggetto (SAN) del certificato su tutti i server perimetrali nell'ambiente locale deve essere aggiornato in modo da includere tutti i domini SIP presenti nel tenant online puro (escludendo qualsiasi onmicrosoft.<span> domini com), nel formato SIP. \<> di dominio ".</span><span class="sxs-lookup"><span data-stu-id="59b3b-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="59b3b-108">In questo esempio, si tratta di SIP. OriginalCompany. <span>com.</span><span class="sxs-lookup"><span data-stu-id="59b3b-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="59b3b-109">Questo passaggio è fondamentale per eseguire la migrazione di tutti gli utenti nel cloud.</span><span class="sxs-lookup"><span data-stu-id="59b3b-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="59b3b-110">**Passi**</span><span class="sxs-lookup"><span data-stu-id="59b3b-110">**Steps:**</span></span>

1.  <span data-ttu-id="59b3b-111">Ottenere un nuovo certificato perimetrale esterno per il server perimetrale in cui sono presenti tutte le voci esistenti e altre voci nella rete SAN per tutti i domini SIP nell'ambiente cloud (ad eccezione dei domini \*. onmicrosoft.com) nel formato SIP. <DomainName>".</span><span class="sxs-lookup"><span data-stu-id="59b3b-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="59b3b-112">Installare il certificato in locale su ogni server perimetrale e assegnarlo al servizio Edge Skype su ogni servizio Edge.</span><span class="sxs-lookup"><span data-stu-id="59b3b-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="59b3b-113">Per la procedura dettagliata, vedere la sezione "certificati dell'interfaccia perimetrale esterna" in [Deploy Edge service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).</span><span class="sxs-lookup"><span data-stu-id="59b3b-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="59b3b-114">Riavviare il servizio Edge in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="59b3b-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="59b3b-115">È possibile eseguire questa operazione per una singola casella con i comandi di PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="59b3b-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="59b3b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59b3b-116">See also</span></span>

[<span data-ttu-id="59b3b-117">Consolidamento cloud per Teams e Skype for business</span><span class="sxs-lookup"><span data-stu-id="59b3b-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
