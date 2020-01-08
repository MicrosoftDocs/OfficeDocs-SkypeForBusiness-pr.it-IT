---
title: 'Lync Server 2013: Configurazione della federazione di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6dc0a2aeb39c86db54d21a2c4be5ff6c5be599
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="cf9a3-102">Configurazione della federazione di Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf9a3-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf9a3-103">_**Argomento Ultima modifica:** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="cf9a3-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="cf9a3-104">Se si è già distribuito Edge Server o server, l'aggiunta delle caratteristiche degli scenari federati è semplice.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="cf9a3-105">Se non è stato configurato Edge Server, è necessario farlo per primo.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="cf9a3-106">Per informazioni dettagliate, vedere [pianificazione per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) nella documentazione di pianificazione e [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf9a3-107">Se si intende configurare una combinazione di federazione XMPP, Federazione Lync o connettività di messaggistica istantanea pubblica, è possibile distribuirle contemporaneamente o una alla volta.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-107">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time.</span></span> <span data-ttu-id="cf9a3-108">Se si configurano le opzioni tramite il generatore di topologia e Lync Server Management Shell, eseguire la distribuzione guidata su Edge Server dopo la configurazione delle opzioni per uno, due o tutti e tre i tipi di federazione, è possibile ridurre il numero di passaggi necessari.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-108">If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="cf9a3-109">Configurazione della federazione Lync in Generatore di topologie e distribuzione guidata</span><span class="sxs-lookup"><span data-stu-id="cf9a3-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="cf9a3-110">In un server front-end aprire Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-110">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="cf9a3-111">Espandere pool di bordi e quindi fare clic con il pulsante destro del mouse sull'Edge Server o sul pool Edge Server.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-111">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="cf9a3-112">Selezionare Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-112">Select Edit properties.</span></span>

2.  <span data-ttu-id="cf9a3-113">In modifica proprietà in generale selezionare Abilita federazione per questo pool di bordi (porta 5061).</span><span class="sxs-lookup"><span data-stu-id="cf9a3-113">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="cf9a3-114">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-114">Click OK.</span></span>

3.  <span data-ttu-id="cf9a3-115">Fare clic su azione, selezionare topologia, quindi pubblica.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-115">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="cf9a3-116">Quando viene richiesto di pubblicare la topologia, fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-116">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="cf9a3-117">Al termine della pubblicazione, fare clic su fine.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-117">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="cf9a3-118">Nell'Edge Server aprire la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-118">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="cf9a3-119">Fare clic su Installa o aggiorna Lync Server System, quindi fare clic su Imposta o Rimuovi componenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-119">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="cf9a3-120">Fare di nuovo clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-120">Click Run Again.</span></span>

5.  <span data-ttu-id="cf9a3-121">In configurazione componenti di Lync Server fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-121">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="cf9a3-122">La schermata di riepilogo mostrerà le azioni Man mano che vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-122">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="cf9a3-123">Dopo aver completato la distribuzione, fare clic su Visualizza log per visualizzare i file di log disponibili.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-123">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="cf9a3-124">Fare clic su fine per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-124">Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cf9a3-125">È possibile selezionare questa opzione, ma è possibile pubblicare esternamente per la Federazione solo un pool di Edge o un server perimetrale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-125">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="cf9a3-126">Tutti gli accessi da parte di utenti federati, inclusi gli utenti di messaggistica istantanea pubblica, passano attraverso lo stesso pool di Edge o un singolo Edge Server.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-126">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="cf9a3-127">Ad esempio, se la distribuzione include un pool di Edge o un server perimetrale distribuito in New York e uno distribuito a Londra e si Abilita il supporto federativo per il pool Edge di New York o un singolo Edge Server, il traffico di segnale per gli utenti federati passerà attraverso New York Edge pool o Single Edge Server.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-127">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="cf9a3-128">Ciò avviene persino per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiama un utente federato di Londra utilizza il pool o il server perimetrale di Londra per il traffico A/V.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-128">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="cf9a3-129">Configurazione della Federazione con i partner</span><span class="sxs-lookup"><span data-stu-id="cf9a3-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="cf9a3-130">Per configurare una Federazione di successo con un altro Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 o Office Communicator 2007, selezionare il tipo di federazione dalla tabella seguente e definire i record SRV DNS, host DNS (A o AAAA per IPv6) e configurare i criteri applicabili al tipo di Federazione:</span><span class="sxs-lookup"><span data-stu-id="cf9a3-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="cf9a3-131">Tipo di Federazione</span><span class="sxs-lookup"><span data-stu-id="cf9a3-131">Federation type</span></span></th>
    <th><span data-ttu-id="cf9a3-132">Record DNS</span><span class="sxs-lookup"><span data-stu-id="cf9a3-132">DNS Records</span></span></th>
    <th><span data-ttu-id="cf9a3-133">Definizione dei criteri</span><span class="sxs-lookup"><span data-stu-id="cf9a3-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="cf9a3-134">Note</span><span class="sxs-lookup"><span data-stu-id="cf9a3-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="cf9a3-135">Dominio del partner individuato</span><span class="sxs-lookup"><span data-stu-id="cf9a3-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="cf9a3-136">Configurare il record SRV del formato _sipfederationtls. _tcp. &lt;nome&gt;di dominio esterno in cui il valore della porta per il record SRV è TCP 5061 e l' <strong>host che offre questo servizio</strong> è definito come SIP.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="cf9a3-137">&lt;Domain Name esterno&gt; : il nome di dominio completo del servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="cf9a3-138">Per informazioni dettagliate sulla creazione del record SRV, vedere <a href="lync-server-2013-configure-dns-for-edge-support.md">configurare DNS per il supporto Edge in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cf9a3-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="cf9a3-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cf9a3-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="cf9a3-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Abilitare o disabilitare l'individuazione dei partner della federazione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cf9a3-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="cf9a3-141">Le versioni precedenti fanno riferimento a questo tipo di federazione come <strong>Federazione avanzata aperta</strong>.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-141">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>.</span></span> <span data-ttu-id="cf9a3-142">La creazione del record SRV è necessaria per questo tipo di Federazione e consente ad altri partner di individuare la Federazione.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-142">The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="cf9a3-143">Dominio partner consentito</span><span class="sxs-lookup"><span data-stu-id="cf9a3-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="cf9a3-144">Configurare il record SRV del formato _sipfederationtls. _tcp. &lt;nome&gt;di dominio esterno in cui il valore della porta per il record SRV è TCP 5061 e l' <strong>host che offre questo servizio</strong> è definito come SIP.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="cf9a3-145">&lt;Domain Name esterno&gt; : il nome di dominio completo del servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="cf9a3-146">Per informazioni dettagliate sulla creazione del record SRV, vedere <a href="lync-server-2013-configure-dns-for-edge-support.md">configurare DNS per il supporto Edge in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cf9a3-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="cf9a3-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cf9a3-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="cf9a3-148">Le versioni precedenti fanno riferimento a questo tipo di federazione come <strong>Federazione avanzata</strong>.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="cf9a3-149">La creazione del record SRV è facoltativa per questo tipo di Federazione e consente ad altri partner di individuare la Federazione.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="cf9a3-150">Naturalmente, si tratta di una <strong>Federazione avanzata aperta</strong>o di un <strong>dominio partner individuato</strong></span><span class="sxs-lookup"><span data-stu-id="cf9a3-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="cf9a3-151">Server partner consentiti</span><span class="sxs-lookup"><span data-stu-id="cf9a3-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="cf9a3-152">Configurare il nome di dominio SIP e l'FQDN di partner Edge Server come partner federativo nei criteri</span><span class="sxs-lookup"><span data-stu-id="cf9a3-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="cf9a3-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cf9a3-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="cf9a3-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configurare il supporto per i domini esterni consentiti in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cf9a3-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="cf9a3-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configurare il supporto per i domini esterni bloccati in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cf9a3-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="cf9a3-156">Questo tipo di federazione è la definizione di una relazione uno-a-uno e non consente l'individuazione di altri partner federativi.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-156">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners.</span></span> <span data-ttu-id="cf9a3-157">Ogni partner federativo è configurato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-157">Each federation partner is configured explicitly.</span></span> <span data-ttu-id="cf9a3-158">Nelle versioni precedenti questa operazione era denominata <strong>Federazione diretta</strong></span><span class="sxs-lookup"><span data-stu-id="cf9a3-158">In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="cf9a3-159">Provider di hosting e provider di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="cf9a3-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="cf9a3-160">Non sono definiti requisiti DNS specifici per questo tipo di Federazione</span><span class="sxs-lookup"><span data-stu-id="cf9a3-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="cf9a3-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cf9a3-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="cf9a3-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Creare o modificare provider federati SIP pubblici in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cf9a3-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="cf9a3-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Creare o modificare provider federati SIP ospitati in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cf9a3-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="cf9a3-164">Questo tipo di Federazione definisce i servizi e i provider di hosting che si desidera configurare per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="cf9a3-165">Gli usi tipici includono la configurazione per i provider di messaggistica istantanea pubblici come Windows Live Messenger, Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cf9a3-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="cf9a3-166">e AOL, oltre a provider di hosting, ad esempio Lync Online e Office 365</span><span class="sxs-lookup"><span data-stu-id="cf9a3-166">and AOL, as well as hosting providers such as Lync Online and Office 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="cf9a3-167">A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="cf9a3-168">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cf9a3-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="cf9a3-169">Messenger fino alla data di chiusura del servizio.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="cf9a3-170">Data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cf9a3-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="cf9a3-171">è stato annunciato.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-171">has been announced.</span></span> <span data-ttu-id="cf9a3-172">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="cf9a3-173">Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cf9a3-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="cf9a3-174">Messenger.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-174">Messenger.</span></span> <span data-ttu-id="cf9a3-175">La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="cf9a3-176">Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="cf9a3-177">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="cf9a3-178">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="cf9a3-179">Definire e configurare l'host DNS obbligatorio (A o AAAA per IPv6) e i record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="cf9a3-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="cf9a3-180">Definire e configurare i criteri usando il pannello di controllo di Lync Server o usando Lync Server Management Shell e i cmdlet appropriati.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="cf9a3-181">Per informazioni dettagliate sui cmdlet di Lync Server Management Shell, vedere [cmdlet federativo e Access esterni in Lync server 2013](https://docs.microsoft.com/powershell/module/skype/)</span><span class="sxs-lookup"><span data-stu-id="cf9a3-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf9a3-182">Lync room System (LRS) non Mostra il pulsante partecipa per le riunioni inviate dagli organizzatori in partner Lync federati.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="cf9a3-183">Per visualizzare un collegamento a una riunione di join in LRS, l'organizzazione di invio deve abilitare il formato TNEF usando il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="cf9a3-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="cf9a3-184">Tieni presente che questo non è LRS specifico.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="cf9a3-185">Anche Outlook e Lync non visualizzano collegamenti di join in questo caso, poiché le proprietà MAPI non vengono trasportate, ma nel caso di Outlook l'utente può aprire l'invito alla riunione e fare clic sull'URL della riunione.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="cf9a3-186">Quando TNEFEnabled è impostato su true Exchange 2013 non esegue il striping delle proprietà MAPI incluso OnlineMeetingExternalLink e il pulsante partecipa verrà visualizzato nel promemoria.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cf9a3-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf9a3-187">See Also</span></span>


[<span data-ttu-id="cf9a3-188">Pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf9a3-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="cf9a3-189">Gestione della federazione e dell'accesso esterno a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf9a3-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

