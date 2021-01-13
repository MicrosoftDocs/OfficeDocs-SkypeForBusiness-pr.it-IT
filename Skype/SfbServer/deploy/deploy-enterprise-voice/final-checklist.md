---
title: Elenco di controllo per la distribuzione dei controlli di ammissione di chiamata per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Checklist finale per la distribuzione del controllo di ammissione di chiamata (CAC) in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: d3a6484e35225627c8f22002823eff7fd5939694
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830836"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="7c3f6-103">Distribuzione dei controlli di ammissione di chiamata: elenco di controllo finale per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7c3f6-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="7c3f6-104">Checklist finale per la distribuzione del controllo di ammissione di chiamata (CAC) in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="7c3f6-105">Utilizzare l'elenco di controllo seguente per verificare che siano state completate tutte le attività di configurazione necessarie per la distribuzione dei controlli di ammissione di chiamata (CAC).</span><span class="sxs-lookup"><span data-stu-id="7c3f6-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="7c3f6-106">Se uno o più server perimetrali sono distribuiti, ogni indirizzo IP dell'interfaccia esterna deve essere aggiunto all'elenco di subnet nelle impostazioni di configurazione di rete, con una maschera di bit pari a 32.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="7c3f6-107">È inoltre consigliabile associare questa subnet (indirizzo IP) all'ID sito di rete per la posizione geografica in cui è distribuito il servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7c3f6-108">I server perimetrali non sono necessari per implementare il servizio di controllo di ammissione.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="7c3f6-109">Verificare che CAC sia abilitato, come specificato in [Enable Call Admission Control in Skype for Business Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="7c3f6-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="7c3f6-110">Verificare che il servizio di controllo di ammissione sia abilitato in tutti i siti centrali.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="7c3f6-111">È possibile eseguire questa operazione tramite il generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="7c3f6-112">Se viene generato un avviso quando si  *pubblica, non*  ignorarlo.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="7c3f6-113">Verificare che tutte le subnet gestite nella rete aziendale siano configurate nelle impostazioni di configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="7c3f6-114">È inoltre essenziale che ogni subnet sia associata a un sito di rete, come spiegato in [deploy Network Regions, sites and Subnets in Skype for business](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="7c3f6-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="7c3f6-115">Verificare che la subnet o gli indirizzi IP di tutti i Front End Server, Survivable Branch Appliance (SBA), audio/video Conferencing Server (se in un pool separato) e Mediation Server siano configurati nelle impostazioni di configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="7c3f6-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

