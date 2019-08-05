---
title: Configurare la Federazione per un provider di servizi di audioconferenza nella distribuzione ibrida
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
description: 'Riepilogo: informazioni su come configurare la Federazione per un provider di servizi di audioconferenza in Skype for business online.'
ms.openlocfilehash: faeae07c0662bc252e07bbf66ec463355e439461
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185462"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="51b0e-103">Configurare la Federazione per un provider di servizi di audioconferenza nella distribuzione ibrida</span><span class="sxs-lookup"><span data-stu-id="51b0e-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="51b0e-104">**Riepilogo:** Informazioni su come configurare la Federazione per un provider di servizi di audioconferenza in Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="51b0e-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="51b0e-105">Se si vuole usare un provider di servizi di audioconferenza (ACP) nella distribuzione ibrida (locale con online), è necessario configurare la Federazione tra la distribuzione locale e il partner ACP come server partner consentito.</span><span class="sxs-lookup"><span data-stu-id="51b0e-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="51b0e-106">È possibile configurare la Federazione aggiungendo il dominio partner ACP e il server perimetrale (può anche essere chiamato proxy di accesso) nell'elenco dei domini federati per la distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="51b0e-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="51b0e-107">Il partner ACP deve quindi aggiungere il nome di dominio completo del pool di Edge Server locale all'elenco dei domini federati consentiti.</span><span class="sxs-lookup"><span data-stu-id="51b0e-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="51b0e-108">Per ulteriori informazioni, contattare il provider ACP.</span><span class="sxs-lookup"><span data-stu-id="51b0e-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="51b0e-109">Il partner ACP deve quindi aggiungere il nome di dominio completo del pool di Edge Server locale all'elenco dei domini federati consentiti.</span><span class="sxs-lookup"><span data-stu-id="51b0e-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="51b0e-110">**Aggiunta del dominio ACP e del server perimetrale come dominio federato consentito**</span><span class="sxs-lookup"><span data-stu-id="51b0e-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="51b0e-111">Per aggiungere il dominio ACP come server partner consentito (dominio federato consentito), seguire i passaggi descritti in [configurare il supporto per i domini esterni](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)consentiti.</span><span class="sxs-lookup"><span data-stu-id="51b0e-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="51b0e-112">Per il server perimetrale, aggiungere il nome di dominio completo del server Edge del partner ACP.</span><span class="sxs-lookup"><span data-stu-id="51b0e-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="51b0e-113">Potrebbe essere necessario contattare il partner ACP per ottenere il nome di dominio completo per il server perimetrale, che può anche essere indicato dal proprio proxy di accesso per i paesi ACP.</span><span class="sxs-lookup"><span data-stu-id="51b0e-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="51b0e-114">**Fornire il nome di dominio completo del pool di Edge Server al partner ACP**</span><span class="sxs-lookup"><span data-stu-id="51b0e-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="51b0e-115">Il partner ACP deve configurare la Federazione per aggiungere il dominio locale come server partner consentito aggiungendo il nome FQDN del pool di Edge Server come dominio federato consentito.</span><span class="sxs-lookup"><span data-stu-id="51b0e-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


