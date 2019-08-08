---
title: Configurare il bypass multimediale con routing diretto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Leggere questo argomento per informazioni su come configurare il bypass multimediale con il routing diretto del sistema telefonico.
ms.openlocfilehash: d3991973932ec3ced2ef1a365a7060e2d9449f40
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237482"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="48280-103">Configurare il bypass multimediale con routing diretto</span><span class="sxs-lookup"><span data-stu-id="48280-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="48280-104">Prima di configurare il bypass multimediale con il routing diretto, assicurati di aver letto [piano per il bypass multimediale con routing diretto](direct-routing-plan-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="48280-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="48280-105">Per attivare il bypass multimediale, è necessario che siano soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="48280-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="48280-106">Verificare che il fornitore di Session Border Controller (SBC) di Choice supporti il bypass multimediale e fornisca istruzioni su come configurare il bypass in SBC.</span><span class="sxs-lookup"><span data-stu-id="48280-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="48280-107">Vedere la pagina certificazione per informazioni su SBCs, che supportano il bypass multimediale e per le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="48280-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="48280-108">È necessario attivare il bypass multimediale nel trunk usando il comando seguente: **set-CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**.</span><span class="sxs-lookup"><span data-stu-id="48280-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="48280-109">Verificare che le porte necessarie vengano aperte.</span><span class="sxs-lookup"><span data-stu-id="48280-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="48280-110">Eseguire la migrazione da trunk non bypassati a trunk abilitati per bypass</span><span class="sxs-lookup"><span data-stu-id="48280-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="48280-111">Puoi cambiare tutti gli utenti contemporaneamente oppure puoi implementare un approccio graduale (consigliato).</span><span class="sxs-lookup"><span data-stu-id="48280-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="48280-112">**Cambiare tutti gli utenti contemporaneamente.**</span><span class="sxs-lookup"><span data-stu-id="48280-112">**Switch all users at once.**</span></span> <span data-ttu-id="48280-113">Se tutte le condizioni sono soddisfatte, è possibile attivare la modalità bypass.</span><span class="sxs-lookup"><span data-stu-id="48280-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="48280-114">Tutti gli utenti della produzione verranno comunque cambiati in contemporanea.</span><span class="sxs-lookup"><span data-stu-id="48280-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="48280-115">Poiché potrebbero verificarsi alcuni problemi inizialmente quando si configurano trunk e porte, l'esperienza utente di produzione potrebbe essere interessata.</span><span class="sxs-lookup"><span data-stu-id="48280-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="48280-116">**Approccio graduale. (Scelta consigliata)**.</span><span class="sxs-lookup"><span data-stu-id="48280-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="48280-117">Creare un nuovo trunk per lo stesso SBC (con una porta diversa), testarlo e modificare i criteri di routing vocale online per gli utenti in modo che puntino al nuovo trunk.</span><span class="sxs-lookup"><span data-stu-id="48280-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="48280-118">Questo è l'approccio consigliato perché consente una transizione più fluida e un'esperienza utente senza interruzioni.</span><span class="sxs-lookup"><span data-stu-id="48280-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="48280-119">Questo approccio richiede la configurazione di SBC, un nuovo nome FQDN e la configurazione del firewall.</span><span class="sxs-lookup"><span data-stu-id="48280-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="48280-120">Nota sarà necessario verificare che il certificato supporti entrambi i trunk.</span><span class="sxs-lookup"><span data-stu-id="48280-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="48280-121">In SAN è necessario avere due nomi (**sbc1.contoso.com** e **sbc2.contoso.com**) o avere un certificato con carattere jolly.</span><span class="sxs-lookup"><span data-stu-id="48280-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Eseguire la migrazione da trunk non bypassati a trunk abilitati per bypass)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="48280-123">Per istruzioni su come configurare i trunk ed eseguire la migrazione, vedere la documentazione del fornitore di SBC:</span><span class="sxs-lookup"><span data-stu-id="48280-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="48280-124">Documentazione di distribuzione di AudioCodes</span><span class="sxs-lookup"><span data-stu-id="48280-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="48280-125">Documentazione di distribuzione Oracle</span><span class="sxs-lookup"><span data-stu-id="48280-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="48280-126">Documentazione sulla distribuzione delle comunicazioni della barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="48280-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="48280-127">Documentazione sulla distribuzione di TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="48280-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="48280-128">Per un elenco di Session Border Controller (SBCs) Certified for Direct routing, vedere l' [elenco dei controller di sessione Broder certificati per il routing diretto](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="48280-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="see-also"></a><span data-ttu-id="48280-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48280-129">See also</span></span>

[<span data-ttu-id="48280-130">Pianificare il bypass multimediale con routing diretto</span><span class="sxs-lookup"><span data-stu-id="48280-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



