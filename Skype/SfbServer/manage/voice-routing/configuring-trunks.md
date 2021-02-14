---
title: Configurazione dei trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Come parte della distribuzione di VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più peer per fornire connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi VoIP aziendale nell'organizzazione.
ms.openlocfilehash: 57b8635d635c0fd0b8c41c95f92af768ff84dfd4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800116"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="0248d-103">Configurazione dei trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0248d-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="0248d-104">Nell'ambito della distribuzione di VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più dei peer seguenti per fornire connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi VoIP aziendale nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="0248d-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="0248d-105">Connessione con trunk SIP a un provider di servizi di telefonia Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="0248d-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="0248d-106">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="0248d-106">PSTN gateway</span></span>
- <span data-ttu-id="0248d-107">Centralino (PBX)</span><span class="sxs-lookup"><span data-stu-id="0248d-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="0248d-108">Per informazioni dettagliate, vedere [Pianificare la connettività PSTN in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)</span><span class="sxs-lookup"><span data-stu-id="0248d-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0248d-109">Prima di iniziare la configurazione del trunk, verificare che la topologia sia stata creata e che il Mediation Server e il relativo peer siano stati configurati e associati l'uno all'altro.</span><span class="sxs-lookup"><span data-stu-id="0248d-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="0248d-110">Per informazioni dettagliate, [vedere Definire un gateway in Generatore di topologie in Skype for Business Server.](../../deploy/deploy-enterprise-voice/define-a-gateway.md)</span><span class="sxs-lookup"><span data-stu-id="0248d-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0248d-111">Come parte della configurazione trunk, è possibile abilitare la funzionalità di bypass multimediale di Skype for Business Server, che consente agli elementi multimediali di ignorare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="0248d-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="0248d-112">I trunk possono essere configurati con o senza il bypass multimediale abilitato, ma è consigliabile abilitarlo.</span><span class="sxs-lookup"><span data-stu-id="0248d-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="0248d-113">Per informazioni dettagliate, vedere [Pianificare il bypass multimediale in Skype for Business.](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="0248d-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
