---
title: Modificare l'espansione delle impostazioni del server perimetrale per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'È possibile modificare le impostazioni per il server perimetrale o il pool di Edge configurando le proprietà seguenti:'
ms.openlocfilehash: 78edbc8093b54474ac9f0429b5232851a5a16663
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697381"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="d13af-103">Modificare l'espansione delle impostazioni del server perimetrale per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d13af-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="d13af-104">È possibile modificare le impostazioni per il server perimetrale o il pool di Edge configurando le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="d13af-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="d13af-105">**Generale**</span><span class="sxs-lookup"><span data-stu-id="d13af-105">**General**</span></span>
  
- <span data-ttu-id="d13af-106">**FQDN del pool interno**: il nome di dominio completo del pool interno è l'identità del server perimetrale o del pool di Edge definito nel record DNS (Domain Name System) host (a o AAAA per IPv6).</span><span class="sxs-lookup"><span data-stu-id="d13af-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="d13af-107">Selezionare **Abilita federazione per questo pool di bordi (porta 5061)** se si vuole abilitare l'Edge Server o il pool di Edge per la Federazione con altri partner del protocollo di avvio della sessione.</span><span class="sxs-lookup"><span data-stu-id="d13af-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d13af-108">È possibile definire un solo Edge Server o un pool di bordi attivamente per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="d13af-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="d13af-109">La configurazione visualizzata nella schermata associata indica che un altro Edge Server o un pool di Edge è già configurato per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="d13af-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="d13af-110">Record SRV DNS esterno per la Federazione (_sipfederationtls. _tcp.\< nome\>di dominio esterno) punterà al server perimetrale o al pool di Edge per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="d13af-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="d13af-111">La **porta di replica della configurazione interna (HTTPS)**, per impostazione predefinita alla porta TCP 4443, è la porta in cui viene replicata la copia locale (ovvero locale per i server perimetrali) dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="d13af-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="d13af-112">La copia locale di Central Management store si trova nel database **RTCLOCAL** in SQL Server in ogni computer.</span><span class="sxs-lookup"><span data-stu-id="d13af-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="d13af-113">La replica è unidirezionale, avviata dal server di gestione centrale (oppure il front end server o il pool Front-end che contiene il ruolo del server di gestione centrale) agli Edge Server ed è una porta di interfaccia interna.</span><span class="sxs-lookup"><span data-stu-id="d13af-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="d13af-114">**Selezione hop successivo**</span><span class="sxs-lookup"><span data-stu-id="d13af-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="d13af-115">Selezionare per l'elenco il **pool di hop successivo**.</span><span class="sxs-lookup"><span data-stu-id="d13af-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="d13af-116">Si definisce un Director, un pool di Director, un front end server o un pool Front end per assumere questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="d13af-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="d13af-117">Il pool di hop successivo è il pool di server o server che accetterà i messaggi SIP in ingresso dall'interfaccia interna del server perimetrale o del pool Edge e invierà il SIP in uscita all'interfaccia interna del bordo.</span><span class="sxs-lookup"><span data-stu-id="d13af-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d13af-118">Il Director è un ruolo facoltativo e se si decide di non distribuire i direttori, i server front-end (singolo computer o pool) assumeranno il ruolo di Director.</span><span class="sxs-lookup"><span data-stu-id="d13af-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="d13af-119">**Impostazioni esterne**</span><span class="sxs-lookup"><span data-stu-id="d13af-119">**External settings**</span></span>
  
<span data-ttu-id="d13af-120">Questa sezione delle proprietà consente di modificare le proprietà per le impostazioni esterne del server perimetrale o del pool di bordi.</span><span class="sxs-lookup"><span data-stu-id="d13af-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="d13af-121">Le proprietà seguenti sono disponibili per la modifica:</span><span class="sxs-lookup"><span data-stu-id="d13af-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="d13af-122">Selezionare la casella di controllo **attiva FQDN separato e indirizzo IP per le conferenze Web e a/V** se si vogliono assegnare indirizzi IP distinti e nomi di dominio completi a ogni servizio Edge Server.</span><span class="sxs-lookup"><span data-stu-id="d13af-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d13af-123">Se si sceglie di non selezionare la casella di controllo, è necessario usare porte separate per ogni servizio Edge.</span><span class="sxs-lookup"><span data-stu-id="d13af-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="d13af-124">Ogni servizio Edge condividerà l'FQDN definito per il servizio Access Edge e utilizzerà quindi lo stesso indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="d13af-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="d13af-125">Ogni servizio Edge deve essere identificato in modo univoco da un indirizzo IP distinto e da una stessa porta oppure dagli stessi indirizzi IP e dai valori di porta univoci.</span><span class="sxs-lookup"><span data-stu-id="d13af-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="d13af-126">Selezionare **un/v Edge Server è abilitato NAT** se si vuole configurare il servizio a/v Edge per l'uso di un indirizzo privato o di un altro indirizzo che verrà nascosto dietro un dispositivo NAT (Network Address Translation).</span><span class="sxs-lookup"><span data-stu-id="d13af-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="d13af-127">Per modificare il **servizio Access Edge**, è possibile definire il **nome di dominio completo del pool** per il servizio Access Edge definito in DNS per i record host (a e aaaa se IPv6 viene usato) e un valore di porta</span><span class="sxs-lookup"><span data-stu-id="d13af-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="d13af-128">Per modificare il **servizio Web Conferencing Edge**, è possibile definire un **nome di dominio completo del pool** per il servizio Web Conferencing Edge definito in DNS per i record host (a e aaaa if IPv6 viene usato) e un valore di porta</span><span class="sxs-lookup"><span data-stu-id="d13af-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="d13af-129">Per modificare il **servizio a/v Edge**, è possibile definire un **nome di dominio completo del pool** per il servizio a/v Edge definito in DNS per i record host (a e aaaa if IPv6 viene usato) e un valore di porta</span><span class="sxs-lookup"><span data-stu-id="d13af-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d13af-130">Se è stata selezionata la casella di controllo **Abilita FQDN separato e indirizzo IP per conferenze Web e a/V** , sarà disponibile solo il nome di dominio completo del pool di servizi Edge di Access per la modifica.</span><span class="sxs-lookup"><span data-stu-id="d13af-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="d13af-131">Assegnare porte distinte per ognuno dei tre servizi Edge.</span><span class="sxs-lookup"><span data-stu-id="d13af-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="d13af-132">**OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d13af-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="d13af-133">**Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d13af-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="d13af-134">**Guida** Consente di visualizzare questa schermata della Guida.</span><span class="sxs-lookup"><span data-stu-id="d13af-134">**Help** Displays this help screen.</span></span>
  

