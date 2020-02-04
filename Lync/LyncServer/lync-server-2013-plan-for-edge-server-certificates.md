---
title: 'Lync Server 2013: Pianificare i certificati dei server perimetrali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faad6dba610df8033b75b0c87c52fbb065dc5dcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a><span data-ttu-id="21db1-102">Pianificare i certificati dei server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21db1-102">Plan for Edge Server certificates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21db1-103">_**Argomento Ultima modifica:** 2012-11-05_</span><span class="sxs-lookup"><span data-stu-id="21db1-103">_**Topic Last Modified:** 2012-11-05_</span></span>

<span data-ttu-id="21db1-104">La creazione di certificati per Edge è semplificata in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21db1-104">Certificate creation for Edge is simplified in Lync Server 2013.</span></span>

<span data-ttu-id="21db1-105">**Diagramma di flusso Certificati per Edge Server**</span><span class="sxs-lookup"><span data-stu-id="21db1-105">**Certificates Flow Chart for Edge Server**</span></span>

<span data-ttu-id="21db1-106">![a5fc20db-7ced-4364-B577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-B577-6a709a8367cd")</span><span class="sxs-lookup"><span data-stu-id="21db1-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span></span>

<span data-ttu-id="21db1-107">Creare un singolo certificato pubblico, verificare di avere una chiave privata esportabile definita per il certificato e assegnarla alle interfacce esterne di Edge Server seguenti tramite la creazione guidata certificato:</span><span class="sxs-lookup"><span data-stu-id="21db1-107">Create a single public certificate, ensure that you have an exportable private key defined for the certificate, and assign it to the following Edge Server external interfaces using the certificate wizard:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="21db1-108">I certificati con caratteri jolly non sono supportati in Lync Server, ad eccezione di quelli usati per riepilogare gli URL semplici tramite il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="21db1-108">Wildcard certificates are not supported in Lync Server, except where used to summarize the Simple URLs through the reverse proxy.</span></span> <span data-ttu-id="21db1-109">È necessario definire SANs per ogni nome di dominio SIP, Web Conferencing Edge service, A/V Edge e il dominio XMPP offerti dalla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="21db1-109">You must define distinct subject alternate names (SANs) for each SIP domain name, Web Conferencing Edge service, A/V Edge service and XMPP domain offered by your deployment.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="21db1-110">Introdotti in Lync Server 2013, i certificati di autenticazione audio/video in anticipo rispetto all'ora di scadenza del certificato corrente richiedono una pianificazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="21db1-110">Introduced in Lync Server 2013, staging Audio/Video Authentication certificates in advance of the expiration time of the current certificate requires some additional planning.</span></span> <span data-ttu-id="21db1-111">Invece di un certificato con più scopi per l'interfaccia perimetrale esterna, sono necessari due certificati, uno assegnato al servizio Access Edge e Web Conferencing Edge e un certificato per il servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="21db1-111">Instead of one certificate with multiple purposes for the external Edge interface, you will require two certificates, one assigned to the Access Edge service and Web Conferencing Edge service, and one certificate for the A/V Edge service.</span></span> <span data-ttu-id="21db1-112">Per ulteriori informazioni, vedere <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">gestione dei certificati di staging AV e OAuth in Lync Server 2013 con-roll in Set-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="21db1-112">For additional details, see <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</A></span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="21db1-113">In caso di pool di Edge Server, è possibile esportare il certificato con la chiave privata in ogni Edge Server e assegnare il certificato a ogni servizio Edge Server.</span><span class="sxs-lookup"><span data-stu-id="21db1-113">In the event of a pool of Edge Servers, you export the certificate with the private key to each Edge Server and assign the certificate to each Edge Server service.</span></span> <span data-ttu-id="21db1-114">Eseguire la stessa operazione per il certificato Internal Edge Server, esportando il certificato con la chiave privata e assegnando a ogni interfaccia Edge interna.</span><span class="sxs-lookup"><span data-stu-id="21db1-114">Do the same for the internal Edge Server certificate, exporting the certificate with the private key and assigning to each internal Edge interface.</span></span>



</div>

  - <span data-ttu-id="21db1-115">Verificare di avere una chiave privata esportabile assegnata per il certificato</span><span class="sxs-lookup"><span data-stu-id="21db1-115">Ensure that you have an exportable private key assigned for the certificate</span></span>

  - <span data-ttu-id="21db1-116">Access Edge Services (denominato Edge di **accesso SIP esterno** nella procedura guidata certificato)</span><span class="sxs-lookup"><span data-stu-id="21db1-116">Access Edge service (referred to as **SIP Access Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="21db1-117">Web Conferencing Edge Services (denominato **Web Conferencing Edge esterno** nella procedura guidata certificati)</span><span class="sxs-lookup"><span data-stu-id="21db1-117">Web Conferencing Edge service (referred to as **Web Conferencing Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="21db1-118">Servizio di autenticazione a/V (denominato a **/v Edge External** nella procedura guidata certificato)</span><span class="sxs-lookup"><span data-stu-id="21db1-118">A/V Authentication service (referred to as **A/V Edge External** in the certificate wizard)</span></span>

<span data-ttu-id="21db1-119">Creare un singolo certificato interno con una chiave privata esportabile, copiarla e assegnarla a ognuna delle interfacce interne del server perimetrale:</span><span class="sxs-lookup"><span data-stu-id="21db1-119">Create a single internal certificate with exportable private key, copy and assign it to each of the Edge Server internal interfaces:</span></span>

  - <span data-ttu-id="21db1-120">Edge Server (denominato **Edge Internal** nella creazione guidata certificato)</span><span class="sxs-lookup"><span data-stu-id="21db1-120">Edge Server (referred to as **Edge Internal** in the certificate wizard)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="21db1-121">È possibile usare certificati distinti per ogni servizio Edge Server.</span><span class="sxs-lookup"><span data-stu-id="21db1-121">It is possible to use separate and distinct certificates for each Edge Server service.</span></span> <span data-ttu-id="21db1-122">Un buon motivo per scegliere i certificati distinti è se si vuole usare la nuova caratteristica di certificato rotante per il certificato del servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="21db1-122">A good reason to choose separate certificates is if you want to use the new rolling certificate feature for the A/V Edge service certificate.</span></span> <span data-ttu-id="21db1-123">Nel caso di questa caratteristica, è consigliabile disaccoppiare il certificato A/V Edge service da Access Edge service e Web Conferencing Edge service.</span><span class="sxs-lookup"><span data-stu-id="21db1-123">In the case of this feature, decoupling the A/V Edge service certificate from the Access Edge service and Web Conferencing Edge service is recommended.</span></span> <span data-ttu-id="21db1-124">Se si sceglie di richiedere, acquisire e assegnare certificati distinti per ogni servizio, è necessario richiedere che la chiave privata sia esportabile per il servizio A/V Edge (di nuovo, si tratta in realtà del servizio di autenticazione A/V) e assegnare lo stesso certificato all'interfaccia esterna di un/V Edge in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="21db1-124">If you choose to request, acquire and assign separate certificates for each service, you must request that the private key be exportable for the A/V Edge service (again, this is in actuality the A/V Authentication service) and assign the same certificate to the A/V Edge External interface on each Edge Server.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="21db1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21db1-125">See Also</span></span>


[<span data-ttu-id="21db1-126">Gestione di certificati AV e OAuth in Lync Server 2013 con-roll in Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="21db1-126">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[<span data-ttu-id="21db1-127">Modifiche introdotte in Lync Server 2013 che incidono sulla pianificazione dei server perimetrali</span><span class="sxs-lookup"><span data-stu-id="21db1-127">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

