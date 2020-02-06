---
title: Espansione delle impostazioni del computer perimetrale per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: "Per modificare le proprietà dei computer Edge Server come un singolo Edge Server o come computer membri in un pool di Edge, è possibile configurare le impostazioni di configurazione del nome del server e dell'indirizzo IP:"
ms.openlocfilehash: b90a3a00dcb1198e696112fc3d3ded08ff00060d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820098"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="03017-103">Espansione delle impostazioni del computer perimetrale per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="03017-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="03017-104">Per modificare le proprietà dei computer Edge Server come un singolo Edge Server o come computer membri in un pool di Edge, è possibile configurare le impostazioni di **configurazione del nome del server e dell'indirizzo IP** :</span><span class="sxs-lookup"><span data-stu-id="03017-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="03017-105">**Nome interno o FQDN**: digitare il nome del computer a cui viene fatto riferimento nel DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="03017-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="03017-106">**Indirizzo IPv4 interno**: digitare l'indirizzo IPv4 della scheda di interfaccia di rete interna (NIC) per il computer.</span><span class="sxs-lookup"><span data-stu-id="03017-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="03017-107">Si configura l' **indirizzo IPv4 esterno** del **servizio Access Edge** associato al computer</span><span class="sxs-lookup"><span data-stu-id="03017-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="03017-108">Se si è scelto di usare un singolo indirizzo IP per la configurazione di Edge Server, sarà possibile modificare solo l'indirizzo IPv4 esterno per il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="03017-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="03017-109">Gli altri servizi Edge condividono lo stesso indirizzo IPv4 del servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="03017-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="03017-110">Se disponibile per la modifica, configurare l' **indirizzo IPv4 esterno** del **servizio di conferenza Web** associato al computer</span><span class="sxs-lookup"><span data-stu-id="03017-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="03017-111">Se disponibile per la modifica, è possibile configurare l' **indirizzo IPv4 esterno** del **servizio a/V** associato al computer</span><span class="sxs-lookup"><span data-stu-id="03017-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="03017-112">Se disponibile per la modifica, è possibile configurare l' **indirizzo IPv4 pubblico abilitato per NAT** associato al computer.</span><span class="sxs-lookup"><span data-stu-id="03017-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="03017-113">La proprietà di configurazione per l' **indirizzo IPv4 pubblico abilitato per NAT** sarà disponibile solo per la modifica se si è scelto di specificare la NAT (Network Address Translation) per il servizio a/V Edge</span><span class="sxs-lookup"><span data-stu-id="03017-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="03017-114">**OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="03017-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="03017-115">**Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="03017-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="03017-116">**Guida** Consente di visualizzare questa schermata della Guida.</span><span class="sxs-lookup"><span data-stu-id="03017-116">**Help** Displays this help screen.</span></span>
  

