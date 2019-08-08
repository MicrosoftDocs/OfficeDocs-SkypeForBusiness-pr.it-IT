---
title: Elenco di controllo per la distribuzione dei controlli di ammissione di chiamata per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Elenco di controllo finale per la distribuzione di controlli di ammissione di chiamata (CAC) in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 275afdfcb3c5e2b7cc635e073bcb5b9ba5edc853
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240569"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="bc0a5-103">Distribuzione del controllo di ammissione alle chiamate: elenco di verifica finale per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bc0a5-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="bc0a5-104">Elenco di controllo finale per la distribuzione di controlli di ammissione di chiamata (CAC) in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="bc0a5-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="bc0a5-105">Usare l'elenco di controllo seguente per verificare di aver completato tutte le attività di configurazione necessarie per distribuire il controllo di ammissione di chiamata (CAC).</span><span class="sxs-lookup"><span data-stu-id="bc0a5-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="bc0a5-106">Se vengono distribuiti uno o più Edge Server, ogni indirizzo IP dell'interfaccia esterna deve essere aggiunto all'elenco subnet nelle impostazioni di configurazione della rete, con una maschera di bit di 32.</span><span class="sxs-lookup"><span data-stu-id="bc0a5-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="bc0a5-107">Devi anche associare questa subnet (indirizzo IP) con l'ID sito di rete per la posizione geografica in cui è distribuito il servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="bc0a5-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bc0a5-108">I server perimetrali non sono obbligatori per implementare CAC.</span><span class="sxs-lookup"><span data-stu-id="bc0a5-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="bc0a5-109">Verificare che CAC sia abilitato, come specificato in [Abilita controllo ammissione chiamata in Skype for Business Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="bc0a5-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="bc0a5-110">Verificare che CAC sia abilitato in tutti i siti centrali.</span><span class="sxs-lookup"><span data-stu-id="bc0a5-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="bc0a5-111">Questa operazione può essere eseguita tramite il generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="bc0a5-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="bc0a5-112">Se viene generato un avviso durante la pubblicazione, *non* ignorarlo.</span><span class="sxs-lookup"><span data-stu-id="bc0a5-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="bc0a5-113">Verificare che tutte le subnet gestite nella rete aziendale siano configurate nelle impostazioni di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="bc0a5-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="bc0a5-114">È anche essenziale che ogni subnet sia associata a un sito di rete, come spiegato in [distribuire aree di rete, siti e subnet in Skype for business](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="bc0a5-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="bc0a5-115">Verificare che la subnet o gli indirizzi IP di tutti i server front-end, Survivable Branch Appliances (SBAs), audio/video Conferencing Servers (se in un pool separato) e Mediation Server siano configurati nelle impostazioni di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="bc0a5-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

