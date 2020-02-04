---
title: Definire un nuovo trunk
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Si definisce un nuovo trunk SIP (Session Initiation Protocol) fornendo le informazioni seguenti:'
ms.openlocfilehash: 9de4808bc7a53aae79c2373116e74be98c7ae9ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684839"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="4809e-103">Definire un nuovo trunk</span><span class="sxs-lookup"><span data-stu-id="4809e-103">Define a New Trunk</span></span>

<span data-ttu-id="4809e-104">Si definisce un nuovo trunk SIP (Session Initiation Protocol) fornendo le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4809e-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="4809e-105">**Trunk Name**: nome univoco nella topologia che identificherà questo trunk</span><span class="sxs-lookup"><span data-stu-id="4809e-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="4809e-106">**Gateway PSTN associato**: selezionare un gateway PSTN distribuito e configurato nella distribuzione dall'elenco</span><span class="sxs-lookup"><span data-stu-id="4809e-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="4809e-107">**Porta di ascolto per il gateway IP/PSTN**: porta che verrà ascoltata dal gateway IP-PBX o PSTN.</span><span class="sxs-lookup"><span data-stu-id="4809e-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="4809e-108">Deve essere univoco da tutte le altre porte di ascolto del trunk configurate nella distribuzione</span><span class="sxs-lookup"><span data-stu-id="4809e-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="4809e-109">**Protocollo di trasporto SIP**: selezionare dall'elenco TCP o TLS</span><span class="sxs-lookup"><span data-stu-id="4809e-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="4809e-110">**Mediation Server associato**: selezionare dall'elenco un Mediation Server distribuito e configurato nella distribuzione</span><span class="sxs-lookup"><span data-stu-id="4809e-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="4809e-111">**Porta Mediation Server associata**: imposta il valore della porta uguale al valore della porta TCP o TLS del server di mediazione che verrà usato da questo trunk SIP</span><span class="sxs-lookup"><span data-stu-id="4809e-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="4809e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4809e-112">See also</span></span>

[<span data-ttu-id="4809e-113">Trunk con relazioni molti-a-molti in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4809e-113">M:N trunk in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="4809e-114">Come implementare il trunking SIP</span><span class="sxs-lookup"><span data-stu-id="4809e-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
