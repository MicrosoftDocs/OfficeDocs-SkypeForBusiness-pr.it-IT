---
title: 'Lync Server 2013: requisiti e supporto per i server aggiuntivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7b83f900a5d6ccca9932b68e012d5c0dbbd6d23
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="cdf70-102">Requisiti e supporto per i server aggiuntivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdf70-102">Additional server support and requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdf70-103">_**Ultimo argomento modificato:** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="cdf70-103">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="cdf70-104">Oltre al supporto software descritto nelle altre sezioni della documentazione relativa alla supportabilità, Lync Server 2013 presenta le limitazioni di supporto seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf70-104">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="cdf70-105">Lync Server 2013 supporta DNS (Domain Name System) e bilanciamento del carico hardware per ruoli del server specifici.</span><span class="sxs-lookup"><span data-stu-id="cdf70-105">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="cdf70-106">Laddove appropriato, è inoltre supportato il bilanciamento del carico delle applicazioni per Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="cdf70-106">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="cdf70-107">Per informazioni dettagliate su quando utilizzare ciascun tipo di bilanciamento del carico, vedere la documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="cdf70-107">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="cdf70-108">Lync Server 2013 utilizza il protocollo DLX (Distribution List Expansion Protocol) per espandere le liste di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cdf70-108">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="cdf70-109">Questo protocollo specifica inoltre il metodo del servizio Web utilizzato per ottenere i membri di una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cdf70-109">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="cdf70-110">Microsoft Exchange Server supporta i gruppi dinamici che non dispongono di membri a essi assegnati in modo statico.</span><span class="sxs-lookup"><span data-stu-id="cdf70-110">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="cdf70-111">In tali gruppi sono invece archiviate query valutate durante l'espansione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="cdf70-111">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="cdf70-112">Il protocollo DLX non supporta le liste di distribuzione dinamiche.</span><span class="sxs-lookup"><span data-stu-id="cdf70-112">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="cdf70-113">Questa limitazione del DLX si applica a tutte le versioni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cdf70-113">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="cdf70-114">Poiché la procedura guidata Abilita utenti non supporta la conversione automatica di caratteri non inglesi in un URI compatibile con SIP, è necessario modificare l'indirizzo SIP manualmente.</span><span class="sxs-lookup"><span data-stu-id="cdf70-114">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="cdf70-115">Per i server che eseguono il software antivirus, fare riferimento alle [esclusioni di analisi antivirus per Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) per le esclusioni dei virus consigliate e altre raccomandazioni relative alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cdf70-115">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="cdf70-116">Se si utilizza IPsec, è consigliabile disabilitarlo negli intervalli di porte utilizzati per il traffico audio e video.</span><span class="sxs-lookup"><span data-stu-id="cdf70-116">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="cdf70-117">Per informazioni dettagliate, vedere [IPSec Exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="cdf70-117">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="cdf70-118">Se nell'organizzazione è prevista un'infrastruttura di qualità del servizio (QoS), il sottosistema multimediale è progettato per essere utilizzato nell'infrastruttura esistente.</span><span class="sxs-lookup"><span data-stu-id="cdf70-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="cdf70-119">Per informazioni dettagliate sull'implementazione di QoS, vedere [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="cdf70-119">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="cdf70-120">L'utilizzo del firewall del sistema operativo è supportato.</span><span class="sxs-lookup"><span data-stu-id="cdf70-120">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="cdf70-121">Lync Server 2013 gestisce le eccezioni del firewall per il firewall del sistema operativo, tranne che per il software di database di Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cdf70-121">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="cdf70-122">Per informazioni dettagliate sui requisiti del firewall di SQL Server, vedere la documentazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cdf70-122">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="cdf70-123">Le interfacce esterne utilizzate per implementare il supporto per l'accesso utente esterno devono trovarsi in una subnet distinta e *non* nella stessa rete delle interfacce interne.</span><span class="sxs-lookup"><span data-stu-id="cdf70-123">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="cdf70-p106">La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la federazione di messaggistica istantanea con Google Talk. Per altri sistemi XMPP, contattare il fornitore di terze parti per verificare l'eventuale supporto della federazione con Lync Server 2013 e per indicazioni per la distribuzione o la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="cdf70-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="cdf70-126">Con la versione di Lync Server 2013 aggiornamenti cumulativi: luglio 2013, Lync Server 2013 ora supporta l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="cdf70-126">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="cdf70-127">Per ulteriori informazioni, vedere [autenticazione a due fattori in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="cdf70-127">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="cdf70-128">La maggior parte dei server interni richiede un tipo di certificato definito come **autenticazione aperta** (OAuth).</span><span class="sxs-lookup"><span data-stu-id="cdf70-128">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="cdf70-129">È necessario richiedere e assegnare un certificato OAuth durante la fase di **richiesta, installazione e assegnazione dei certificati** della distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cdf70-129">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="cdf70-130">La dimensione minima per una chiave del certificato OAuth è di 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="cdf70-130">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="cdf70-131">È possibile che venga visualizzato un messaggio di avviso se si richiede un certificato con una lunghezza di chiave inferiore a 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="cdf70-131">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="cdf70-132">Per evitare potenziali problemi nel caso in cui venga applicata una lunghezza della chiave di 2048 anziché avvisata, è consigliabile utilizzare sempre una lunghezza di chiave di 2048 per i certificati OAuth.</span><span class="sxs-lookup"><span data-stu-id="cdf70-132">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="cdf70-133">Lync Server 2013 e Microsoft Exchange Server 2010 Service Pack 1 (SP1) operano con il supporto per gli algoritmi FIPS (Federal Information Processing Standard) 140-2 se i sistemi operativi Windows Server 2008 R2 sono configurati per l'utilizzo degli algoritmi FIPS 140-2 per crittografia del sistema.</span><span class="sxs-lookup"><span data-stu-id="cdf70-133">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="cdf70-134">Per implementare il supporto FIPS, è necessario configurare ogni server su cui è in esecuzione Lync Server 2013 per supportarlo.</span><span class="sxs-lookup"><span data-stu-id="cdf70-134">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="cdf70-135">Per informazioni dettagliate sugli algoritmi FIPS conformi e su come implementare il supporto FIPS, vedere l'articolo 811833 della Microsoft Knowledge Base "crittografia del sistema: utilizzare gli algoritmi FIPS conformi per la crittografia, l'hashing e la firma delle impostazioni di sicurezza in Windows XP e [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)nelle versioni successive di Windows all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="cdf70-135">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="cdf70-136">Per informazioni dettagliate sul supporto e le limitazioni di FIPS 140-2 in Exchange 2010, vedere "Exchange 2010 SP1 and Support for FIPS compliant algorithms [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)" at.</span><span class="sxs-lookup"><span data-stu-id="cdf70-136">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="cdf70-137">Lync Server 2013 richiede l'installazione di altri software su componenti specifici prima o durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cdf70-137">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="cdf70-138">Questo include il software disponibile con il sistema operativo, il software scaricabile e il software che viene installato automaticamente durante l'installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf70-138">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="cdf70-139">Di seguito è disponibile un elenco di software aggiuntivo che può essere necessario:</span><span class="sxs-lookup"><span data-stu-id="cdf70-139">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="cdf70-140">Windows Update</span><span class="sxs-lookup"><span data-stu-id="cdf70-140">Windows Update</span></span>

  - <span data-ttu-id="cdf70-141">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="cdf70-141">Windows Identity Foundation</span></span>

  - <span data-ttu-id="cdf70-142">Microsoft .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="cdf70-142">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="cdf70-143">Microsoft Visual C++ 2012 Redistributable</span><span class="sxs-lookup"><span data-stu-id="cdf70-143">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cdf70-144">Microsoft Visual C++ 2012 Redistributable viene installato automaticamente quando si installa Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf70-144">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="cdf70-145">Non è consigliabile installare e utilizzare altre versioni.</span><span class="sxs-lookup"><span data-stu-id="cdf70-145">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="cdf70-146">URL Rewrite Module 2.0 Redistributable</span><span class="sxs-lookup"><span data-stu-id="cdf70-146">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="cdf70-147">Runtime formato Windows Media</span><span class="sxs-lookup"><span data-stu-id="cdf70-147">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="cdf70-148">Windows PowerShell versione 3,0</span><span class="sxs-lookup"><span data-stu-id="cdf70-148">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="cdf70-149">Plug-in del browser Microsoft Silverlight 4 (Silverlight 4.0.50524.0 o la versione più recente per il Pannello di controllo di Lync Server)</span><span class="sxs-lookup"><span data-stu-id="cdf70-149">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="cdf70-150">Strumenti di servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="cdf70-150">Active Directory Domain Services tools</span></span>

<span data-ttu-id="cdf70-151">Alcuni di questi requisiti software si applicano solo a ruoli del server o componenti specifici.</span><span class="sxs-lookup"><span data-stu-id="cdf70-151">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="cdf70-152">Per informazioni dettagliate su questi requisiti software, vedere [Additional Software Requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="cdf70-152">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

