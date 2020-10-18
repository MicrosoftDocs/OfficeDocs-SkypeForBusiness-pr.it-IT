---
title: Aggiornare i record SRV DNS
description: Aggiornare i record SRV DNS.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24161074e8f3bcf7e296a957588eeb59d5f2ad1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579592"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="0d49b-103">Aggiornare i record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="0d49b-103">Update DNS SRV records</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d49b-104">_**Ultimo argomento modificato:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="0d49b-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="0d49b-105">Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="0d49b-105">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="0d49b-106">In questo argomento viene descritto come aggiornare i record DNS (Domain Name System) dopo la migrazione a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d49b-106">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="0d49b-107">Dopo che tutti gli utenti sono stati spostati in Lync Server 2013, ma prima di rimuovere il pool o il Director di Lync Server 2010 legacy, è necessario aggiornare i record SRV DNS nel DNS interno per ogni dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="0d49b-107">After all users have been moved to Lync Server 2013, but before the legacy Lync Server 2010 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="0d49b-108">Per questa procedura si presuppone che nel sistema DNS interno siano disponibili aree per i domini utente SIP.</span><span class="sxs-lookup"><span data-stu-id="0d49b-108">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="0d49b-109">**Per configurare un record DNS SRV**</span><span class="sxs-lookup"><span data-stu-id="0d49b-109">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="0d49b-110">Nel server DNS fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0d49b-110">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="0d49b-111">Nell'albero della console per il dominio SIP espandere **zone di ricerca diretta**, espandere il dominio SIP in cui è installato Lync Server 2013 e passare all'impostazione \*\* \_ TCP\*\* .</span><span class="sxs-lookup"><span data-stu-id="0d49b-111">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="0d49b-112">Nel riquadro destro fare clic con il pulsante destro del mouse su \*\* \_ sipinternaltls\*\* e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0d49b-112">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="0d49b-113">In **host che offre questo servizio**aggiornare il nome di dominio completo host in modo che punti al pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d49b-113">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="0d49b-114">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0d49b-114">Click **OK**.</span></span>

<span data-ttu-id="0d49b-115">**Per verificare che il nome di domino completo del pool Front End o del server Standard Edition possa essere risolto**</span><span class="sxs-lookup"><span data-stu-id="0d49b-115">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="0d49b-116">Accedere a un computer client nel dominio.</span><span class="sxs-lookup"><span data-stu-id="0d49b-116">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="0d49b-117">Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0d49b-117">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="0d49b-118">Nella casella **Apri** digitare **cmd** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0d49b-118">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="0d49b-119">Al prompt dei comandi digitare **nslookup** \<FQDN of the Front End pool\> o \<FQDN of the Standard Edition server\> , quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0d49b-119">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="0d49b-120">Verificare di ricevere una risposta che si risolve nell'indirizzo IP appropriato per il nome FQDN.</span><span class="sxs-lookup"><span data-stu-id="0d49b-120">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

