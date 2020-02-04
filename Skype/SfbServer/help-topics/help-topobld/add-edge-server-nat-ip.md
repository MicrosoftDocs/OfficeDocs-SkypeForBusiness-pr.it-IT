---
title: Aggiungere Edge Server NAT IP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: L'indirizzo IP pubblico è l'indirizzo IP usato da NAT (Network Address Translation). L'indirizzo IP deve essere instradabile pubblicamente. Questa operazione è necessaria perché è stato selezionato l'indirizzo IP esterno di questo pool di bordi viene tradotto dall'opzione NAT nella pagina Seleziona caratteristiche della procedura guidata.
ms.openlocfilehash: f2e5a00b4e7c91f2343b9c917f6249d2ecee8930
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698401"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="d6346-105">Aggiungere Edge Server NAT IP</span><span class="sxs-lookup"><span data-stu-id="d6346-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="d6346-106">L'indirizzo IP pubblico è l'indirizzo IP usato da NAT (Network Address Translation).</span><span class="sxs-lookup"><span data-stu-id="d6346-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="d6346-107">L'indirizzo IP deve essere instradabile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="d6346-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="d6346-108">Questa operazione è necessaria perché è stato selezionato **l'indirizzo IP esterno di questo pool di bordi viene tradotto dall'opzione NAT** nella pagina **Seleziona caratteristiche** della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="d6346-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="d6346-109">NAT (Network Address Translation) Abilita client o server in una rete privata, ad esempio l'intervallo 192.168.0.0, per comunicare con sistemi su reti remote tramite le reti Internet pubbliche.</span><span class="sxs-lookup"><span data-stu-id="d6346-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="d6346-110">NAT funziona usando un singolo indirizzo IP pubblico su un'interfaccia esterna e associando indirizzi IP interni con l'unico indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="d6346-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="d6346-111">Il mapping NAT associa un indirizzo interno all'indirizzo IP pubblico esterno.</span><span class="sxs-lookup"><span data-stu-id="d6346-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="d6346-112">Il sistema remoto Visualizza solo l'indirizzo pubblico dell'origine.</span><span class="sxs-lookup"><span data-stu-id="d6346-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="d6346-113">Il sistema remoto risponde all'origine e la fonte si riferisce alla mappa NAT per determinare l'indirizzo IP interno a cui deve essere restituita la risposta.</span><span class="sxs-lookup"><span data-stu-id="d6346-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="d6346-p104">È possibile aggiungere il supporto per l'accesso degli utenti esterni durante o dopo la distribuzione della topologia iniziale. Per informazioni dettagliate sull'aggiunta di server perimetrali a una topologia esistente, vedere [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) nella documentazione relativa alla distribuzione di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="d6346-p104">You can add support for external user access when you deploy your initial topology or afterward. For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


