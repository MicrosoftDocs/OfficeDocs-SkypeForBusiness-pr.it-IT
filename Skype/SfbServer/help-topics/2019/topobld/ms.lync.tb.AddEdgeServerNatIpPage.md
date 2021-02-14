---
title: Aggiungere l'indirizzo IP di NAT del server perimetrale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: L'indirizzo IP pubblico è l'indirizzo IP utilizzato da Network Address Translation (NAT). L'indirizzo IP deve essere instradabile pubblicamente. Questa operazione è necessaria perché è stata selezionata l'opzione Indirizzo IP del pool Edge Server convertito da NAT nella pagina Selezione funzionalità di questa procedura guidata.
ms.openlocfilehash: 1e722a997346daadedf1f017a66f85d6a7355e18
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800966"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="c3d77-105">Aggiungere Edge Server NAT IP</span><span class="sxs-lookup"><span data-stu-id="c3d77-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="c3d77-p102">L'indirizzo IP pubblico è l'indirizzo IP utilizzato da Network Address Translation (NAT). L'indirizzo IP deve essere instradabile pubblicamente. Questa operazione è necessaria perché è stata selezionata l'opzione **Indirizzo IP del pool Edge Server convertito da NAT** nella pagina **Selezione funzionalità** di questa procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="c3d77-p102">The public IP address is the IP address that is used by network address translation (NAT). The IP address must be publicly routable. This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="c3d77-109">Nat (Network Address Translation) consente ai client o ai server in una rete privata (ad esempio, l'intervallo 192.168.0.0) di comunicare con i sistemi su reti remote tramite le reti Internet pubbliche.</span><span class="sxs-lookup"><span data-stu-id="c3d77-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="c3d77-110">NAT funziona utilizzando un solo indirizzo IP pubblico su un'interfaccia esterna e associando gli indirizzi IP interni a quell'unico indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="c3d77-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="c3d77-111">Il mapping NAT associa un indirizzo interno all'indirizzo IP pubblico esterno.</span><span class="sxs-lookup"><span data-stu-id="c3d77-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="c3d77-112">Il sistema remoto vede solo l'indirizzo pubblico dell'origine.</span><span class="sxs-lookup"><span data-stu-id="c3d77-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="c3d77-113">Risponde pertanto all'origine e questa, a sua volta, fa riferimento alla mappa NAT per determinare l'indirizzo IP interno a cui deve essere restituita la risposta.</span><span class="sxs-lookup"><span data-stu-id="c3d77-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="c3d77-114">È possibile aggiungere il supporto dell'accesso utente esterno quando si distribuisce la topologia iniziale o successivamente.</span><span class="sxs-lookup"><span data-stu-id="c3d77-114">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="c3d77-115">Per informazioni dettagliate sull'aggiunta di server perimetrali a una topologia esistente, vedere [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) nella documentazione relativa alla distribuzione di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="c3d77-115">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


