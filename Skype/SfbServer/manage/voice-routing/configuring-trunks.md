---
title: Configurazione di Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Come parte della distribuzione di VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più peer per consentire la connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi VoIP aziendali nell'organizzazione.
ms.openlocfilehash: 41e92f994606ea2153359546d408335d13a21f88
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817016"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="b1e64-103">Configurazione di Trunks in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b1e64-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="b1e64-104">Come parte della distribuzione VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più dei peer seguenti per consentire la connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi VoIP aziendali nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="b1e64-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="b1e64-105">Connessione trunk SIP a un provider di servizi di telefonia Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="b1e64-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="b1e64-106">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="b1e64-106">PSTN gateway</span></span>
- <span data-ttu-id="b1e64-107">PBX (Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="b1e64-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="b1e64-108">Per informazioni dettagliate, vedere [pianificare la connettività PSTN in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="b1e64-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1e64-109">Prima di iniziare la configurazione del trunk, verificare che la topologia sia stata creata e che il Mediation Server e il relativo peer siano stati configurati e associati tra loro.</span><span class="sxs-lookup"><span data-stu-id="b1e64-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="b1e64-110">Per informazioni dettagliate, vedere [definire un gateway in Generatore di topologia in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="b1e64-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b1e64-111">Come parte della configurazione trunk, puoi abilitare la caratteristica di bypass multimediale Skype for Business Server, che consente ai media di aggirare il server Mediation.</span><span class="sxs-lookup"><span data-stu-id="b1e64-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="b1e64-112">I trunk possono essere configurati con o senza bypass multimediale abilitato, ma ti consigliamo vivamente di abilitarlo.</span><span class="sxs-lookup"><span data-stu-id="b1e64-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="b1e64-113">Per informazioni dettagliate, vedere [pianificare il bypass multimediale in Skype for business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="b1e64-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
