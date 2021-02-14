---
title: Configurare la federazione per un provider di servizi di audioconferenza nella distribuzione ibrida
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Riepilogo: informazioni su come configurare la federazione per un provider di servizi di audioconferenza in Skype for Business online.'
ms.openlocfilehash: a19704327d1cf5591a1ebb3f62aa23f46fe09d10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726886"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="8c092-103">Configurare la federazione per un provider di servizi di audioconferenza nella distribuzione ibrida</span><span class="sxs-lookup"><span data-stu-id="8c092-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="8c092-104">**Riepilogo:** Informazioni su come configurare la federazione per un provider di servizi di audioconferenza in Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="8c092-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="8c092-105">Se si desidera utilizzare un Provider di servizi di audioconferenza (ACP) nella distribuzione ibrida (locale con online), è necessario configurare la federazione tra la distribuzione locale e il partner ACP come server partner consentito.</span><span class="sxs-lookup"><span data-stu-id="8c092-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="8c092-106">È possibile configurare la federazione aggiungendo il dominio del partner ACP e il server perimetrale (denominato anche proxy di accesso) all'elenco Domini federati per la distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="8c092-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="8c092-107">Il partner ACP deve quindi aggiungere il nome di dominio completo del pool di server perimetrali locali all'elenco dei domini federati consentiti.</span><span class="sxs-lookup"><span data-stu-id="8c092-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="8c092-108">Per ulteriori dettagli, contattare il provider ACP.</span><span class="sxs-lookup"><span data-stu-id="8c092-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="8c092-109">Il partner ACP deve quindi aggiungere il nome di dominio completo del pool di server perimetrali locali all'elenco dei domini federati consentiti.</span><span class="sxs-lookup"><span data-stu-id="8c092-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="8c092-110">**Aggiunta del dominio ACP e del server perimetrale come dominio federato consentito**</span><span class="sxs-lookup"><span data-stu-id="8c092-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="8c092-111">Per aggiungere il dominio ACP come server partner consentito (dominio federato consentito), seguire la procedura descritta in Configurare il supporto [per i domini esterni consentiti.](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)</span><span class="sxs-lookup"><span data-stu-id="8c092-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="8c092-112">Per il server perimetrale, aggiungere il nome di dominio completo del server perimetrale del partner ACP.</span><span class="sxs-lookup"><span data-stu-id="8c092-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="8c092-113">Potrebbe essere necessario contattare il partner ACP per ottenere il nome di dominio completo per il server perimetrale, che può anche essere indicato dal proprio ACP come proxy di accesso.</span><span class="sxs-lookup"><span data-stu-id="8c092-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="8c092-114">**Fornire l'FQDN del pool di server perimetrali al partner ACP**</span><span class="sxs-lookup"><span data-stu-id="8c092-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="8c092-115">Il partner ACP deve configurare la federazione per aggiungere il dominio locale come server partner consentito aggiungendo il nome di dominio completo del pool di server perimetrali come dominio federato consentito.</span><span class="sxs-lookup"><span data-stu-id="8c092-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


