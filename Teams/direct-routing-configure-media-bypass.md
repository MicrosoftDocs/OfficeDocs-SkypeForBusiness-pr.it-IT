---
title: Configurare il bypass multimediale con Instradamento diretto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Scopri come configurare il bypass multimediale con il routing diretto del sistema telefonico per Microsoft Teams passando contemporaneamente a tutti gli utenti o implementando un approccio a fasi (scelta consigliata).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416896"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="4e9e8-103">Configurare il bypass multimediale con Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="4e9e8-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="4e9e8-104">Prima di configurare il bypass multimediale con il routing diretto, assicurarsi di avere letto [Pianificare il bypass multimediale con Routing diretto.](direct-routing-plan-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="4e9e8-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="4e9e8-105">Per attivare il bypass multimediale, è necessario che siano soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e9e8-105">To turn on media bypass, the following conditions must be met:</span></span>

1.    <span data-ttu-id="4e9e8-106">Assicurarsi che il proprio fornitore di Session Border Controller (SBC) supporti il bypass multimediale e fornisce istruzioni su come configurare il bypass sul controller SBC.</span><span class="sxs-lookup"><span data-stu-id="4e9e8-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="4e9e8-107">Per istruzioni, consulta la pagina di certificazione per informazioni su SBC, che supportano il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="4e9e8-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.    <span data-ttu-id="4e9e8-108">È necessario attivare il bypass multimediale sul trunk con il comando seguente: **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true.**</span><span class="sxs-lookup"><span data-stu-id="4e9e8-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.    <span data-ttu-id="4e9e8-109">Assicurarsi che le porte richieste siano aperte.</span><span class="sxs-lookup"><span data-stu-id="4e9e8-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="4e9e8-110">Eseguire la migrazione da trunk non bypassati a trunk abilitati per bypass</span><span class="sxs-lookup"><span data-stu-id="4e9e8-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="4e9e8-111">È possibile cambiare tutti gli utenti contemporaneamente oppure implementare un approccio a fasi (scelta consigliata).</span><span class="sxs-lookup"><span data-stu-id="4e9e8-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="4e9e8-112">**Cambiare tutti gli utenti contemporaneamente.**</span><span class="sxs-lookup"><span data-stu-id="4e9e8-112">**Switch all users at once.**</span></span> <span data-ttu-id="4e9e8-113">Se vengono soddisfatte tutte le condizioni, è possibile attivare la modalità bypass.</span><span class="sxs-lookup"><span data-stu-id="4e9e8-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="4e9e8-114">Tuttavia, tutti gli utenti di produzione verranno alternati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="4e9e8-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="4e9e8-115">Poiché inizialmente potrebbero verificarsi alcuni problemi durante la configurazione di trunk e porte, l'esperienza utente di produzione potrebbe risultare interessata.</span><span class="sxs-lookup"><span data-stu-id="4e9e8-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="4e9e8-116">**Approccio a fasi. (Scelta consigliata).**</span><span class="sxs-lookup"><span data-stu-id="4e9e8-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="4e9e8-117">Creare un nuovo trunk per lo stesso SBC (con una porta diversa), testarlo e modificare i criteri di routing vocale online in modo che gli utenti puntino al nuovo trunk.</span><span class="sxs-lookup"><span data-stu-id="4e9e8-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="4e9e8-118">Questo è l'approccio consigliato perché consente una transizione più fluida e un'esperienza utente senza interruzioni.</span><span class="sxs-lookup"><span data-stu-id="4e9e8-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="4e9e8-119">Questo approccio richiede la configurazione del servizio SBC, di un nuovo nome FQDN e della configurazione del firewall.</span><span class="sxs-lookup"><span data-stu-id="4e9e8-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="4e9e8-120">Tenere presente che è necessario verificare che il certificato supporti entrambi i trunk.</span><span class="sxs-lookup"><span data-stu-id="4e9e8-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="4e9e8-121">In SAN è necessario avere due nomi (**sbc1.contoso.com** e **sbc2.contoso.com**) o un certificato con caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="4e9e8-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Eseguire la migrazione da trunk non bypassati a trunk abilitati per bypass)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="4e9e8-123">Per istruzioni su come configurare i trunk ed eseguire la migrazione, vedere la documentazione del fornitore di SBC:</span><span class="sxs-lookup"><span data-stu-id="4e9e8-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="4e9e8-124">Documentazione sulla distribuzione di AudioCodes</span><span class="sxs-lookup"><span data-stu-id="4e9e8-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="4e9e8-125">Documentazione della distribuzione Oracle</span><span class="sxs-lookup"><span data-stu-id="4e9e8-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="4e9e8-126">Documentazione sulla distribuzione di Ribbon Communications</span><span class="sxs-lookup"><span data-stu-id="4e9e8-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="4e9e8-127">Documentazione sulla distribuzione di TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="4e9e8-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="4e9e8-128">Per un elenco dei controller dei confini della sessione (SBC) certificati per l'instradamento diretto, vedere l'elenco dei controller di bordo di sessione certificati per [l'instradamento diretto.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="4e9e8-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="4e9e8-129">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4e9e8-129">Related topics</span></span>

[<span data-ttu-id="4e9e8-130">Pianificare il bypass multimediale con l'instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="4e9e8-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



