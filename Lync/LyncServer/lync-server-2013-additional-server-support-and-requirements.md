---
title: 'Lync Server 2013: Requisiti e supporto per i server aggiuntivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29f2d1a1b728fcec84f0aed70f00f1143c70c490
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="e7c30-102">Requisiti e supporto per i server aggiuntivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7c30-102">Additional server support and requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7c30-103">_**Argomento Ultima modifica:** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="e7c30-103">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="e7c30-104">Oltre al supporto software descritto nelle altre sezioni della documentazione relativa alla supportabilità, Lync Server 2013 ha le seguenti limitazioni di supporto:</span><span class="sxs-lookup"><span data-stu-id="e7c30-104">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="e7c30-105">Lync Server 2013 supporta il DNS (Domain Name System) e il bilanciamento del carico hardware per ruoli server specifici.</span><span class="sxs-lookup"><span data-stu-id="e7c30-105">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="e7c30-106">Supporta anche il bilanciamento del carico delle applicazioni per Mediation Server, se necessario.</span><span class="sxs-lookup"><span data-stu-id="e7c30-106">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="e7c30-107">Per informazioni dettagliate su quando usarle, vedere la documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="e7c30-107">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="e7c30-108">Lync Server 2013 usa il protocollo DLX (Distribution List Expansion Protocol) per espandere le liste di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e7c30-108">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="e7c30-109">Questo protocollo specifica anche il metodo di servizio Web usato per ottenere l'appartenenza a una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e7c30-109">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="e7c30-110">Microsoft Exchange Server supporta i gruppi dinamici a cui non sono assegnati membri in modo statico.</span><span class="sxs-lookup"><span data-stu-id="e7c30-110">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="e7c30-111">Archiviano invece le query che vengono valutate quando il gruppo viene espanso.</span><span class="sxs-lookup"><span data-stu-id="e7c30-111">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="e7c30-112">DLX non supporta le liste di distribuzione dinamiche.</span><span class="sxs-lookup"><span data-stu-id="e7c30-112">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="e7c30-113">Questa limitazione di DLX si applica a tutte le versioni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e7c30-113">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="e7c30-114">La procedura guidata Abilita utente non supporta la conversione automatica di caratteri non inglesi in un URI conforme a SIP, quindi è necessario modificare manualmente l'indirizzo SIP.</span><span class="sxs-lookup"><span data-stu-id="e7c30-114">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="e7c30-115">Per i server che esegue il software antivirus, vedere [esclusioni della scansione antivirus per Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) per le esclusioni di virus suggerite e altre raccomandazioni relative alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e7c30-115">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="e7c30-116">Se si usa IPsec, è consigliabile disabilitare IPsec sugli intervalli di porte usati per il traffico audio e video.</span><span class="sxs-lookup"><span data-stu-id="e7c30-116">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="e7c30-117">Per informazioni dettagliate, vedere [Eccezioni IPsec in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="e7c30-117">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="e7c30-118">Se l'organizzazione usa un'infrastruttura QoS (Quality of Service), il sottosistema multimediale è progettato per funzionare all'interno di questa infrastruttura esistente.</span><span class="sxs-lookup"><span data-stu-id="e7c30-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="e7c30-119">Per informazioni dettagliate sull'implementazione di QoS, vedere [gestione della qualità del servizio (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="e7c30-119">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="e7c30-120">È supportato l'uso del firewall del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e7c30-120">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="e7c30-121">Lync Server 2013 gestisce le eccezioni del firewall per il firewall del sistema operativo, ad eccezione del software di database di Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e7c30-121">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="e7c30-122">Per informazioni dettagliate sui requisiti di SQL Server firewall, vedere la documentazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e7c30-122">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="e7c30-123">Le interfacce esterne usate per implementare il supporto per l'accesso degli utenti esterni devono trovarsi in una subnet separata, *non* nella stessa rete delle interfacce interne.</span><span class="sxs-lookup"><span data-stu-id="e7c30-123">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="e7c30-124">La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la Federazione della messaggistica istantanea con Google Talk.</span><span class="sxs-lookup"><span data-stu-id="e7c30-124">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="e7c30-125">Per qualsiasi altro sistema XMPP, contattare il fornitore di terze parti per verificare che supportino la Federazione con Lync Server 2013 e per eventuali suggerimenti per la distribuzione o la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="e7c30-125">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="e7c30-126">Con il rilascio degli aggiornamenti cumulativi di Lync Server 2013:2013 luglio, Lync Server 2013 ora supporta l'autenticazione a due fattori.</span><span class="sxs-lookup"><span data-stu-id="e7c30-126">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="e7c30-127">Per altre informazioni, vedere [autenticazione a due fattori in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e7c30-127">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="e7c30-128">La maggior parte dei server interni richiede un tipo di certificato definito come **Open Authentication** (OAuth).</span><span class="sxs-lookup"><span data-stu-id="e7c30-128">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="e7c30-129">È necessario richiedere e assegnare un certificato OAuth durante la **richiesta, installare e assegnare** la fase certificati della distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e7c30-129">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="e7c30-130">La dimensione minima per una chiave di certificato OAuth è 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="e7c30-130">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="e7c30-131">Se si richiede un certificato con una lunghezza di chiave inferiore a 2048 bit, è possibile che venga visualizzato un avviso.</span><span class="sxs-lookup"><span data-stu-id="e7c30-131">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="e7c30-132">Per evitare potenziali problemi se viene applicata una lunghezza di chiave di 2048 anziché avvisata, è consigliabile usare sempre una lunghezza di chiave di 2048 per i certificati OAuth.</span><span class="sxs-lookup"><span data-stu-id="e7c30-132">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="e7c30-133">Lync Server 2013 e Microsoft Exchange Server 2010 Service Pack 1 (SP1) funzionano con il supporto per gli algoritmi FIPS (Federal Information Processing Standard) 140-2 se i sistemi operativi Windows Server 2008 R2 sono configurati per l'uso degli algoritmi FIPS 140-2 per crittografia di sistema.</span><span class="sxs-lookup"><span data-stu-id="e7c30-133">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="e7c30-134">Per implementare il supporto FIPS, è necessario configurare ogni server in cui è in esecuzione Lync Server 2013 per supportarlo.</span><span class="sxs-lookup"><span data-stu-id="e7c30-134">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="e7c30-135">Per informazioni dettagliate sugli algoritmi conformi FIPS e su come implementare il supporto FIPS, vedere l'articolo 811833 della Microsoft Knowledge Base "crittografia sistema: usare gli algoritmi conformi a FIPS per la crittografia, l'hashing e la firma dell'impostazione di sicurezza in Windows XP e [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)nelle versioni successive di Windows at.</span><span class="sxs-lookup"><span data-stu-id="e7c30-135">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="e7c30-136">Per informazioni dettagliate sul supporto e le limitazioni di FIPS 140-2 in Exchange 2010, vedere "Exchange 2010 SP1 e supporto per gli algoritmi di conformità [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)FIPS".</span><span class="sxs-lookup"><span data-stu-id="e7c30-136">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="e7c30-137">Lync Server 2013 richiede l'installazione di altri software su componenti specifici prima o durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e7c30-137">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="e7c30-138">Questo include il software disponibile con il sistema operativo, il software scaricabile e il software che viene installato automaticamente durante l'installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7c30-138">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="e7c30-139">Di seguito è riportato un elenco di software aggiuntivo che può essere necessario:</span><span class="sxs-lookup"><span data-stu-id="e7c30-139">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="e7c30-140">Windows Update</span><span class="sxs-lookup"><span data-stu-id="e7c30-140">Windows Update</span></span>

  - <span data-ttu-id="e7c30-141">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="e7c30-141">Windows Identity Foundation</span></span>

  - <span data-ttu-id="e7c30-142">Microsoft .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="e7c30-142">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="e7c30-143">Microsoft Visual C++ 2012 ridistribuibile</span><span class="sxs-lookup"><span data-stu-id="e7c30-143">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e7c30-144">Microsoft Visual C++ 2012 Redistributable viene installato automaticamente durante l'installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7c30-144">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="e7c30-145">Non è consigliabile installare e usare altre versioni.</span><span class="sxs-lookup"><span data-stu-id="e7c30-145">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="e7c30-146">Modulo di riscrittura URL versione 2,0 ridistribuibile</span><span class="sxs-lookup"><span data-stu-id="e7c30-146">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="e7c30-147">Runtime in formato Windows Media</span><span class="sxs-lookup"><span data-stu-id="e7c30-147">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="e7c30-148">Versione 3,0 di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7c30-148">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="e7c30-149">Plug-in del browser di Microsoft Silverlight 4 (Silverlight 4.0.50524.0 o la versione più recente per il pannello di controllo di Lync Server)</span><span class="sxs-lookup"><span data-stu-id="e7c30-149">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="e7c30-150">Strumenti dei servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="e7c30-150">Active Directory Domain Services tools</span></span>

<span data-ttu-id="e7c30-151">Alcuni di questi requisiti software si applicano solo a specifici ruoli o componenti del server.</span><span class="sxs-lookup"><span data-stu-id="e7c30-151">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="e7c30-152">Per informazioni dettagliate su questi requisiti software, vedere [requisiti software aggiuntivi per Lync Server 2013](lync-server-2013-additional-software-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="e7c30-152">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

