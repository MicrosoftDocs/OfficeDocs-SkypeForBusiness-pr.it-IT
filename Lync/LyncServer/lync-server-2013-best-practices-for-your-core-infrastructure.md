---
title: "Lync Server 2013: procedure consigliate per l'infrastruttura di base"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfb6e12f6f2c6d66a0d4f5fed17bc01dc250db5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976878"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="6ec95-102">Procedure consigliate per l'infrastruttura di base in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ec95-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ec95-103">_**Argomento Ultima modifica:** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="6ec95-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="6ec95-104">Probabilmente hai già adottato misure per progettare la tolleranza di errore nel sistema, usando procedure come la garanzia di ridondanza hardware, la protezione contro la perdita di corrente, l'installazione di routine degli aggiornamenti della sicurezza e delle misure antivirus e il monitoraggio delle attività del server.</span><span class="sxs-lookup"><span data-stu-id="6ec95-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="6ec95-105">Queste procedure non sono utili solo per l'infrastruttura di Microsoft Lync Server 2013, ma anche per l'intera rete.</span><span class="sxs-lookup"><span data-stu-id="6ec95-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="6ec95-106">Se non sono state implementate queste procedure, è consigliabile eseguire questa operazione prima di distribuire Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6ec95-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="6ec95-107">Per proteggere i server della distribuzione di 2013 di Lync Server da danni accidentali o intenzionali che potrebbero causare tempi di inattività, seguire le seguenti precauzioni:</span><span class="sxs-lookup"><span data-stu-id="6ec95-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="6ec95-108">Aggiornare i server con gli aggiornamenti della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6ec95-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="6ec95-109">La sottoscrizione al servizio di notifica della sicurezza Microsoft consente di ricevere una notifica immediata dei rilasci del Bollettino della sicurezza per qualsiasi prodotto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6ec95-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="6ec95-110">Per eseguire la sottoscrizione, visitare il sito Web Microsoft Technical Security [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)Notifications.</span><span class="sxs-lookup"><span data-stu-id="6ec95-110">To subscribe, go to the Microsoft Technical Security Notifications website at [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="6ec95-111">Verificare che i diritti di accesso siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="6ec95-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="6ec95-112">Conservare i server in un ambiente fisico che impedisce l'accesso non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="6ec95-112">Keep your servers in a physical environment that prevents unauthorized access.</span></span> <span data-ttu-id="6ec95-113">Verificare che in tutti i server sia installato un software antivirus adeguato.</span><span class="sxs-lookup"><span data-stu-id="6ec95-113">Ensure that adequate antivirus software is installed on all your servers.</span></span> <span data-ttu-id="6ec95-114">Tieni aggiornato il software con i file di firma del virus più recenti.</span><span class="sxs-lookup"><span data-stu-id="6ec95-114">Keep the software up-to-date with the latest virus signature files.</span></span> <span data-ttu-id="6ec95-115">Usa la funzionalità di aggiornamento automatico dell'applicazione antivirus per conservare le firme del virus aggiornate.</span><span class="sxs-lookup"><span data-stu-id="6ec95-115">Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="6ec95-116">È consigliabile disabilitare i servizi di sistema operativo Windows Server che non sono necessari nei computer in cui è installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6ec95-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="6ec95-117">Crittografare sistemi operativi e unità disco in cui i dati vengono archiviati con un sistema di crittografia completo, a meno che non sia possibile garantire il controllo costante e completo dei server, il totale isolamento fisico e la disattivazione corretta e sicura del disco sostituito o non riuscito unità.</span><span class="sxs-lookup"><span data-stu-id="6ec95-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="6ec95-118">Disabilitare tutte le porte di accesso diretto alla memoria esterna (DMA) del server, a meno che non sia possibile garantire un controllo molto limitato sull'accesso fisico ai server.</span><span class="sxs-lookup"><span data-stu-id="6ec95-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="6ec95-119">Gli attacchi basati su DMA, che possono essere avviati abbastanza facilmente, potrebbero esporre informazioni molto riservate, come le chiavi di crittografia private.</span><span class="sxs-lookup"><span data-stu-id="6ec95-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

