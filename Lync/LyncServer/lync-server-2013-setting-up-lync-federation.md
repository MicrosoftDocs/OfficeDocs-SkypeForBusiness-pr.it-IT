---
title: 'Lync Server 2013: configurazione della Federazione di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cea596f571064a3b72ecbb3b0c2b56c2179aa315
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="9e708-102">Configurazione della Federazione di Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e708-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e708-103">_**Ultimo argomento modificato:** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="9e708-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="9e708-104">Se il server o i server perimetrali sono già stati distribuiti, l'aggiunta delle funzionalità degli scenari federati è un'operazione semplice.</span><span class="sxs-lookup"><span data-stu-id="9e708-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="9e708-105">Se i server perimetrali non sono stati impostati, è necessario prima eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="9e708-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="9e708-106">Per informazioni dettagliate, vedere: [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) nella documentazione relativa alla pianificazione e [distribuzione di accesso utente esterno in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9e708-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e708-p102">Se si intende configurare una combinazione di federazione XMPP, Lync o connettività di messaggistica istantanea, è possibile effettuare la distribuzione contemporaneamente o un componente alla volta. Se si configurano le opzioni attraverso il Generatore di topologie e Lync Server Management Shell, eseguire la Distribuzione guidata nel server perimetrale dopo avere configurato le opzioni per uno, due o tutti e tre i tipi di federazione. In questo modo si ridurrà il numero di passaggi necessari.</span><span class="sxs-lookup"><span data-stu-id="9e708-p102">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time. If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="9e708-109">Configurazione della federazione Lync nel Generatore di topologie e nella Distribuzione guidata</span><span class="sxs-lookup"><span data-stu-id="9e708-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="9e708-p103">In un server Front End aprire il Generatore di topologie. Espandere Pool di server perimetrali e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali. Scegliere Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="9e708-p103">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="9e708-p104">In Modifica Proprietà, sotto Generale, selezionare Abilita federazione per pool di server perimetrali (porta 5061). Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="9e708-p104">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="9e708-p105">Fare clic su Azione, selezionare Topologia, selezionare Pubblica. Quando viene richiesto di pubblicare la topologia, fare clic su Avanti. Quando la pubblicazione è terminata, fare clic su Fine.</span><span class="sxs-lookup"><span data-stu-id="9e708-p105">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="9e708-p106">Nel server perimetrale, aprire la Distribuzione guidata di Lync Server. Fare clic su Installa o aggiorna il sistema Lync Server, quindi fare clic su Installazione o rimozione componenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9e708-p106">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="9e708-p107">In Installazione componenti di Lync Server fare clic su Avanti. Nella schermata di riepilogo verranno visualizzate le azioni in esecuzione. Al termine della distribuzione, fare clic su Visualizza log per visualizzare i file di log disponibili. Fare clic su Fine per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9e708-p107">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9e708-p108">È possibile selezionare questa opzione, tuttavia solo un pool di server perimetrali o un server perimetrale dell'organizzazione può essere pubblicato esternamente per la federazione. Tutto l'accesso da parte di utenti federati, inclusi gli utenti di messaggistica istantanea pubblica, passa per lo stesso pool di server perimetrali o server perimetrale singolo. Se, ad esempio, la distribuzione include un pool di server perimetrali o un singolo server perimetrale distribuito a New York e uno distribuito a Londra e si abilita il supporto per la federazione nel pool di server perimetrali o nel server perimetrale di New York, il traffico dei segnali per gli utenti federati passerà per il pool di server perimetrali o il singolo server perimetrale di New York. Ciò vale anche per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiami un utente federato di Londra utilizzerà il pool o il server perimetrale di Londra per il traffico audio/video.</span><span class="sxs-lookup"><span data-stu-id="9e708-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="9e708-129">Configurazione della federazione con i partner</span><span class="sxs-lookup"><span data-stu-id="9e708-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="9e708-130">Per configurare correttamente una federazione con un altro Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 o Office Communicator 2007, selezionare il tipo di federazione dalla tabella seguente e definire i record DNS SRV, host DNS (A o AAAA per IPv6) e configurare i criteri applicabili al tipo di Federazione:</span><span class="sxs-lookup"><span data-stu-id="9e708-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="9e708-131">Tipo di federazione</span><span class="sxs-lookup"><span data-stu-id="9e708-131">Federation type</span></span></th>
    <th><span data-ttu-id="9e708-132">Record DNS</span><span class="sxs-lookup"><span data-stu-id="9e708-132">DNS Records</span></span></th>
    <th><span data-ttu-id="9e708-133">Definizione criterio</span><span class="sxs-lookup"><span data-stu-id="9e708-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="9e708-134">Notes</span><span class="sxs-lookup"><span data-stu-id="9e708-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="9e708-135">Dominio partner individuato</span><span class="sxs-lookup"><span data-stu-id="9e708-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="9e708-136">Configurare il record SRV del formato _sipfederationtls. _tcp. &lt;nome&gt;di dominio esterno in cui il valore della porta per il record SRV è TCP 5061 e l' <strong>host che offre questo servizio</strong> è definito come SIP.</span><span class="sxs-lookup"><span data-stu-id="9e708-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="9e708-137">&lt;nome&gt; di dominio esterno – FQDN del servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="9e708-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="9e708-138">Per informazioni dettagliate sulla creazione del record SRV, vedere <a href="lync-server-2013-configure-dns-for-edge-support.md">configurare DNS per il supporto di Edge in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9e708-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="9e708-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9e708-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="9e708-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Abilitare o disabilitare l'individuazione dei partner federativi in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9e708-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="9e708-p110">Nelle versioni precedenti si fa riferimento a questo tipo di federazione come alla <strong>Federazione avanzata aperta</strong>. Questo tipo di federazione richiede la creazione del record SRV e ha lo scopo di consentire agli altri partner di individuare la federazione.</span><span class="sxs-lookup"><span data-stu-id="9e708-p110">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>. The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="9e708-143">Dominio partner consentito</span><span class="sxs-lookup"><span data-stu-id="9e708-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="9e708-144">Configurare il record SRV del formato _sipfederationtls. _tcp. &lt;nome&gt;di dominio esterno in cui il valore della porta per il record SRV è TCP 5061 e l' <strong>host che offre questo servizio</strong> è definito come SIP.</span><span class="sxs-lookup"><span data-stu-id="9e708-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="9e708-145">&lt;nome&gt; di dominio esterno – FQDN del servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="9e708-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="9e708-146">Per informazioni dettagliate sulla creazione del record SRV, vedere <a href="lync-server-2013-configure-dns-for-edge-support.md">configurare DNS per il supporto di Edge in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9e708-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="9e708-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9e708-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="9e708-148">Le versioni precedenti fanno riferimento a questo tipo di federazione come <strong>Federazione avanzata</strong>.</span><span class="sxs-lookup"><span data-stu-id="9e708-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="9e708-149">Per questo tipo di federazione la creazione del record SRV è facoltativa e ha lo scopo di consentire agli altri partner di individuare la federazione.</span><span class="sxs-lookup"><span data-stu-id="9e708-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="9e708-150">Si tratta pertanto di un tipo <strong>Federazione avanzata aperta</strong> o <strong>Dominio partner individuato</strong></span><span class="sxs-lookup"><span data-stu-id="9e708-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="9e708-151">Server partner consentito</span><span class="sxs-lookup"><span data-stu-id="9e708-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="9e708-152">Configurare il nome di dominio SIP e l'FQDN del server perimetrale partner come partner federativo nei criteri</span><span class="sxs-lookup"><span data-stu-id="9e708-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="9e708-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9e708-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="9e708-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configurare il supporto per i domini esterni consentiti in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9e708-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="9e708-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configurare il supporto per i domini esterni bloccati in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9e708-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="9e708-p113">Questo tipo di federazione è la definizione di una relazione uno a uno e non consente l'individuazione di altri partner della federazione. Ogni partner della federazione viene configurato esplicitamente. Nelle versioni precedenti questa funzionalità è denominata <strong>Federazione diretta</strong></span><span class="sxs-lookup"><span data-stu-id="9e708-p113">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners. Each federation partner is configured explicitly. In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="9e708-159">Provider di hosting e Provider di servizi di messaggistica istantanea pubblici</span><span class="sxs-lookup"><span data-stu-id="9e708-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="9e708-160">Per questo tipo di federazione non sono definiti requisiti DNS specifici</span><span class="sxs-lookup"><span data-stu-id="9e708-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="9e708-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9e708-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="9e708-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Creare o modificare provider federati SIP pubblici in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9e708-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="9e708-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Creare o modificare provider federati SIP ospitati Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9e708-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="9e708-164">Questo tipo di federazione definisce servizi e provider di hosting che si desidera configurare per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="9e708-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="9e708-165">Tra gli usi più comuni è inclusa la configurazione per i provider di servizi di messaggistica istantanea pubblici come Windows Live Messenger, Yahoo!</span><span class="sxs-lookup"><span data-stu-id="9e708-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="9e708-166">e AOL, oltre a provider di hosting come Lync Online e Office 365</span><span class="sxs-lookup"><span data-stu-id="9e708-166">and AOL, as well as hosting providers such as Lync Online and Office 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="9e708-167">Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="9e708-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="9e708-168">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="9e708-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="9e708-169">Messenger fino alla data di arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="9e708-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="9e708-170">Una data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="9e708-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="9e708-171">sono stati annunciati.</span><span class="sxs-lookup"><span data-stu-id="9e708-171">has been announced.</span></span> <span data-ttu-id="9e708-172">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9e708-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="9e708-173">Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="9e708-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="9e708-174">Messaggero.</span><span class="sxs-lookup"><span data-stu-id="9e708-174">Messenger.</span></span> <span data-ttu-id="9e708-175">La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</span><span class="sxs-lookup"><span data-stu-id="9e708-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="9e708-176">Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="9e708-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="9e708-177">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="9e708-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="9e708-178">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</span><span class="sxs-lookup"><span data-stu-id="9e708-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="9e708-179">Definire e configurare qualsiasi host DNS richiesto (A o AAAA per IPv6) e record DNS SRV</span><span class="sxs-lookup"><span data-stu-id="9e708-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="9e708-180">Definire e configurare i criteri utilizzando il pannello di controllo di Lync Server o utilizzando Lync Server Management Shell e i cmdlet corretti.</span><span class="sxs-lookup"><span data-stu-id="9e708-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="9e708-181">Per informazioni dettagliate sui cmdlet di Lync Server Management Shell, vedere [cmdlet per la Federazione e l'accesso esterno in Lync server 2013](https://docs.microsoft.com/powershell/module/skype/)</span><span class="sxs-lookup"><span data-stu-id="9e708-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e708-182">Lync room System (LRS) non Mostra il pulsante Join per le riunioni inviate dagli organizzatori nei partner di Lync federati.</span><span class="sxs-lookup"><span data-stu-id="9e708-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="9e708-183">Affinché un collegamento di partecipazione alle riunioni venga visualizzato in LRS, l'organizzazione di invio deve abilitare TNEF utilizzando il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="9e708-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="9e708-184">Si noti che non è specifico di LRS.</span><span class="sxs-lookup"><span data-stu-id="9e708-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="9e708-185">Anche Outlook e Lync non visualizzano i collegamenti di join in questo caso, poiché le proprietà MAPI non vengono trasportate, ma nel caso di Outlook, l'utente può aprire l'invito alla riunione e fare clic sull'URL della riunione.</span><span class="sxs-lookup"><span data-stu-id="9e708-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="9e708-186">Quando TNEFEnabled è impostato su true Exchange 2013 non rimuove le proprietà MAPI incluso OnlineMeetingExternalLink e il pulsante join verrà visualizzato nel promemoria.</span><span class="sxs-lookup"><span data-stu-id="9e708-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9e708-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e708-187">See Also</span></span>


[<span data-ttu-id="9e708-188">Pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e708-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="9e708-189">Gestione della Federazione e dell'accesso esterno a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e708-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

