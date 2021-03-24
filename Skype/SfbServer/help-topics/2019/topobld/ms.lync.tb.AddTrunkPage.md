---
title: Definire un nuovo trunk
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'È possibile definire un nuovo trunk SIP (Session Initiation Protocol) fornendo le informazioni seguenti:'
ms.openlocfilehash: 540076814d2916f74a5e11be42f99b57711da2b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093274"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="25bc3-103">Definire un nuovo trunk</span><span class="sxs-lookup"><span data-stu-id="25bc3-103">Define a New Trunk</span></span>

<span data-ttu-id="25bc3-104">È possibile definire un nuovo trunk SIP (Session Initiation Protocol) fornendo le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="25bc3-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="25bc3-105">**Nome trunk**: nome univoco nella topologia che identificherà questo trunk</span><span class="sxs-lookup"><span data-stu-id="25bc3-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="25bc3-106">**Gateway PSTN associato**: selezionare un gateway PSTN distribuito e configurato nella distribuzione dall'elenco</span><span class="sxs-lookup"><span data-stu-id="25bc3-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="25bc3-107">**Porta di attesa per il gateway IP/PSTN**: porta su cui il gateway IP-PBX o PSTN sarà in ascolto.</span><span class="sxs-lookup"><span data-stu-id="25bc3-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="25bc3-108">Deve essere univoco da tutte le altre porte di attesa trunk configurate nella distribuzione</span><span class="sxs-lookup"><span data-stu-id="25bc3-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="25bc3-109">**Protocollo di trasporto SIP**: selezionare nell'elenco TCP o TLS</span><span class="sxs-lookup"><span data-stu-id="25bc3-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="25bc3-110">**Mediation Server associato:** selezionare nell'elenco un Mediation Server distribuito e configurato nella distribuzione</span><span class="sxs-lookup"><span data-stu-id="25bc3-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="25bc3-111">**Porta Mediation Server associata**: impostare il valore della porta uguale al valore della porta TCP o TLS del Mediation Server che verrà utilizzato da questo trunk SIP</span><span class="sxs-lookup"><span data-stu-id="25bc3-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="25bc3-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25bc3-112">See also</span></span>

[<span data-ttu-id="25bc3-113">M:N trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="25bc3-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="25bc3-114">Come si implementa il trunking SIP?</span><span class="sxs-lookup"><span data-stu-id="25bc3-114">How do I implement SIP trunking?</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)