---
title: Aggiornare i record SRV DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 927bdab6721583fd744f68969a852f29ba478027
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a><span data-ttu-id="cb4eb-102">Aggiornare i record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="cb4eb-102">Update DNS SRV records</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb4eb-103">_**Argomento Ultima modifica:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="cb4eb-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="cb4eb-104">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="cb4eb-105">Questo argomento descrive come aggiornare i record DNS (Domain Name System) dopo la migrazione a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="cb4eb-106">Dopo che tutti gli utenti sono stati spostati in Lync Server 2013, ma prima che il pool o il Director legacy di Office Communications Server 2007 R2 venga rimosso, è necessario aggiornare i record SRV DNS nel DNS interno per ogni dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-106">After all users have been moved to Lync Server 2013, but before the legacy Office Communications Server 2007 R2 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="cb4eb-107">Questa procedura presuppone che il DNS interno disponga di aree per i domini utente SIP.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="cb4eb-108">**Per configurare un record SRV DNS**</span><span class="sxs-lookup"><span data-stu-id="cb4eb-108">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="cb4eb-109">Nel server DNS fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="cb4eb-110">Nell'albero della console per il dominio SIP espandere **aree di ricerca in avanti**, espandere il dominio SIP in cui è installato Lync Server 2013 e passare all'impostazione \*\* \_TCP\*\* .</span><span class="sxs-lookup"><span data-stu-id="cb4eb-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="cb4eb-111">Nel riquadro destro fare clic con il pulsante destro del mouse su \*\* \_sipinternaltls\*\* e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-111">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="cb4eb-112">In **host che offre questo servizio**aggiornare il nome di dominio completo dell'host per posizionare il puntatore sul pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-112">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="cb4eb-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-113">Click **OK**.</span></span>

<span data-ttu-id="cb4eb-114">**Per verificare che il nome di dominio completo del pool Front-end o del server Standard Edition possa essere risolto**</span><span class="sxs-lookup"><span data-stu-id="cb4eb-114">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="cb4eb-115">Accedere a un computer client nel dominio.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-115">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="cb4eb-116">Fare clic sul pulsante **Start**e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-116">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="cb4eb-117">Nella casella **Apri** Digitare **cmd**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-117">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="cb4eb-118">Al prompt dei comandi digitare il nome di dominio completo **nslookup** \<del pool\> di \<front end o il nome di\>dominio completo del server Standard Edition, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-118">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="cb4eb-119">Verificare di ricevere una risposta che venga risolta nell'indirizzo IP appropriato per il nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

