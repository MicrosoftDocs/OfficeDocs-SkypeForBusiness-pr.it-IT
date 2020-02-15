---
title: Definire e configurare un pool Front end o un server Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f35c49ab232bd69184191ab841431e6c80eca20a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="9c039-102">Definire e configurare un pool Front end o un server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c039-102">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c039-103">_**Ultimo argomento modificato:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="9c039-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="9c039-p101">Per questa procedura non è necessaria l'appartenenza a un gruppo di amministratori locali o di dominio privilegiato, ma è consigliabile accedere a un computer come utente standard.</span><span class="sxs-lookup"><span data-stu-id="9c039-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="9c039-106">Se si sta distribuendo un server Enterprise, è necessario che il numero minimo di front end server in un pool sia sempre in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9c039-106">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="9c039-107">I requisiti di versione sono riassunti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9c039-107">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c039-108">Numero totale di Front End Server nel pool</span><span class="sxs-lookup"><span data-stu-id="9c039-108">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="9c039-109">Numero minimo di server attivi per il funzionamento del pool</span><span class="sxs-lookup"><span data-stu-id="9c039-109">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c039-110">1-2</span><span class="sxs-lookup"><span data-stu-id="9c039-110">1-2</span></span></p></td>
<td><p><span data-ttu-id="9c039-111">1 </span><span class="sxs-lookup"><span data-stu-id="9c039-111">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c039-112">3-4</span><span class="sxs-lookup"><span data-stu-id="9c039-112">3-4</span></span></p></td>
<td><p><span data-ttu-id="9c039-113">2 </span><span class="sxs-lookup"><span data-stu-id="9c039-113">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c039-114">5-6</span><span class="sxs-lookup"><span data-stu-id="9c039-114">5-6</span></span></p></td>
<td><p><span data-ttu-id="9c039-115">3 </span><span class="sxs-lookup"><span data-stu-id="9c039-115">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c039-116">7-8</span><span class="sxs-lookup"><span data-stu-id="9c039-116">7-8</span></span></p></td>
<td><p><span data-ttu-id="9c039-117">4 </span><span class="sxs-lookup"><span data-stu-id="9c039-117">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c039-118">9-10</span><span class="sxs-lookup"><span data-stu-id="9c039-118">9-10</span></span></p></td>
<td><p><span data-ttu-id="9c039-119">5 </span><span class="sxs-lookup"><span data-stu-id="9c039-119">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c039-120">11-12</span><span class="sxs-lookup"><span data-stu-id="9c039-120">11-12</span></span></p></td>
<td><p><span data-ttu-id="9c039-121">6 </span><span class="sxs-lookup"><span data-stu-id="9c039-121">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="9c039-122">Per Lync Server 2013, ogni volta che si aggiunge o si rimuove un front end server dal pool, è necessario riavviare i servizi.</span><span class="sxs-lookup"><span data-stu-id="9c039-122">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="9c039-123">La rimozione e l'aggiunta di server devono essere eseguite come operazioni separate.</span><span class="sxs-lookup"><span data-stu-id="9c039-123">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="9c039-124">Ad esempio, se si intende aggiungere due front end server e rimuovere due front end server, utilizzare il processo seguente:</span><span class="sxs-lookup"><span data-stu-id="9c039-124">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="9c039-125">Rimuovere i due Front End Server</span><span class="sxs-lookup"><span data-stu-id="9c039-125">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="9c039-126">Pubblicare e riattivare la topologia.</span><span class="sxs-lookup"><span data-stu-id="9c039-126">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="9c039-127">Riavviare i servizi.</span><span class="sxs-lookup"><span data-stu-id="9c039-127">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="9c039-128">Aggiungere i due Front End Server</span><span class="sxs-lookup"><span data-stu-id="9c039-128">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="9c039-129">Pubblicare e riattivare la topologia.</span><span class="sxs-lookup"><span data-stu-id="9c039-129">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="9c039-130">Riavviare i servizi.</span><span class="sxs-lookup"><span data-stu-id="9c039-130">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="9c039-131">Dopo aver definito la topologia, utilizzare la procedura seguente per definire un pool Front end per il sito.</span><span class="sxs-lookup"><span data-stu-id="9c039-131">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="9c039-132">Per informazioni dettagliate sulla definizione della topologia, vedere [definire e configurare una topologia in Generatore di topologie per Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="9c039-132">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="9c039-133">Per definire un pool Front End</span><span class="sxs-lookup"><span data-stu-id="9c039-133">To define a Front End pool</span></span>

1.  <span data-ttu-id="9c039-134">Nella pagina **Definire il nuovo pool Front End** della procedura guidata Definisci nuovo pool Front End fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9c039-134">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="9c039-135">Nella pagina **definire l'FQDN del pool Front End** immettere un nome di dominio completo (FQDN) per il pool in cui si sta creando, fare clic su **Enterprise Edition Front End pool**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9c039-135">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="9c039-136">Nella pagina **definire i computer in questo pool** , immettere un nome di dominio completo del computer per il primo front end server nel pool e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9c039-136">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="9c039-137">Ripetere questo passaggio per tutti i computer aggiuntivi (fino a dodici anni) che si desidera aggiungere al pool e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9c039-137">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="9c039-138">Nella pagina **Selezionare funzionalità** selezionare le caselle di controllo corrispondenti alle caratteristiche desiderate per il pool Front End.</span><span class="sxs-lookup"><span data-stu-id="9c039-138">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="9c039-139">Ad esempio, se si stanno distribuendo solo le funzionalità di messaggistica istantanea e presenza, è necessario selezionare la casella di controllo per consentire la messaggistica istantanea a più parti, ma non selezionare le caselle di controllo per le conferenze telefoniche **con accesso esterno**, **VoIP aziendale**o di **ammissione di chiamata** , perché **rappresentano le funzionalità** di conferenza vocale, video e di collaborazione.</span><span class="sxs-lookup"><span data-stu-id="9c039-139">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="9c039-140">\*\*\*\*   Servizi di conferenza questa selezione consente di abilitare una serie completa di funzionalità, tra cui:</span><span class="sxs-lookup"><span data-stu-id="9c039-140">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="9c039-141">Messaggistica istantanea con più di due partecipanti in una sessione</span><span class="sxs-lookup"><span data-stu-id="9c039-141">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="9c039-142">Servizio di conferenza, che include la collaborazione sui documenti, la condivisione di applicazioni e la condivisione del desktop</span><span class="sxs-lookup"><span data-stu-id="9c039-142">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="9c039-143">A/V Conferencing, che consente agli utenti di disporre di conferenze audio/video (A/V) in tempo reale senza dover utilizzare servizi esterni, come il servizio Live Meeting o un ponte audio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9c039-143">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="9c039-144">**Le conferenze**   telefoniche con accesso esterno (PSTN) consentono agli utenti di partecipare alla parte audio di una conferenza di Lync Server 2013 utilizzando un telefono PSTN senza dover utilizzare un provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="9c039-144">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="9c039-145">**Enterprise Voice**   Enterprise Voice è la soluzione VoIP (Voice over IP) in Lync Server 2013 che consente agli utenti di effettuare e ricevere chiamate telefoniche.</span><span class="sxs-lookup"><span data-stu-id="9c039-145">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="9c039-146">Questa caratteristica viene distribuita se si prevede di utilizzare Lync Server 2013 per le chiamate vocali, la segreteria telefonica e altre funzioni che utilizzano un dispositivo hardware o un client software.</span><span class="sxs-lookup"><span data-stu-id="9c039-146">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="9c039-147">**Il controllo di ammissione di chiamata**   CAC determina, in base alla larghezza di banda di rete disponibile, se consentire la creazione di sessioni di comunicazione in tempo reale, ad esempio chiamate vocali o video.</span><span class="sxs-lookup"><span data-stu-id="9c039-147">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="9c039-148">Se si distribuiscono solo le funzionalità di messaggistica istantanea e presenza, il controllo di ammissione di chiamata non è necessario, perché non è utilizzato da nessuna di queste due funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9c039-148">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="9c039-149">**Archiviazione archiviazione**consente di archiviare il contenuto di messaggistica istantanea, il contenuto delle conferenze (riunioni) o entrambi inviati tramite Lync Server 2013.   </span><span class="sxs-lookup"><span data-stu-id="9c039-149">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="9c039-150">**Monitoring**   Server Monitoring consente di raccogliere dati numerici che descrivono la qualità multimediale della rete e degli endpoint, le informazioni sull'utilizzo relative alle chiamate VoIP, i messaggi di messaggistica istantanea, le conversazioni a/V, le riunioni, la condivisione di applicazioni e i trasferimenti di file e le informazioni sulla risoluzione dei problemi per le chiamate non riuscite.</span><span class="sxs-lookup"><span data-stu-id="9c039-150">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="9c039-p109">Se si desidera abilitare il servizio Controllo di ammissione di chiamata nella distribuzione, è necessario abilitarlo esattamente in un pool per ogni sito centrale. È consigliabile abilitare questo servizio quando si distribuiscono caratteristiche vocali o conferenze audio/video.</span><span class="sxs-lookup"><span data-stu-id="9c039-p109">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site. CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="9c039-p110">Nella tabella seguente vengono indicate le caratteristiche disponibili (in alto) e le funzioni offerte agli utenti (a sinistra). Le selezioni indicate nella tabella corrispondono alle opzioni che è necessario selezionare per abilitare queste caratteristiche per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9c039-p110">The following table shows the available features (top) and the functions offered to users (left). The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th><span data-ttu-id="9c039-155">Conferenza</span><span class="sxs-lookup"><span data-stu-id="9c039-155">Conferencing</span></span></th>
    <th><span data-ttu-id="9c039-156">Conferenze telefoniche con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="9c039-156">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="9c039-157">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="9c039-157">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="9c039-158">Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="9c039-158">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="9c039-159">Messaggistica istantanea e presenza</span><span class="sxs-lookup"><span data-stu-id="9c039-159">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="9c039-160">X</span><span class="sxs-lookup"><span data-stu-id="9c039-160">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="9c039-161">Conferenza</span><span class="sxs-lookup"><span data-stu-id="9c039-161">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="9c039-162">X</span><span class="sxs-lookup"><span data-stu-id="9c039-162">X</span></span></p></td>
    <td><p><span data-ttu-id="9c039-163">X</span><span class="sxs-lookup"><span data-stu-id="9c039-163">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="9c039-164">A/V conferencing</span><span class="sxs-lookup"><span data-stu-id="9c039-164">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="9c039-165">X</span><span class="sxs-lookup"><span data-stu-id="9c039-165">X</span></span></p></td>
    <td><p><span data-ttu-id="9c039-166">X</span><span class="sxs-lookup"><span data-stu-id="9c039-166">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="9c039-167">X</span><span class="sxs-lookup"><span data-stu-id="9c039-167">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="9c039-168">VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="9c039-168">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="9c039-169">X</span><span class="sxs-lookup"><span data-stu-id="9c039-169">X</span></span></p></td>
    <td><p><span data-ttu-id="9c039-170">X</span><span class="sxs-lookup"><span data-stu-id="9c039-170">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="9c039-171">Nella pagina **Selezione ruoli server collocato** è possibile collocare il Mediation Server nel front end server o distribuirlo come server autonomo.</span><span class="sxs-lookup"><span data-stu-id="9c039-171">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="9c039-172">È possibile collocare il Mediation Server nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="9c039-172">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="9c039-173">Se si intende collocare il Mediation Server nel pool Enterprise Edition front end, verificare che sia selezionata la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="9c039-173">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="9c039-174">I ruoli del server verranno distribuiti nei server del pool.</span><span class="sxs-lookup"><span data-stu-id="9c039-174">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="9c039-175">Se si intende distribuire il Mediation Server come server autonomo, deselezionare la casella di controllo appropriata.</span><span class="sxs-lookup"><span data-stu-id="9c039-175">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="9c039-176">Si distribuirà Mediation Server in un passaggio di distribuzione separato dopo aver completamente distribuito il front end server.</span><span class="sxs-lookup"><span data-stu-id="9c039-176">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="9c039-177">È consigliabile aggiungere Mediation Server nella stessa posizione, se possibile.</span><span class="sxs-lookup"><span data-stu-id="9c039-177">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="9c039-178">Per informazioni dettagliate sul supporto per i Mediation Server collocati o autonomi, vedere <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">componenti e topologie per Mediation Server in Lync server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="9c039-178">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="9c039-179">I **ruoli del server associato con questa pagina del pool Front End** consentono di definire e associare i ruoli del server al pool Front end.</span><span class="sxs-lookup"><span data-stu-id="9c039-179">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="9c039-180">È disponibile il seguente ruolo:</span><span class="sxs-lookup"><span data-stu-id="9c039-180">The following role is available:</span></span>
    
    <span data-ttu-id="9c039-181">**Abilitazione**   di un pool di server perimetrali, definisce e associa un singolo perimetro o un pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="9c039-181">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="9c039-182">Un server perimetrale facilita la comunicazione e la collaborazione tra gli utenti all'interno dell'organizzazione e le persone esterne all'organizzazione, inclusi gli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="9c039-182">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="9c039-183">Esistono due possibili scenari che è possibile utilizzare per distribuire e associare i ruoli del server:</span><span class="sxs-lookup"><span data-stu-id="9c039-183">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="9c039-p116">Per il primo scenario, è necessario definire una nuova topologia per una nuova installazione. È possibile eseguire l'installazione scegliendo tra due metodi diversi:</span><span class="sxs-lookup"><span data-stu-id="9c039-p116">For scenario one, you are defining a new topology for a new installation. You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="9c039-186">Lasciare deselezionate tutte le caselle di controllo e continuare con la definizione della topologia.</span><span class="sxs-lookup"><span data-stu-id="9c039-186">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="9c039-187">Dopo aver pubblicato, configurato e testato i ruoli del server front-end e back-end, è possibile eseguire di nuovo il generatore di topologie per aggiungere i server di ruoli alla topologia.</span><span class="sxs-lookup"><span data-stu-id="9c039-187">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="9c039-188">Questa strategia consentirà di verificare il pool Front end e il server che esegue SQL Server senza ulteriori complicazioni da ruoli aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="9c039-188">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="9c039-189">Dopo aver completato il testing iniziale, è possibile eseguire di nuovo il generatore di topologie per selezionare i ruoli che è necessario distribuire.</span><span class="sxs-lookup"><span data-stu-id="9c039-189">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="9c039-190">Selezionare i ruoli che è necessario installare e quindi configurare l'hardware per gestire i ruoli selezionati.</span><span class="sxs-lookup"><span data-stu-id="9c039-190">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="9c039-191">Per lo scenario 2 si dispone di una distribuzione esistente e l'infrastruttura è pronta per i nuovi ruoli oppure è necessario associare i ruoli esistenti a un nuovo front end server:</span><span class="sxs-lookup"><span data-stu-id="9c039-191">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="9c039-192">In questo caso, verranno selezionati i ruoli che si intende distribuire o associare al nuovo front end server.</span><span class="sxs-lookup"><span data-stu-id="9c039-192">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="9c039-193">In entrambi i casi, sarà necessario procedere con la definizione dei ruoli, la configurazione dell'hardware necessario e l'installazione.</span><span class="sxs-lookup"><span data-stu-id="9c039-193">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="9c039-194">Nella pagina **Definire archivio SQL** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9c039-194">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9c039-195">Per utilizzare un archivio di SQL Server esistente già definito nella topologia, selezionare **Archivio SQL**.</span><span class="sxs-lookup"><span data-stu-id="9c039-195">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="9c039-196">Per definire una nuova istanza di SQL Server per archiviare le informazioni sul pool, fare clic su **nuovo** e quindi specificare il **nome di dominio completo di SQL Server**nella finestra di dialogo **Definisci nuovo archivio SQL** .</span><span class="sxs-lookup"><span data-stu-id="9c039-196">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="9c039-197">Per specificare il nome di un'istanza di SQL Server, selezionare **Istanza denominata** e quindi specificare il nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="9c039-197">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="9c039-198">Per utilizzare l'istanza predefinita, fare clic su **Istanza predefinita**.</span><span class="sxs-lookup"><span data-stu-id="9c039-198">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="9c039-199">Per utilizzare il mirroring SQL, selezionare **Abilita mirroring SQL** e selezionare un'istanza esistente, o creare una nuova istanza.</span><span class="sxs-lookup"><span data-stu-id="9c039-199">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="9c039-200">Nella pagina **Definire condivisione file** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9c039-200">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9c039-201">Per utilizzare una condivisione file già definita nella topologia, selezionare **Utilizza condivisione file definita in precedenza**.</span><span class="sxs-lookup"><span data-stu-id="9c039-201">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="9c039-202">Per definire una nuova condivisione file, selezionare **Definisci nuova condivisione file**, nella casella **FQDN file server** immettere l'FQDN del file server esistente in cui deve trovarsi la condivisione file e quindi immettere un nome per la condivisione nella casella **Condivisione file**.</span><span class="sxs-lookup"><span data-stu-id="9c039-202">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="9c039-203">La condivisione file per Lync Server 2013 non può essere posizionata nel front end server.</span><span class="sxs-lookup"><span data-stu-id="9c039-203">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="9c039-204">Si noti che in questo esempio la condivisione file è stata posizionata nel server Back End Server basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9c039-204">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="9c039-205">Questa posizione può non risultare ottimale per i requisiti dell'organizzazione e un file server può rappresentare una scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="9c039-205">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="9c039-206">È possibile definire la condivisione file senza che questa sia stata creata.</span><span class="sxs-lookup"><span data-stu-id="9c039-206">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="9c039-207">Sarà necessario creare la condivisione file nella posizione definita prima di pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="9c039-207">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="9c039-208">Nella pagina **Specificare l'URL dei servizi Web** eseguire una o entrambe le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9c039-208">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="9c039-209">L'URL di base è l'identità dei servizi Web per l'URL meno https://.</span><span class="sxs-lookup"><span data-stu-id="9c039-209">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="9c039-210">Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net, l'URL di base è pool01.contoso.NET.</span><span class="sxs-lookup"><span data-stu-id="9c039-210">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="9c039-211">Se si dispone di più di un pool Front end o front end server, l'FQDN dei servizi Web esterni deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="9c039-211">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="9c039-212">Ad esempio, se si definisce l'FQDN dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile utilizzare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front end o front end server.</span><span class="sxs-lookup"><span data-stu-id="9c039-212">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="9c039-213">Se si sta configurando il bilanciamento del carico DNS, selezionare la casella di controllo **Sostituisci FQDN pool servizi Web interni** , immettere l'URL di base interno (che deve essere diverso dall'FQDN del pool e potrebbe essere\<, ad esempio\>, Internal-your base URL) in **URL di base interno**.</span><span class="sxs-lookup"><span data-stu-id="9c039-213">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="9c039-214">Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="9c039-214">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="9c039-215"><STRONG>Utilizzare solo caratteri standard</STRONG> (tra cui a – z, a – z, 0 – 9 e trattini) per la definizione di URL o di nomi di dominio completi.</span><span class="sxs-lookup"><span data-stu-id="9c039-215"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="9c039-216">Non utilizzare caratteri Unicode o di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="9c039-216">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="9c039-217">I caratteri non standard in un URL o FQDN spesso non sono supportati dal DNS esterno e dalle CA pubbliche (ovvero, quando l'URL o il nome di dominio completo deve essere assegnato al nome del soggetto o all'oggetto alternativo del soggetto nel certificato).</span><span class="sxs-lookup"><span data-stu-id="9c039-217">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="9c039-218">Facoltativamente, immettere l'URL di base esterno in **URL di base esterno**.</span><span class="sxs-lookup"><span data-stu-id="9c039-218">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="9c039-219">È necessario immettere l'URL di base esterno per differenziarlo dalla denominazione di dominio interno.</span><span class="sxs-lookup"><span data-stu-id="9c039-219">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="9c039-220">Si supponga, ad esempio, che il nome di dominio interno sia contoso.net e il nome di dominio esterno sia contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9c039-220">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="9c039-221">In questo caso, l'URL verrebbe definito con il nome di dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9c039-221">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="9c039-222">Questo è un aspetto importante anche nel caso di un proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="9c039-222">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="9c039-223">Il nome di dominio dell'URL di base esterno è lo stesso del nome di dominio dell'FQDN del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="9c039-223">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="9c039-224">La messaggistica istantanea e la presenza richiedono l'accesso HTTP al pool Front end.</span><span class="sxs-lookup"><span data-stu-id="9c039-224">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="9c039-225">Per utilizzare il bilanciamento del carico DNS, è necessario creare i record DNS appropriati.</span><span class="sxs-lookup"><span data-stu-id="9c039-225">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="9c039-226">Per ulteriori informazioni, vedere <A href="lync-server-2013-configure-dns-for-load-balancing.md">configurare DNS per il bilanciamento del carico in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9c039-226">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="9c039-227">Se nella pagina **Selezione funzionalità** è stata selezionata l'opzione servizi di **conferenza** , nella pagina selezionare **un server Office Web Apps** selezionare **Associa pool a un server Office Web Apps** e quindi fare clic su **nuovo** (o selezionare un server Office Web Apps esistente nell'elenco a discesa).</span><span class="sxs-lookup"><span data-stu-id="9c039-227">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="9c039-228">Nella finestra di dialogo **Definire un nuovo server Office Web Apps** digitare il nome di dominio completo (FQDN) del computer del server Office Web Apps nella casella **FQDN server Office Web Apps**. L'URL di individuazione del server Office Web Apps dovrebbe comparire così automaticamente nella casella **URL di individuazione server Office Web Apps**.</span><span class="sxs-lookup"><span data-stu-id="9c039-228">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="9c039-229">Se il server Office Web Apps è installato in locale e nella stessa area di rete di Lync Server 2013, il **Server Office Web Apps Option è distribuito in una rete esterna (ovvero perimetro/Internet)** non deve essere selezionata.</span><span class="sxs-lookup"><span data-stu-id="9c039-229">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="9c039-230">Se il server Office Web Apps è distribuito all'esterno del firewall interno, allora selezionare l'opzione **Il server Office Web Apps è distribuito in una rete esterna (perimetro/Internet)**.</span><span class="sxs-lookup"><span data-stu-id="9c039-230">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="9c039-231">Per ulteriori informazioni, vedere <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">configurazione dell'integrazione con Office Web Apps Server e Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9c039-231">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="9c039-232">Nella pagina **Definire l'archivio SQL Server per l'archiviazione**, selezionare un'istanza SQL Server esistente, o definire una nuova istanza per l'archiviazione dei dati associati ai dati di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9c039-232">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="9c039-233">Nella pagina **Definire l'archivio SQL Server per il monitoraggio**, selezionare un'istanza SQL Server esistente, o definire una nuova istanza per l'archiviazione dei dati associati ai dati di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="9c039-233">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="9c039-234">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9c039-234">Click **Next**.</span></span> <span data-ttu-id="9c039-235">Se sono stati definiti altri server di ruoli nella pagina **associa ruoli server al pool Front End** , verranno aperte le pagine della configurazione guidata ruolo separate che consentono di configurare i ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="9c039-235">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="9c039-236">Per ulteriori dettagli, vedere:</span><span class="sxs-lookup"><span data-stu-id="9c039-236">For details, see the following:</span></span>
    
    [<span data-ttu-id="9c039-237">Distribuzione dell'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c039-237">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="9c039-238">Se non sono stati selezionati altri ruoli del server da configurare e distribuire oppure al termine della configurazione dei ruoli del server aggiuntivi, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="9c039-238">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

