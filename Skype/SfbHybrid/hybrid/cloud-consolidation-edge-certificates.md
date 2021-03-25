---
title: Aggiornare il certificato perimetrale
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
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Questa appendice include la procedura dettagliata per aggiornare il certificato perimetrale come parte del consolidamento del cloud per Teams e Skype for Business.
ms.openlocfilehash: 724ac63239c881283368fbd617ce0654d49fc0e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120345"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="6054d-103">Aggiornare il certificato perimetrale</span><span class="sxs-lookup"><span data-stu-id="6054d-103">Update the edge certificate</span></span>

<span data-ttu-id="6054d-104">L'aggiornamento del certificato perimetrale è il passaggio chiave per garantire che un ambiente locale con SipDomain1 possa aggiungersi a un ambiente cloud con SipDomain2 e garantire il routing corretto in un ambiente con spazio di indirizzi condiviso tra i due domini SIP.</span><span class="sxs-lookup"><span data-stu-id="6054d-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="6054d-105">Vedere il passaggio 14 in [Consolidamento cloud per Teams e Skype for Business](cloud-consolidation.md) per il contesto in cui è possibile eseguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="6054d-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="6054d-106">In questo esempio SipDomain1 è AcquiredCompany. <span> com e SipDomain2 sono OriginalCompany. <span> com.</span><span class="sxs-lookup"><span data-stu-id="6054d-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="6054d-107">Il nome soggetto alternativo (SAN) del certificato in tutti i server perimetrali nell'ambiente locale deve essere aggiornato in modo da includere tutti i domini SIP presenti nel tenant online puro (escluso qualsiasi onmicrosoft). <span> com domains), nel formato "sip. \<domain> ".</span><span class="sxs-lookup"><span data-stu-id="6054d-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="6054d-108">In questo esempio, si tratta di sip. OriginalCompany. <span> com.</span><span class="sxs-lookup"><span data-stu-id="6054d-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="6054d-109">Questo passaggio è fondamentale prima di eseguire la migrazione degli utenti nel cloud.</span><span class="sxs-lookup"><span data-stu-id="6054d-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="6054d-110">**Passaggi:**</span><span class="sxs-lookup"><span data-stu-id="6054d-110">**Steps:**</span></span>

1.  <span data-ttu-id="6054d-111">Ottenere un nuovo certificato edge esterno per il server perimetrale con tutte le voci esistenti più voci aggiuntive nella san per tutti i domini SIP nell'ambiente cloud (esclusi i domini \*.onmicrosoft.com) nel formato "sip. <DomainName> ".</span><span class="sxs-lookup"><span data-stu-id="6054d-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="6054d-112">Installare il certificato in locale in ogni server perimetrale e assegnarlo al servizio Skype Edge in ogni servizio edge.</span><span class="sxs-lookup"><span data-stu-id="6054d-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="6054d-113">Per la procedura dettagliata, vedere la sezione "Certificati dell'interfaccia perimetrale esterna" [in Deploy Edge Service in Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="6054d-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).</span></span>
3.  <span data-ttu-id="6054d-114">Riavviare il servizio Edge in ognuno dei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="6054d-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="6054d-115">È possibile eseguire questa operazione per una singola casella con i comandi di PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="6054d-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="6054d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6054d-116">See also</span></span>

[<span data-ttu-id="6054d-117">Consolidamento cloud per Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6054d-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)