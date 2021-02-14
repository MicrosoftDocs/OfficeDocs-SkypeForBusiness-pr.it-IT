---
title: Espansione delle impostazioni di modifica del server perimetrale per Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'È possibile modificare le impostazioni del server perimetrale o del pool di server perimetrali configurando le proprietà seguenti:'
ms.openlocfilehash: f77eb71948bbbe6d2fe3e24b400d29e3bf5fd5a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803296"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="81cce-103">Modificare l'espansione delle impostazioni del server perimetrale per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="81cce-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="81cce-104">È possibile modificare le impostazioni del server perimetrale o del pool di server perimetrali configurando le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="81cce-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="81cce-105">**Generale**</span><span class="sxs-lookup"><span data-stu-id="81cce-105">**General**</span></span>
  
- <span data-ttu-id="81cce-106">FQDN **pool interno:** il nome di dominio completo del pool interno è l'identità del server perimetrale o del pool di server perimetrali come definito nel record host DNS (Domain Name System) (A o AAAA per IPv6).</span><span class="sxs-lookup"><span data-stu-id="81cce-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="81cce-107">Selezionare Abilita federazione per il pool di server perimetrali **(porta 5061)** se si desidera abilitare il server perimetrale o il pool di server perimetrali per la federazione con altri partner del protocollo di avvio sessione.</span><span class="sxs-lookup"><span data-stu-id="81cce-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="81cce-108">È possibile definire attivamente un solo server perimetrale o un pool di server perimetrali per la federazione.</span><span class="sxs-lookup"><span data-stu-id="81cce-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="81cce-109">La configurazione mostrata nella schermata associata indica che un altro server perimetrale o un pool di server perimetrali è già configurato per la federazione.</span><span class="sxs-lookup"><span data-stu-id="81cce-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="81cce-110">Il record DNS SRV esterno per la federazione (_sipfederationtls._tcp. ) farà riferimento al server perimetrale o al pool di server perimetrali \<external domain name\> per la federazione.</span><span class="sxs-lookup"><span data-stu-id="81cce-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="81cce-111">La porta di replica della configurazione interna **(HTTPS),** per impostazione predefinita alla porta TCP 4443, è la porta su cui viene replicata la copia locale (ovvero locale dei server perimetrali) dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="81cce-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="81cce-112">La copia locale dell'archivio di gestione centrale si trova nel database **RTCLOCAL** nella SQL Server di ogni computer.</span><span class="sxs-lookup"><span data-stu-id="81cce-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="81cce-113">La replica è unidirezionale, avviata dal server di gestione centrale (o dal Front End Server o dal pool Front End che contiene il ruolo server di gestione centrale) ai server perimetrali ed è una porta di interfaccia interna.</span><span class="sxs-lookup"><span data-stu-id="81cce-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="81cce-114">**Selezione hop successivo**</span><span class="sxs-lookup"><span data-stu-id="81cce-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="81cce-115">Selezionare nell'elenco il **Pool hop successivo**.</span><span class="sxs-lookup"><span data-stu-id="81cce-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="81cce-116">È necessario definire un Director, un pool di server Director, un Front End Server o un pool Front End per assumere questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="81cce-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="81cce-117">Il pool dell'hop successivo è il server o il pool di server che accetterà i messaggi SIP in ingresso dall'interfaccia interna del server perimetrale o del pool di server perimetrali e invierà SIP in uscita all'interfaccia interna del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="81cce-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="81cce-118">Il Director è un ruolo facoltativo e se si decide di non distribuire i Director, i Front End Server (singolo computer o pool) assumeranno il ruolo Di director.</span><span class="sxs-lookup"><span data-stu-id="81cce-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="81cce-119">**Impostazioni esterne**</span><span class="sxs-lookup"><span data-stu-id="81cce-119">**External settings**</span></span>
  
<span data-ttu-id="81cce-120">Questa sezione delle proprietà consente di modificare le proprietà per le impostazioni esterne del server perimetrale o del pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="81cce-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="81cce-121">È possibile modificare le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="81cce-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="81cce-122">Selezionare la casella di controllo Abilita FQDN e indirizzo IP distinti per Web Conferencing e **A/V** se si desidera assegnare indirizzi IP e nomi di dominio completi distinti a ogni servizio server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="81cce-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="81cce-123">Se non si seleziona la casella di controllo, è necessario usare porte distinte per ogni servizio Edge.</span><span class="sxs-lookup"><span data-stu-id="81cce-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="81cce-124">Ogni servizio Edge condividerà il nome di dominio completo definito per il servizio Access Edge e utilizzerà quindi lo stesso indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="81cce-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="81cce-125">Ogni servizio Edge deve essere identificato in modo univoco da un indirizzo IP distinto e dalla stessa porta oppure dallo stesso indirizzo IP e da valori di porta univoci.</span><span class="sxs-lookup"><span data-stu-id="81cce-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="81cce-126">Selezionare **Il servizio A/V Edge** è abilitato per NAT se si desidera configurare il servizio A/V Edge per l'utilizzo di un indirizzo privato o di un altro indirizzo che verrà nascosto dietro un dispositivo NAT (Network Address Translation).</span><span class="sxs-lookup"><span data-stu-id="81cce-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="81cce-127">Per modificare il servizio **Access Edge,** è necessario definire l'FQDN del **pool** per il servizio Access Edge come definito in DNS dai record host (A e AAAA se si usa IPv6) e un valore di porta</span><span class="sxs-lookup"><span data-stu-id="81cce-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="81cce-128">Per modificare il servizio **Web Conferencing Edge,** è necessario definire un FQDN del **pool** per il servizio Web Conferencing Edge come definito in DNS dai record host (A e AAAA se si usa IPv6) e un valore di porta</span><span class="sxs-lookup"><span data-stu-id="81cce-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="81cce-129">Per modificare il **servizio A/V Edge,** è necessario definire un FQDN del **pool** per il servizio A/V Edge come definito in DNS dai record host (A e AAAA se si usa IPv6) e un valore di porta</span><span class="sxs-lookup"><span data-stu-id="81cce-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="81cce-130">Se è stata selezionata la casella di controllo Abilita FQDN e indirizzo IP distinti per Web Conferencing e **A/V,** sarà disponibile per la modifica solo l'FQDN del pool di servizi Access Edge.</span><span class="sxs-lookup"><span data-stu-id="81cce-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="81cce-131">Assegnare porte distinte a ognuno dei tre servizi Edge.</span><span class="sxs-lookup"><span data-stu-id="81cce-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="81cce-132">**OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.</span><span class="sxs-lookup"><span data-stu-id="81cce-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="81cce-133">**Annulla** Rimuove le modifiche e chiude la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="81cce-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="81cce-134">**?** Visualizza questa schermata della Guida.</span><span class="sxs-lookup"><span data-stu-id="81cce-134">**Help** Displays this help screen.</span></span>
  

