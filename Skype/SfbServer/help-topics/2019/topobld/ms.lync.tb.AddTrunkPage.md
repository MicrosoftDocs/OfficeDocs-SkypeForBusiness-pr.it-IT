---
title: Definire un nuovo trunk
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Si definisce un nuovo trunk SIP (Session Initiation Protocol) fornendo le informazioni seguenti:'
ms.openlocfilehash: 17f6b72f1234813e717cfc72be60bb5f0352134a
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794315"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="3bb24-103">Definire un nuovo trunk</span><span class="sxs-lookup"><span data-stu-id="3bb24-103">Define a New Trunk</span></span>

<span data-ttu-id="3bb24-104">Si definisce un nuovo trunk SIP (Session Initiation Protocol) fornendo le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3bb24-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="3bb24-105">**Trunk Name**: nome univoco nella topologia che identificherà questo trunk</span><span class="sxs-lookup"><span data-stu-id="3bb24-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="3bb24-106">**Gateway PSTN associato**: selezionare un gateway PSTN distribuito e configurato nella distribuzione dall'elenco</span><span class="sxs-lookup"><span data-stu-id="3bb24-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="3bb24-107">**Porta di ascolto per il gateway IP/PSTN**: porta che verrà ascoltata dal gateway IP-PBX o PSTN.</span><span class="sxs-lookup"><span data-stu-id="3bb24-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="3bb24-108">Deve essere univoco da tutte le altre porte di ascolto del trunk configurate nella distribuzione</span><span class="sxs-lookup"><span data-stu-id="3bb24-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="3bb24-109">**Protocollo di trasporto SIP**: selezionare dall'elenco TCP o TLS</span><span class="sxs-lookup"><span data-stu-id="3bb24-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="3bb24-110">**Mediation Server associato**: selezionare dall'elenco un Mediation Server distribuito e configurato nella distribuzione</span><span class="sxs-lookup"><span data-stu-id="3bb24-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="3bb24-111">**Porta Mediation Server associata**: imposta il valore della porta uguale al valore della porta TCP o TLS del server di mediazione che verrà usato da questo trunk SIP</span><span class="sxs-lookup"><span data-stu-id="3bb24-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="3bb24-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bb24-112">See also</span></span>

[<span data-ttu-id="3bb24-113">Trunk M:N in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3bb24-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="3bb24-114">Come implementare il trunking SIP</span><span class="sxs-lookup"><span data-stu-id="3bb24-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
