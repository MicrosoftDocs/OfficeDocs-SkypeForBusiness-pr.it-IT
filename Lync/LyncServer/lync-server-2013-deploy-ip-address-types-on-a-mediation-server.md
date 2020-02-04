---
title: 'Lync Server 2013: Distribuire i tipi di indirizzi IP in un Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab30a2153dc7dbf5a15557f6eeaf3b6cb65f68f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a><span data-ttu-id="10a1e-102">Distribuire i tipi di indirizzi IP in un Mediation Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10a1e-102">Deploy IP address types on a Mediation Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10a1e-103">_**Argomento Ultima modifica:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="10a1e-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="10a1e-104">Usando generatore di topologie, eseguire i passaggi descritti nella procedura seguente per distribuire i tipi di indirizzo IP in un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="10a1e-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="10a1e-105">Per distribuire i tipi di indirizzo IP in un Mediation Server</span><span class="sxs-lookup"><span data-stu-id="10a1e-105">To deploy IP address types on a Mediation Server</span></span>

  - <span data-ttu-id="10a1e-106">In Generatore di topologia, in **pool di mediazione**, fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="10a1e-106">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="10a1e-107">In alternativa, selezionare il server e quindi fare clic su **modifica proprietà** dal menu **azione** .</span><span class="sxs-lookup"><span data-stu-id="10a1e-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

  - <span data-ttu-id="10a1e-108">Nella finestra di dialogo **modifica proprietà** selezionare il tipo di indirizzo IP che si vuole configurare.</span><span class="sxs-lookup"><span data-stu-id="10a1e-108">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="10a1e-109">Per una configurazione a doppio stack, selezionare **Abilita IPv4** e **Abilita IPv6**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="10a1e-109">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="10a1e-110">**Finestra di dialogo Modifica proprietà per il pool di Mediation Server**</span><span class="sxs-lookup"><span data-stu-id="10a1e-110">**Edit Properties dialog box for the Mediation Server pool**</span></span>
    
    <span data-ttu-id="10a1e-111">![Pagina delle proprietà generali di Lync Server con FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Pagina delle proprietà generali di Lync Server con FQDN")</span><span class="sxs-lookup"><span data-stu-id="10a1e-111">![Lync Server general properties page with FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Lync Server general properties page with FQDN")</span></span>
    
      - <span data-ttu-id="10a1e-112">**Usare tutti gli indirizzi IP configurati**.</span><span class="sxs-lookup"><span data-stu-id="10a1e-112">**Use all configured IP addresses**.</span></span> <span data-ttu-id="10a1e-113">Selezionare questa opzione se si vuole consentire l'uso di qualsiasi indirizzo IP definito nel computer.</span><span class="sxs-lookup"><span data-stu-id="10a1e-113">Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="10a1e-114">Questa è l'opzione consigliata per le configurazioni IP versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="10a1e-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="10a1e-115">**Limitare l'utilizzo del servizio agli indirizzi IP selezionati**.</span><span class="sxs-lookup"><span data-stu-id="10a1e-115">**Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="10a1e-116">Selezionare questa opzione per specificare un indirizzo specifico da usare nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="10a1e-116">Select this option to specify a specific address to use on the new server.</span></span> <span data-ttu-id="10a1e-117">Se si seleziona questa opzione, è necessario immettere un valore per l'indirizzo IP principale.</span><span class="sxs-lookup"><span data-stu-id="10a1e-117">If you select this option, you must enter a value for Primary IP address.</span></span>
    
      - <span data-ttu-id="10a1e-118">**Indirizzo IP principale**.</span><span class="sxs-lookup"><span data-stu-id="10a1e-118">**Primary IP address**.</span></span> <span data-ttu-id="10a1e-119">Immettere un indirizzo IP che il server userà per tutte le comunicazioni eccetto PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="10a1e-119">Enter an IP address that the server will use for all communications except public switched telephone network (PSTN).</span></span> <span data-ttu-id="10a1e-120">L'indirizzo IP immesso deve corrispondere al formato del tipo di indirizzo di selezione.</span><span class="sxs-lookup"><span data-stu-id="10a1e-120">The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="10a1e-121">**Indirizzo IP PSTN**.</span><span class="sxs-lookup"><span data-stu-id="10a1e-121">**PSTN IP address**.</span></span> <span data-ttu-id="10a1e-122">Definire un indirizzo IP PSTN quando un Mediation Server è autonomo.</span><span class="sxs-lookup"><span data-stu-id="10a1e-122">Define a PSTN IP address when a Mediation Server is standalone.</span></span> <span data-ttu-id="10a1e-123">Questo indirizzo deve corrispondere al formato del tipo di indirizzo selezionato.</span><span class="sxs-lookup"><span data-stu-id="10a1e-123">This address must match the format of the selected address type.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="10a1e-124">L'installazione di altre schede di interfaccia di rete (NIC) per supportare la configurazione degli indirizzi IP PSTN per Lync Server 2013 non è supportata nei ruoli di Mediation Server collocati.</span><span class="sxs-lookup"><span data-stu-id="10a1e-124">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="10a1e-125">Per altre informazioni sulle configurazioni di NIC supportate per Lync Server 2013, vedere <A href="lync-server-2013-server-hardware-platforms.md">piattaforme hardware del server per Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="10a1e-125">For more information about supported NIC configurations for Lync Server 2013, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

