---
title: Definire e configurare un pool Front End o un server Standard Edition
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
ms.openlocfilehash: ddc430370c59e279e0e36aa662da0f33973e0d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="d0134-102">Definire e configurare un pool Front End o un server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0134-102">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0134-103">_**Argomento Ultima modifica:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="d0134-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="d0134-104">Questa procedura non richiede l'appartenenza a un amministratore locale o a un gruppo di domini privilegiati.</span><span class="sxs-lookup"><span data-stu-id="d0134-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="d0134-105">È necessario accedere a un computer come utente standard.</span><span class="sxs-lookup"><span data-stu-id="d0134-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="d0134-106">Se si distribuisce un server aziendale, è necessario che un numero minimo di server front-end in un pool sia sempre in uso.</span><span class="sxs-lookup"><span data-stu-id="d0134-106">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="d0134-107">Nella tabella seguente vengono riepilogati questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="d0134-107">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0134-108">Numero totale di server front-end nel pool</span><span class="sxs-lookup"><span data-stu-id="d0134-108">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="d0134-109">Numero di server che devono essere in uso per il pool per essere funzionali</span><span class="sxs-lookup"><span data-stu-id="d0134-109">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0134-110">1-2</span><span class="sxs-lookup"><span data-stu-id="d0134-110">1-2</span></span></p></td>
<td><p><span data-ttu-id="d0134-111">1</span><span class="sxs-lookup"><span data-stu-id="d0134-111">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0134-112">3-4</span><span class="sxs-lookup"><span data-stu-id="d0134-112">3-4</span></span></p></td>
<td><p><span data-ttu-id="d0134-113">2</span><span class="sxs-lookup"><span data-stu-id="d0134-113">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0134-114">5-6</span><span class="sxs-lookup"><span data-stu-id="d0134-114">5-6</span></span></p></td>
<td><p><span data-ttu-id="d0134-115">3</span><span class="sxs-lookup"><span data-stu-id="d0134-115">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0134-116">7-8</span><span class="sxs-lookup"><span data-stu-id="d0134-116">7-8</span></span></p></td>
<td><p><span data-ttu-id="d0134-117">4</span><span class="sxs-lookup"><span data-stu-id="d0134-117">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0134-118">9-10</span><span class="sxs-lookup"><span data-stu-id="d0134-118">9-10</span></span></p></td>
<td><p><span data-ttu-id="d0134-119">5</span><span class="sxs-lookup"><span data-stu-id="d0134-119">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0134-120">11-12</span><span class="sxs-lookup"><span data-stu-id="d0134-120">11-12</span></span></p></td>
<td><p><span data-ttu-id="d0134-121">6</span><span class="sxs-lookup"><span data-stu-id="d0134-121">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="d0134-122">Per Lync Server 2013 ogni volta che si aggiunge o si rimuove un server front-end dal pool, è necessario riavviare i servizi.</span><span class="sxs-lookup"><span data-stu-id="d0134-122">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="d0134-123">La rimozione e l'aggiunta di server devono essere eseguite come operazioni separate.</span><span class="sxs-lookup"><span data-stu-id="d0134-123">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="d0134-124">Se ad esempio si vuole aggiungere due server front-end e rimuovere due server front-end, usare il processo seguente:</span><span class="sxs-lookup"><span data-stu-id="d0134-124">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="d0134-125">Rimuovere i due server front-end.</span><span class="sxs-lookup"><span data-stu-id="d0134-125">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="d0134-126">Pubblicare e riattivare la topologia.</span><span class="sxs-lookup"><span data-stu-id="d0134-126">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="d0134-127">Riavviare i servizi</span><span class="sxs-lookup"><span data-stu-id="d0134-127">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="d0134-128">Aggiungere i due server front-end.</span><span class="sxs-lookup"><span data-stu-id="d0134-128">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="d0134-129">Pubblicare e riattivare la topologia.</span><span class="sxs-lookup"><span data-stu-id="d0134-129">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="d0134-130">Riavviare i servizi.</span><span class="sxs-lookup"><span data-stu-id="d0134-130">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="d0134-131">Dopo avere definito la topologia, usare la procedura seguente per definire un pool Front-end per il sito.</span><span class="sxs-lookup"><span data-stu-id="d0134-131">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="d0134-132">Per informazioni dettagliate sulla definizione della topologia, vedere [definire e configurare una topologia in Generatore di topologie per Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="d0134-132">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="d0134-133">Per definire un pool Front-End</span><span class="sxs-lookup"><span data-stu-id="d0134-133">To define a Front End pool</span></span>

1.  <span data-ttu-id="d0134-134">Nella procedura guidata Definisci nuovo pool, nella pagina **Definisci il nuovo pool di front-end** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d0134-134">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="d0134-135">Nella pagina **Definisci il** nome di dominio completo del pool di front-end immettere un FQDN (Fully Qualified Domain Name) per il pool da creare, fare clic su **pool Enterprise Edition front-end**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d0134-135">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="d0134-136">Nella pagina **Definisci i computer in questo pool** immettere un nome di dominio completo del computer per il primo server front-end nel pool e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d0134-136">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="d0134-137">Ripetere questo passaggio per tutti i computer aggiuntivi (fino a dodici) che si desidera aggiungere al pool e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d0134-137">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="d0134-138">Nella pagina **selezionare le caratteristiche** selezionare le caselle di controllo relative alle caratteristiche desiderate in questo pool di front-end.</span><span class="sxs-lookup"><span data-stu-id="d0134-138">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="d0134-139">Ad esempio, se si stanno distribuendo solo le funzionalità di messaggistica istantanea e presenza, è necessario selezionare la casella di controllo **conferenza** per consentire la messaggistica istantanea in più parti, ma non selezionare le caselle di controllo per i servizi di conferenza telefonica con **accesso esterno**, **VoIP aziendale**o di **ammissione alle chiamate** , perché rappresentano le caratteristiche di conferenza telefonica vocale, video e collaborazione.</span><span class="sxs-lookup"><span data-stu-id="d0134-139">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="d0134-140">**Conferenza**   questa selezione consente di creare una vasta gamma di funzionalità, tra cui:</span><span class="sxs-lookup"><span data-stu-id="d0134-140">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="d0134-141">Messaggistica istantanea con più di due parti in una sessione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="d0134-141">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="d0134-142">Servizi di conferenza, che includono la collaborazione tra documenti, la condivisione delle applicazioni e la condivisione desktop.</span><span class="sxs-lookup"><span data-stu-id="d0134-142">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="d0134-143">A/V Conferencing, che consente agli utenti di avere conferenze audio/video (A/V) in tempo reale senza la necessità di servizi esterni, come il servizio Live Meeting o un bridge audio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="d0134-143">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="d0134-144">**Le conferenze**   telefoniche con accesso esterno (PSTN) consentono agli utenti di partecipare alla parte audio di una conferenza di Lync Server 2013 usando un telefono PSTN (Public Switched Telephone Network) senza richiedere un provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="d0134-144">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="d0134-145">**Enterprise Voice**   Enterprise Voice è la soluzione VoIP (Voice over IP) in Lync Server 2013 che consente agli utenti di effettuare e ricevere chiamate telefoniche.</span><span class="sxs-lookup"><span data-stu-id="d0134-145">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="d0134-146">Questa funzionalità verrà distribuita se si prevede di usare Lync Server 2013 per le chiamate vocali, la segreteria telefonica e altre funzioni che usano un dispositivo hardware o un client software.</span><span class="sxs-lookup"><span data-stu-id="d0134-146">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="d0134-147">**Controllo di ammissione di chiamata (CAC)**   CAC determina, in base alla larghezza di banda della rete disponibile, se consentire la creazione di sessioni di comunicazioni in tempo reale, ad esempio chiamate vocali o videochiamate.</span><span class="sxs-lookup"><span data-stu-id="d0134-147">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="d0134-148">Se è stata distribuita solo la messaggistica istantanea e la presenza, il CAC non è necessario perché nessuna delle due caratteristiche USA CAC.</span><span class="sxs-lookup"><span data-stu-id="d0134-148">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="d0134-149">**L'archiviazione dell'**   archiviazione consente di archiviare il contenuto di messaggistica istantanea, i contenuti di conferenza (riunione) o entrambi inviati tramite Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0134-149">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="d0134-150">**Il monitoraggio**   del server di monitoraggio consente di raccogliere dati numerici che descrivono la qualità multimediale della rete e degli endpoint, le informazioni sull'utilizzo relative alle chiamate VoIP, i messaggi istantanei, le conversazioni a/V, le riunioni, la condivisione delle applicazioni e i trasferimenti di file e le informazioni sulla risoluzione dei problemi per le chiamate non riuscite.</span><span class="sxs-lookup"><span data-stu-id="d0134-150">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d0134-151">Se si vuole abilitare CAC nella distribuzione, è necessario abilitare CAC in un unico pool per ogni sito centrale.</span><span class="sxs-lookup"><span data-stu-id="d0134-151">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site.</span></span> <span data-ttu-id="d0134-152">Il comando CAC è consigliato se si distribuiscono le funzionalità vocali o i servizi di conferenza A/V.</span><span class="sxs-lookup"><span data-stu-id="d0134-152">CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="d0134-153">La tabella seguente mostra le funzionalità disponibili (inizio) e le funzioni offerte agli utenti (a sinistra).</span><span class="sxs-lookup"><span data-stu-id="d0134-153">The following table shows the available features (top) and the functions offered to users (left).</span></span> <span data-ttu-id="d0134-154">Le selezioni nella tabella sono quelle da selezionare per abilitare tali funzionalità per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d0134-154">The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
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
    <th><span data-ttu-id="d0134-155">Servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="d0134-155">Conferencing</span></span></th>
    <th><span data-ttu-id="d0134-156">Servizi di conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="d0134-156">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="d0134-157">VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="d0134-157">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="d0134-158">Controllo ammissione chiamata</span><span class="sxs-lookup"><span data-stu-id="d0134-158">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d0134-159">Messaggistica istantanea e presenza</span><span class="sxs-lookup"><span data-stu-id="d0134-159">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="d0134-160">X</span><span class="sxs-lookup"><span data-stu-id="d0134-160">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d0134-161">Servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="d0134-161">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="d0134-162">X</span><span class="sxs-lookup"><span data-stu-id="d0134-162">X</span></span></p></td>
    <td><p><span data-ttu-id="d0134-163">X</span><span class="sxs-lookup"><span data-stu-id="d0134-163">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d0134-164">Servizi di conferenza A/V</span><span class="sxs-lookup"><span data-stu-id="d0134-164">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="d0134-165">X</span><span class="sxs-lookup"><span data-stu-id="d0134-165">X</span></span></p></td>
    <td><p><span data-ttu-id="d0134-166">X</span><span class="sxs-lookup"><span data-stu-id="d0134-166">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="d0134-167">X</span><span class="sxs-lookup"><span data-stu-id="d0134-167">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d0134-168">VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="d0134-168">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="d0134-169">X</span><span class="sxs-lookup"><span data-stu-id="d0134-169">X</span></span></p></td>
    <td><p><span data-ttu-id="d0134-170">X</span><span class="sxs-lookup"><span data-stu-id="d0134-170">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="d0134-171">Nella pagina **Selezione ruoli server collocato** è possibile collocare il Mediation Server nel server front-end o distribuirlo come server autonomo.</span><span class="sxs-lookup"><span data-stu-id="d0134-171">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="d0134-172">È possibile collocare il Mediation Server nel pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="d0134-172">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="d0134-173">Se si intende collocare il Mediation Server nel pool Enterprise Edition front-end, verificare che la casella di controllo sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="d0134-173">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="d0134-174">Il ruolo del server verrà distribuito nei server del pool.</span><span class="sxs-lookup"><span data-stu-id="d0134-174">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="d0134-175">Se si intende distribuire il server di mediazione come server autonomo, deselezionare la casella di controllo appropriata.</span><span class="sxs-lookup"><span data-stu-id="d0134-175">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="d0134-176">Si distribuirà Mediation Server in un passaggio di distribuzione distinto dopo la distribuzione completa del server front-end.</span><span class="sxs-lookup"><span data-stu-id="d0134-176">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d0134-177">È consigliabile collocare il Mediation Server, se possibile.</span><span class="sxs-lookup"><span data-stu-id="d0134-177">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="d0134-178">Per informazioni dettagliate sul supporto per i server di mediazione collocati o autonomi, vedere <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">componenti e topologie per Mediation Server in Lync server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d0134-178">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="d0134-179">I **ruoli del server associato con questa pagina del pool Front-End** consentono di definire e associare i ruoli del server al pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="d0134-179">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="d0134-180">Il ruolo seguente è disponibile:</span><span class="sxs-lookup"><span data-stu-id="d0134-180">The following role is available:</span></span>
    
    <span data-ttu-id="d0134-181">**Abilitare un pool**   Edge definisce e associa un singolo Edge Server o un pool di Edge Server.</span><span class="sxs-lookup"><span data-stu-id="d0134-181">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="d0134-182">Un Edge Server facilita la comunicazione e la collaborazione tra gli utenti all'interno dell'organizzazione e le persone esterne all'organizzazione, inclusi gli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="d0134-182">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="d0134-183">Esistono due scenari possibili che è possibile usare per distribuire e associare i ruoli del server:</span><span class="sxs-lookup"><span data-stu-id="d0134-183">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="d0134-184">Per scenario uno, si sta definendo una nuova topologia per una nuova installazione.</span><span class="sxs-lookup"><span data-stu-id="d0134-184">For scenario one, you are defining a new topology for a new installation.</span></span> <span data-ttu-id="d0134-185">Puoi avvicinarti all'installazione in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0134-185">You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="d0134-186">Uscire dalla casella di controllo e procedere con la definizione della topologia.</span><span class="sxs-lookup"><span data-stu-id="d0134-186">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="d0134-187">Dopo aver pubblicato, configurato e testato i ruoli del server front-end e back-end, è possibile eseguire di nuovo il generatore di topologia per aggiungere i server dei ruoli alla topologia.</span><span class="sxs-lookup"><span data-stu-id="d0134-187">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="d0134-188">Questa strategia consentirà di testare il pool Front end e il server che eseguirà SQL Server senza ulteriori complicazioni da ruoli aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="d0134-188">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="d0134-189">Dopo aver completato il test iniziale, è possibile eseguire di nuovo il generatore di topologia per selezionare i ruoli che è necessario distribuire.</span><span class="sxs-lookup"><span data-stu-id="d0134-189">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="d0134-190">Selezionare i ruoli che è necessario installare e quindi configurare l'hardware in grado di ospitare i ruoli selezionati.</span><span class="sxs-lookup"><span data-stu-id="d0134-190">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="d0134-191">Per lo scenario due è disponibile una distribuzione esistente e l'infrastruttura è pronta per i nuovi ruoli oppure è necessario associare i ruoli esistenti a un nuovo server front-end:</span><span class="sxs-lookup"><span data-stu-id="d0134-191">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="d0134-192">In questo caso, selezionare i ruoli che si desidera distribuire o associare al nuovo server front-end.</span><span class="sxs-lookup"><span data-stu-id="d0134-192">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="d0134-193">In entrambi i casi, procedere con la definizione dei ruoli, configurare l'hardware necessario e procedere con l'installazione.</span><span class="sxs-lookup"><span data-stu-id="d0134-193">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="d0134-194">Nella pagina **Definisci l'archivio SQL** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0134-194">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="d0134-195">Per usare un archivio di SQL Server esistente già definito nella topologia, selezionare un'istanza da **SQL Store**.</span><span class="sxs-lookup"><span data-stu-id="d0134-195">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="d0134-196">Per definire una nuova istanza di SQL Server per archiviare le informazioni sul pool, fare clic su **nuovo** e quindi specificare il **nome di dominio completo di SQL Server**nella finestra di dialogo **Definisci nuovo archivio SQL** .</span><span class="sxs-lookup"><span data-stu-id="d0134-196">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="d0134-197">Per specificare il nome di un'istanza di SQL Server, selezionare **istanza denominata**e quindi specificare il nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="d0134-197">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="d0134-198">Per usare l'istanza predefinita, fare clic su **istanza predefinita**.</span><span class="sxs-lookup"><span data-stu-id="d0134-198">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="d0134-199">Per usare il mirroring SQL, selezionare **Abilita il mirroring SQL** e selezionare un'istanza esistente o creare una nuova istanza.</span><span class="sxs-lookup"><span data-stu-id="d0134-199">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="d0134-200">Nella pagina **Definisci la condivisione file** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0134-200">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="d0134-201">Per usare una condivisione file già definita nella topologia, selezionare **Usa una condivisione file definita in precedenza**.</span><span class="sxs-lookup"><span data-stu-id="d0134-201">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="d0134-202">Per definire una nuova condivisione file, selezionare **Definisci una nuova condivisione file**, nella casella **FQDN file server** immettere il nome di dominio completo del file server esistente in cui si trova la condivisione file e quindi immettere un nome per la condivisione file nella casella **condivisione file** .</span><span class="sxs-lookup"><span data-stu-id="d0134-202">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="d0134-203">La condivisione file per Lync Server 2013 non può essere posizionata nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="d0134-203">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="d0134-204">Si noti che in questo esempio la condivisione file si trova nel server back-end basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d0134-204">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="d0134-205">Potrebbe non essere una posizione ottimale per i requisiti dell'organizzazione e un file server potrebbe essere una scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="d0134-205">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="d0134-206">È possibile definire la condivisione file senza che la condivisione file sia stata creata.</span><span class="sxs-lookup"><span data-stu-id="d0134-206">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="d0134-207">Sarà necessario creare la condivisione file nella posizione definita prima di pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="d0134-207">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="d0134-208">Nella pagina **specificare l'URL dei servizi Web** eseguire una o entrambe le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0134-208">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="d0134-209">L'URL di base è l'identità dei servizi Web per l'URL, meno il https://.</span><span class="sxs-lookup"><span data-stu-id="d0134-209">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="d0134-210">Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net, l'URL di base è pool01.contoso.NET.</span><span class="sxs-lookup"><span data-stu-id="d0134-210">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="d0134-211">Se si dispone di più di un pool Front-end o di un server front-end, l'FQDN dei servizi Web esterni deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="d0134-211">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="d0134-212">Se ad esempio si definisce il nome di dominio completo dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile usare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front-end o front end server.</span><span class="sxs-lookup"><span data-stu-id="d0134-212">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="d0134-213">Se si sta configurando il bilanciamento del carico DNS, selezionare la casella di controllo **Sostituisci il nome completo del pool di servizi Web interni** , immettere l'URL di base interno (che deve essere diverso dall'FQDN del\<pool e potrebbe\>essere, ad esempio, l'URL di base interno) nell' **URL di base interno**.</span><span class="sxs-lookup"><span data-stu-id="d0134-213">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="d0134-214">Se si decide di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni nome di dominio completo deve essere univoco da qualsiasi altro pool di front-end, direttore o pool di Director.</span><span class="sxs-lookup"><span data-stu-id="d0134-214">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="d0134-215">Quando si definiscono URL o nomi di dominio completi, <STRONG>usare solo caratteri standard</STRONG> (tra cui a-z, a-z, 0-9 e segni meno).</span><span class="sxs-lookup"><span data-stu-id="d0134-215"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="d0134-216">Non usare caratteri Unicode o carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="d0134-216">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="d0134-217">I caratteri non standard in un URL o FQDN spesso non sono supportati dal DNS esterno e dalle CA pubbliche, ovvero quando l'URL o il nome di dominio completo deve essere assegnato al nome dell'oggetto o all'oggetto alternativo nel certificato.</span><span class="sxs-lookup"><span data-stu-id="d0134-217">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="d0134-218">Facoltativamente, immettere l'URL della base esterna nell' **URL di base esterno**.</span><span class="sxs-lookup"><span data-stu-id="d0134-218">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="d0134-219">Si immetterebbe l'URL della base esterna per differenziarlo dalla denominazione interna del dominio.</span><span class="sxs-lookup"><span data-stu-id="d0134-219">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="d0134-220">Ad esempio, il dominio interno è contoso.net, ma il nome di dominio esterno è contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d0134-220">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="d0134-221">Definiresti l'URL usando il nome di dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d0134-221">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="d0134-222">Questo è importante anche nel caso di un proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d0134-222">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="d0134-223">Il nome di dominio dell'URL di base esterno corrisponde al nome di dominio dell'FQDN del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d0134-223">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="d0134-224">La messaggistica istantanea e la presenza richiedono l'accesso HTTP al pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="d0134-224">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d0134-225">Per usare il bilanciamento del carico DNS, è necessario creare i record DNS appropriati.</span><span class="sxs-lookup"><span data-stu-id="d0134-225">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="d0134-226">Per informazioni dettagliate, vedere <A href="lync-server-2013-configure-dns-for-load-balancing.md">configurare il DNS per il bilanciamento del carico in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d0134-226">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="d0134-227">Se è stata selezionata l'opzione servizi di **conferenza** nella pagina **Seleziona funzionalità** , nella pagina **selezionare un server di Office Web Apps** selezionare **Associa pool a un server di Office Web Apps** e quindi fare clic su **nuovo** (o selezionare un server di Office Web Apps esistente nell'elenco a discesa).</span><span class="sxs-lookup"><span data-stu-id="d0134-227">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="d0134-228">Nella finestra di dialogo **Definisci nuovo server Office Web Apps** Digitare il nome di dominio completo (FQDN) del computer Office Web Apps Server nella casella **FQDN server di Office Web Apps** . Quando si esegue questa operazione, l'URL di individuazione del server di Office Web Apps deve essere automaticamente immesso nella casella **URL individuazione server di Office Web Apps** .</span><span class="sxs-lookup"><span data-stu-id="d0134-228">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="d0134-229">Se il server Office Web Apps è installato in locale e nella stessa area di rete di Lync Server 2013, l'opzione **Office Web Apps Server è distribuita in una rete esterna, ovvero perimetro/Internet,** non deve essere selezionata.</span><span class="sxs-lookup"><span data-stu-id="d0134-229">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="d0134-230">Se il server Office Web Apps è distribuito all'esterno del firewall interno, selezionare l'opzione **Office Web Apps Server è distribuito in una rete esterna (ovvero perimetro/Internet)**.</span><span class="sxs-lookup"><span data-stu-id="d0134-230">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d0134-231">Per informazioni dettagliate, vedere <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">configurazione dell'integrazione con Office Web Apps Server e Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d0134-231">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="d0134-232">Nella pagina **Definisci archiviazione SQL Store** selezionare un'istanza o un server SQL esistente oppure definire una nuova istanza per archiviare i dati associati ai dati di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d0134-232">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="d0134-233">Nella pagina **Definisci il monitoraggio dell'archivio SQL** selezionare un'istanza o un server SQL esistente oppure definire una nuova istanza per archiviare i dati associati al monitoraggio dei dati.</span><span class="sxs-lookup"><span data-stu-id="d0134-233">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="d0134-234">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d0134-234">Click **Next**.</span></span> <span data-ttu-id="d0134-235">Se sono stati definiti altri server di ruoli nei **ruoli del server associato con questa pagina del pool Front-End** , le pagine della configurazione guidata ruolo separato verranno aperte per consentire la configurazione dei ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="d0134-235">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="d0134-236">Per informazioni dettagliate, vedere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d0134-236">For details, see the following:</span></span>
    
    [<span data-ttu-id="d0134-237">Distribuzione dell'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0134-237">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="d0134-238">Se non è stato selezionato ruoli server aggiuntivi per la configurazione e la distribuzione oppure quando è stata completata l'installazione di altri server dei ruoli, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="d0134-238">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

