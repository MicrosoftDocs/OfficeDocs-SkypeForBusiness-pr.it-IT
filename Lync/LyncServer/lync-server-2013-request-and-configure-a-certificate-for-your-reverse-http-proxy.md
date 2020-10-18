---
title: Richiedere e configurare un certificato per il proxy inverso HTTP
description: Richiedere e configurare un certificato per il proxy inverso HTTP.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdeaa080e3ccb6a9895e18a6ac02084e99a1e33e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579042"
---
# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a><span data-ttu-id="77441-103">Richiedere e configurare un certificato per il proxy inverso HTTP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77441-103">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77441-104">_**Ultimo argomento modificato:** 2014-02-14_</span><span class="sxs-lookup"><span data-stu-id="77441-104">_**Topic Last Modified:** 2014-02-14_</span></span>

<span data-ttu-id="77441-105">È necessario installare il certificato autorità di certificazione (CA) radice sul server che esegue Microsoft Forefront Threat Management Gateway 2010 o IIS ARR per l'infrastruttura CA che ha emesso i certificati server nei server interni che eseguono Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77441-105">You need to install the root certification authority (CA) certificate on the server running Microsoft Forefront Threat Management Gateway 2010 or IIS ARR for the CA infrastructure that issued the server certificates to the internal servers running Microsoft Lync Server 2013.</span></span>

<span data-ttu-id="77441-p101">È inoltre necessario installare un certificato server Web pubblico nel server proxy inverso. I nomi alternativi soggetto del certificato dovrebbero contenere i nomi di dominio completi (FQDN) esterni pubblicati di ogni pool che ospita gli utenti abilitati per l'accesso remoto e gli FQDN esterni di tutti i Director o pool di server Director che verranno utilizzati in tale infrastruttura Edge. Il nome alternativo soggetto deve contenere anche l'URL semplice della riunione, l'URL semplice di accesso esterno e, se si distribuiscono applicazioni mobili e si prevede di utilizzare l'individuazione automatica, l'URL del servizio di individuazione automatica esterno come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="77441-p101">You also must install a public web server certificate on your reverse proxy server. This certificate’s subject alternative names should contain the published external fully qualified domain names (FQDNs) of each pool that is home to users enabled for remote access, and the external FQDNs of all Directors or Director pools that will be used within that Edge infrastructure. The subject alternative name must also contain the meeting simple URL, the dial-in simple URL, and, if you are deploying mobile applications and plan to use automatic discovery, the external Autodiscover Service URL as shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="77441-109">Valore</span><span class="sxs-lookup"><span data-stu-id="77441-109">Value</span></span></th>
<th><span data-ttu-id="77441-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="77441-110">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77441-111">Nome soggetto</span><span class="sxs-lookup"><span data-stu-id="77441-111">Subject name</span></span></p></td>
<td><p><span data-ttu-id="77441-112">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="77441-112">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="77441-113">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="77441-113">webext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77441-114">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="77441-114">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="77441-115">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="77441-115">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="77441-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="77441-116">webext.contoso.com</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="77441-117">Il nome soggetto deve essere presente anche nel nome alternativo soggetto.</span><span class="sxs-lookup"><span data-stu-id="77441-117">The subject name must also be present in the subject alternative name.</span></span>

</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77441-118">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="77441-118">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="77441-119">Servizi Web Director opzionali (se il Director è distribuito)</span><span class="sxs-lookup"><span data-stu-id="77441-119">Optional Director Web Services (if Director is deployed)</span></span></p></td>
<td><p><span data-ttu-id="77441-120">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="77441-120">webdirext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77441-121">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="77441-121">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="77441-122">URL semplice riunione</span><span class="sxs-lookup"><span data-stu-id="77441-122">Meeting simple URL</span></span></p>



> [!NOTE]
> <span data-ttu-id="77441-p102">Tutti gli URL semplici di riunione devono essere inclusi nel nome alternativo soggetto. Ogni dominio SIP deve avere almeno un URL semplice di riunione attiva.</span><span class="sxs-lookup"><span data-stu-id="77441-p102">All meeting simple URLs must be in the subject alternative name. Each SIP domain must have at least one active meeting simple URL.</span></span>

</td>
<td><p><span data-ttu-id="77441-125">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="77441-125">meet.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77441-126">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="77441-126">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="77441-127">URL semplice accesso esterno</span><span class="sxs-lookup"><span data-stu-id="77441-127">Dial-in simple URL</span></span></p></td>
<td><p><span data-ttu-id="77441-128">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="77441-128">dialin.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77441-129">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="77441-129">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="77441-130">server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="77441-130">Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="77441-131">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="77441-131">officewebapps01.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77441-132">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="77441-132">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="77441-133">URL servizio di individuazione automatica esterno</span><span class="sxs-lookup"><span data-stu-id="77441-133">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="77441-134">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="77441-134">lyncdiscover.contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="77441-135">Se si utilizza anche Microsoft Exchange Server, sarà inoltre necessario configurare le regole del proxy inverso per gli URL di individuazione automatica e servizi Web di Exchange.</span><span class="sxs-lookup"><span data-stu-id="77441-135">If you are also using Microsoft Exchange Server you will also need to configure reverse proxy rules for the Exchange autodiscover and web services URLs.</span></span>

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="77441-136">Se la distribuzione interna include più server Standard Edition o pool Front End, è necessario configurare le regole di pubblicazione Web per ogni FQDN di Web FARM esterna e sarà necessario un certificato e un listener Web per ognuno oppure ottenere un certificato con nome alternativo soggetto che contiene i nomi utilizzati da tutti i pool, assegnarlo a un listener Web e condividerlo tra più regole di pubblicazione Web.</span><span class="sxs-lookup"><span data-stu-id="77441-136">If your internal deployment consists of more than one Standard Edition server or Front End pool, you must configure web publishing rules for each external web farm FQDN and you will either need a certificate and web listener for each, or you must obtain a certificate whose subject alternative name contains the names used by all of the pools, assign it to a web listener, and share it among multiple web publishing rules.</span></span>



</div>

<div>

## <a name="create-a-certificate-request"></a><span data-ttu-id="77441-137">Creare una richiesta di certificato</span><span class="sxs-lookup"><span data-stu-id="77441-137">Create a Certificate Request</span></span>

<span data-ttu-id="77441-138">È possibile creare una richiesta di certificato per il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="77441-138">You create a certificate request on the reverse proxy.</span></span> <span data-ttu-id="77441-139">È possibile creare una richiesta su un altro computer, ma è necessario esportare il certificato firmato con la chiave privata e importarlo nel proxy inverso dopo averlo ricevuto dall'autorità di certificazione pubblica.</span><span class="sxs-lookup"><span data-stu-id="77441-139">You create a request on another computer, but you must export the signed certificate with the private key and import it onto the reverse proxy once you have received it from the public certification authority.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="77441-140">Una richiesta di certificato o una richiesta di firma del certificato (CSR) è una richiesta a un'autorità di certificazione (CA) pubblica attendibile per convalidare e firmare la chiave pubblica del computer richiedente.</span><span class="sxs-lookup"><span data-stu-id="77441-140">A certificate request or a certificate signing request (CSR) is a request to a trusted public certification authority (CA) to validate and sign the requesting computer’s public key.</span></span> <span data-ttu-id="77441-141">Quando viene generato un certificato, vengono create una chiave pubblica e una chiave privata.</span><span class="sxs-lookup"><span data-stu-id="77441-141">When a certificate is generated, a public key and a private key are created.</span></span> <span data-ttu-id="77441-142">Solo la chiave pubblica è condivisa e firmata.</span><span class="sxs-lookup"><span data-stu-id="77441-142">Only the public key is shared and signed.</span></span> <span data-ttu-id="77441-143">Come suggerisce il nome, la chiave pubblica viene messa a disposizione di qualsiasi richiesta pubblica.</span><span class="sxs-lookup"><span data-stu-id="77441-143">As the name implies, the public key is made available to any public request.</span></span> <span data-ttu-id="77441-144">La chiave pubblica è destinata all'utilizzo da parte di client, server e altri richiedenti che devono scambiare informazioni in modo sicuro e convalidare l'identità di un computer.</span><span class="sxs-lookup"><span data-stu-id="77441-144">The public key is for use by clients, servers and other requesters that need to exchange information securely and validate a computer’s identity.</span></span> <span data-ttu-id="77441-145">La chiave privata viene mantenuta protetta e viene utilizzata solo dal computer che ha creato la coppia di chiavi per decrittografare i messaggi crittografati con la chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="77441-145">The private key is kept secured and is used only by the computer that created the key pair to decrypt messages encrypted with its public key.</span></span> <span data-ttu-id="77441-146">La chiave privata può essere utilizzata per altri scopi.</span><span class="sxs-lookup"><span data-stu-id="77441-146">The private key can be used for other purposes.</span></span> <span data-ttu-id="77441-147">Per motivi di proxy inverso, la crittografia dei dati è l'utilizzo principale.</span><span class="sxs-lookup"><span data-stu-id="77441-147">For reverse proxy purposes, data encipherment is the primary use.</span></span> <span data-ttu-id="77441-148">In secondo luogo, l'autenticazione del certificato a livello di chiave del certificato è un altro utilizzo ed è limitata solo alla convalida che un richiedente ha la chiave pubblica del computer o che il computer in cui si dispone di una chiave pubblica è effettivamente il computer che afferma di essere.</span><span class="sxs-lookup"><span data-stu-id="77441-148">Secondarily, the certificate authentication at the certificate key level is another use, and is limited only to validation that a requester has the computer’s public key, or that the computer that you have a public key for is actually the computer that it claims to be.</span></span>



</div>

<div>


> [!TIP]
> <span data-ttu-id="77441-149">Se si pianificano contemporaneamente i certificati del server perimetrale e i certificati per il proxy inverso, è necessario tenere presente che esiste una notevole somiglianza tra i due requisiti del certificato.</span><span class="sxs-lookup"><span data-stu-id="77441-149">If you plan your Edge Server certificates and your reverse proxy certificates at the same time, you should notice that there is a great deal of similarity between the two certificate requirements.</span></span> <span data-ttu-id="77441-150">Quando si configura e si richiede il certificato del server perimetrale, combinare il server perimetrale e i nomi alternativi del soggetto del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="77441-150">When you configure and request your Edge Server certificate, combine the Edge Server and the reverse proxy subject alternative names.</span></span> <span data-ttu-id="77441-151">È possibile utilizzare lo stesso certificato per il proxy inverso se si esporta il certificato e la chiave privata e si copia il file esportato nel proxy inverso e quindi si importa la coppia di certificati/chiavi e la si assegna come necessario nelle procedure imminenti.</span><span class="sxs-lookup"><span data-stu-id="77441-151">You can use the same certificate for your reverse proxy if you export the certificate and the private key and copy the exported file to the reverse proxy and then import the certificate/key pair and assign it as needed in the upcoming procedures.</span></span> <span data-ttu-id="77441-152">Fare riferimento ai requisiti del certificato per il piano server perimetrale &nbsp; <A href="lync-server-2013-plan-for-edge-server-certificates.md">per i certificati server perimetrali in lync Server 2013</A> e il riepilogo dei certificati del proxy inverso <A href="lync-server-2013-certificate-summary-reverse-proxy.md">-proxy inverso in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="77441-152">Refer to the certificate requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A> and the reverse proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate summary - Reverse proxy in Lync Server 2013</A>.</span></span> <span data-ttu-id="77441-153">Assicurarsi di creare il certificato con una chiave privata esportabile.</span><span class="sxs-lookup"><span data-stu-id="77441-153">Make sure that you create the certificate with an exportable private key.</span></span> <span data-ttu-id="77441-154">Per creare il certificato e la richiesta di certificato con una chiave privata esportabile, è necessario eseguire una procedura normale e la configurazione guidata certificati nella distribuzione guidata di Lync Server per il server perimetrale consentirà di impostare il flag <STRONG>Rendi la chiave privata esportabile</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="77441-154">Creating the certificate and certificate request with an exportable private key is required for pooled Edge Servers, so this is a normal practice and the Certificate Wizard in the Lync Server Deployment Wizard for the Edge Server will allow you to set the <STRONG>Make private key exportable</STRONG> flag.</span></span> <span data-ttu-id="77441-155">Dopo aver ricevuto la richiesta di certificato dall'autorità di certificazione pubblica, verranno esportati il certificato e la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="77441-155">Once you receive the certificate request back from the public certification authority, you will export the certificate and the private key.</span></span> <span data-ttu-id="77441-156">Vedere la sezione "per esportare il certificato con la chiave privata per i server perimetrali in un pool" nell'argomento <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">configurare i certificati per l'interfaccia perimetrale esterna per Lync Server 2013</A> per informazioni dettagliate su come creare ed esportare il certificato con una chiave privata.</span><span class="sxs-lookup"><span data-stu-id="77441-156">See the section “To export the certificate with the private key for Edge Servers in a pool” in the topic <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Set up certificates for the external edge interface for Lync Server 2013</A> for details on how to create and export your certificate with a private key.</span></span> <span data-ttu-id="77441-157">L'estensione del certificato deve essere di tipo <STRONG>PFX</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="77441-157">The extension of the certificate should be of type <STRONG>.pfx</STRONG>.</span></span>



</div>

<span data-ttu-id="77441-158">Per generare una richiesta di firma del certificato nel computer in cui verrà assegnato il certificato e la chiave privata, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="77441-158">To generate a certificate signing request on the computer where the certificate and private key will be assigned, you do the following:</span></span>

<span data-ttu-id="77441-159">**Creazione di una richiesta di firma del certificato**</span><span class="sxs-lookup"><span data-stu-id="77441-159">**Creating a certificate signing request**</span></span>

1.  <span data-ttu-id="77441-160">Aprire Microsoft Management Console (MMC) e aggiungere lo snap-in certificati e selezionare **computer**, quindi espandere **personale**.</span><span class="sxs-lookup"><span data-stu-id="77441-160">Open the Microsoft Management Console (MMC) and add the Certificates snap-in and select **Computers**, then expand **Personal**.</span></span> <span data-ttu-id="77441-161">Per informazioni dettagliate su come creare una console di certificati in Microsoft Management Console (MMC), vedere [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616) .</span><span class="sxs-lookup"><span data-stu-id="77441-161">For details on how to create a certificates console in the Microsoft Management Console (MMC), see [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616).</span></span>

2.  <span data-ttu-id="77441-162">Fare clic con il pulsante destro del mouse su **certificati**, scegliere **tutte le attività**, fare clic su **operazioni avanzate**, su **Crea richiesta personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="77441-162">Right-click **Certificates**, click **All Tasks**, click **Advanced Operations**, click **Create Custom Request**.</span></span>

3.  <span data-ttu-id="77441-163">Nella pagina **registrazione certificati** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="77441-163">On the **Certificate Enrollment** page, click **Next**.</span></span>

4.  <span data-ttu-id="77441-164">Nella pagina **selezionare il criterio di registrazione dei certificati** in **richiesta personalizzata**, selezionare **continua senza criteri di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="77441-164">On the **Select Certificate Enrollment Policy** page under **Custom Request**, select **Proceed without enrollment policy**.</span></span> <span data-ttu-id="77441-165">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="77441-165">Click **Next**.</span></span>

5.  <span data-ttu-id="77441-166">Nella pagina **richiesta personalizzata** , per la **Template** **chiave legacy template Select (No Template)**.</span><span class="sxs-lookup"><span data-stu-id="77441-166">On the **Custom Request** page, for **Template** select **(No template) Legacy key**.</span></span> <span data-ttu-id="77441-167">Se non diversamente specificato dal provider di certificati, lasciare invariate le **estensioni predefinite** deselezionate e la selezione del **formato di richiesta** su **PKCS \# 10**.</span><span class="sxs-lookup"><span data-stu-id="77441-167">Unless otherwise directed by your certificate provider, leave **Suppress default extensions** unchecked and the **Request format** selection on **PKCS \#10**.</span></span> <span data-ttu-id="77441-168">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="77441-168">Click **Next**.</span></span>

6.  <span data-ttu-id="77441-169">Nella pagina **informazioni sui certificati** fare clic su **Dettagli**e quindi su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="77441-169">On the **Certificate Information** page, click **Details**, then click **Properties**.</span></span>

7.  <span data-ttu-id="77441-170">Nella pagina delle **proprietà del certificato** nella scheda **generale** del campo **nome descrittivo** digitare un nome per il certificato.</span><span class="sxs-lookup"><span data-stu-id="77441-170">On the **Certificate Properties** page on the **General** tab in the **Friendly Name** field, type a name for this certificate.</span></span> <span data-ttu-id="77441-171">Facoltativamente, digitare una descrizione nel campo **Descrizione** .</span><span class="sxs-lookup"><span data-stu-id="77441-171">Optionally, type a description in the **Description** field.</span></span> <span data-ttu-id="77441-172">Il nome descrittivo e la descrizione vengono in genere utilizzati dall'amministratore per identificare lo scopo del certificato, ad esempio il **listener del proxy inverso per Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="77441-172">The Friendly Name and description are typically used by the Administrator to identify what the certificate purpose is, such as **Reverse Proxy Listener for Lync Server**.</span></span>

8.  <span data-ttu-id="77441-173">Selezionare la scheda **oggetto** . In **nome oggetto** per il **tipo**Selezionare **nome comune** per il tipo di nome soggetto.</span><span class="sxs-lookup"><span data-stu-id="77441-173">Select the **Subject** tab. Under **Subject name** for the **Type**, select **Common name** for the Subject name type.</span></span> <span data-ttu-id="77441-174">Per il **valore**, digitare il nome del soggetto che verrà utilizzato per il proxy inverso, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="77441-174">For the **Value**, type the subject name that you will use for the reverse proxy, and then click **Add**.</span></span> <span data-ttu-id="77441-175">Nell'esempio fornito nella tabella di questo argomento, il nome del soggetto è webext.contoso.com e verrebbe digitato nel campo valore per il nome del soggetto.</span><span class="sxs-lookup"><span data-stu-id="77441-175">In the example provided in the table in this topic, the subject name is webext.contoso.com and would be typed into the Value field for the Subject name.</span></span>

9.  <span data-ttu-id="77441-176">Nella scheda **oggetto** in **nome alternativo**Selezionare **DNS** dal menu a discesa per **tipo**.</span><span class="sxs-lookup"><span data-stu-id="77441-176">On the **Subject** tab under **Alternative name**, select **DNS** from the drop down for **Type**.</span></span> <span data-ttu-id="77441-177">Per ogni nome alternativo del soggetto definito necessario per il certificato, digitare il nome di dominio completo e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="77441-177">For each defined subject alternative name that you require on the certificate, type the fully qualified domain name, then click **Add**.</span></span> <span data-ttu-id="77441-178">Ad esempio, nella tabella sono presenti tre nomi alternativi del soggetto, meet.contoso.com, dialin.contoso.com e lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="77441-178">For example, in the table there are three subject alternative names, meet.contoso.com, dialin.contoso.com, and lyncdiscover.contoso.com.</span></span> <span data-ttu-id="77441-179">Nel campo **valore** Digitare meet.contoso.com, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="77441-179">In the **Value** field, type meet.contoso.com, then click **Add**.</span></span> <span data-ttu-id="77441-180">Ripetere l'argomento per ogni nome alternativo del soggetto che è necessario definire.</span><span class="sxs-lookup"><span data-stu-id="77441-180">Repeat for each subject alternative names that you need to define.</span></span>

10. <span data-ttu-id="77441-181">Nella pagina delle **proprietà del certificato** fare clic sulla scheda **estensioni** . In questa pagina vengono definiti i fini della chiave di crittografia **nell'utilizzo delle chiavi e l'** utilizzo delle chiavi estese nell'utilizzo delle **chiavi estese (criteri applicazione)**.</span><span class="sxs-lookup"><span data-stu-id="77441-181">On the **Certificate Properties** page, click the **Extensions** tab. On this page, you will define the cryptographic key purposes in **Key usage** and the extended key usage in **Extended Key Usage (application policies)**.</span></span>

11. <span data-ttu-id="77441-182">Fare clic sulla freccia **utilizzo chiave** per visualizzare le **opzioni disponibili**.</span><span class="sxs-lookup"><span data-stu-id="77441-182">Click the **Key usage** arrow to show the **Available options**.</span></span> <span data-ttu-id="77441-183">In opzioni disponibili fare clic su **firma digitale**e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="77441-183">Under Available options, click **Digital signature**, then click **Add**.</span></span> <span data-ttu-id="77441-184">Fare clic su **crittografia chiave**, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="77441-184">Click **Key encipherment**, then click **Add**.</span></span> <span data-ttu-id="77441-185">Se la casella di controllo per **rendere questi utilizzi fondamentali** è deselezionata, selezionare la casella di spunta.</span><span class="sxs-lookup"><span data-stu-id="77441-185">If the checkbox for **Make these key usages critical** is unchecked, select the checkbox.</span></span>

12. <span data-ttu-id="77441-186">Fare clic sulla freccia **utilizzo chiave estesa (criteri applicazione)** per visualizzare le **opzioni disponibili**.</span><span class="sxs-lookup"><span data-stu-id="77441-186">Click the **Extended Key Usage (application policies)** arrow to show the **Available options**.</span></span> <span data-ttu-id="77441-187">In opzioni disponibili fare clic su **autenticazione server**e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="77441-187">Under Available options, click **Server Authentication**, then click **Add**.</span></span> <span data-ttu-id="77441-188">Fare clic su **autenticazione client**e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="77441-188">Click **Client Authentication**, then click **Add**.</span></span> <span data-ttu-id="77441-189">Se viene selezionata la casella di controllo **Rendi la chiave estesa utilizzazioni critiche** , deselezionare la casella di spunta.</span><span class="sxs-lookup"><span data-stu-id="77441-189">If the check box for **Make the Extended Key Usages critical** is checked, unselect the checkbox.</span></span> <span data-ttu-id="77441-190">In caso contrario alla casella di controllo utilizzo chiave (che deve essere controllata), è necessario verificare che la casella di controllo utilizzo chiavi estese non sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="77441-190">Contrary to the Key usage checkbox (which must be checked) you must be sure that the Extended Key Usage checkbox is not checked.</span></span>

13. <span data-ttu-id="77441-191">Nella pagina delle **proprietà del certificato** , fare clic sulla scheda **chiave privata** . Fare clic sulla freccia **Opzioni chiave** .</span><span class="sxs-lookup"><span data-stu-id="77441-191">On the **Certificate Properties** page, click the **Private Key** tab. Click the **Key options** arrow.</span></span> <span data-ttu-id="77441-192">Per le **dimensioni della chiave**, selezionare **2048** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="77441-192">For **Key size**, select **2048** from the drop down.</span></span> <span data-ttu-id="77441-193">Se si sta generando questa coppia di chiavi e la RSI su un computer diverso da quello inverso per cui è destinato il certificato, selezionare **Rendi esportazione chiave privata**.</span><span class="sxs-lookup"><span data-stu-id="77441-193">If you are generating this key pair and CSR on a computer other than the reverse proxy that this certificate is intended for, select **Make private key exportable**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" /><span data-ttu-id="77441-195">Nota sulla sicurezza:</span><span class="sxs-lookup"><span data-stu-id="77441-195">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="77441-196">La selezione di <strong>una chiave privata esportabile</strong> viene generalmente consigliata quando si dispone di più di un proxy inverso in una farm, in quanto il certificato e la chiave privata vengono copiati in ogni computer della farm.</span><span class="sxs-lookup"><span data-stu-id="77441-196">Selecting <strong>Make a private key exportable</strong> is generally advised when you have more than one reverse proxy in a farm because you will copy the certificate and the private key to each machine in the farm.</span></span> <span data-ttu-id="77441-197">Se si consente la possibilità di utilizzare una chiave privata esportabile, è necessario prestare particolare attenzione al certificato e al computer in cui è stato generato.</span><span class="sxs-lookup"><span data-stu-id="77441-197">If you do allow for an exportable private key, you must take extra care with the certificate and the computer that it is generated on.</span></span> <span data-ttu-id="77441-198">La chiave privata, se compromessa, renderà il certificato inutilizzabile e potrebbe esporre il computer o i computer all'accesso esterno e ad altre vulnerabilità della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="77441-198">The private key, if compromised, will render the certificate useless as well as potentially expose the computer or computers to external access and other security vulnerabilities.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. <span data-ttu-id="77441-199">Nella scheda **chiave privata** fare clic sulla freccia del **tipo di chiave** .</span><span class="sxs-lookup"><span data-stu-id="77441-199">On the **Private Key** tab, click the **Key type** arrow.</span></span> <span data-ttu-id="77441-200">Selezionare l'opzione di **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="77441-200">Select the **Exchange** option.</span></span>

15. <span data-ttu-id="77441-201">Fare clic su **OK** per salvare le **proprietà del certificato** impostate.</span><span class="sxs-lookup"><span data-stu-id="77441-201">Click **OK** to save the **Certificate Properties** that you have set.</span></span>

16. <span data-ttu-id="77441-202">Nella pagina **registrazione certificati** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="77441-202">On the **Certificate Enrollment** page, click **Next**.</span></span>

17. <span data-ttu-id="77441-203">Nel percorso in **cui si desidera salvare la richiesta offline** , viene richiesto un **nome di file** e un formato di **file** per il salvataggio della richiesta di firma del certificato.</span><span class="sxs-lookup"><span data-stu-id="77441-203">On the **Where do you want to save the offline request?** page, you are prompted for a **File Name** and a **File Format** for saving the certificate signing request.</span></span>

18. <span data-ttu-id="77441-204">Nel campo immissione **nome file** Digitare un percorso e un nome file per la richiesta oppure fare clic su **Sfoglia** per selezionare un percorso per il file e digitare il nome della richiesta.</span><span class="sxs-lookup"><span data-stu-id="77441-204">In the **File Name** entry field, type a path and filename for the request, or click **Browse** to select a location for the file and type the filename for the request.</span></span>

19. <span data-ttu-id="77441-205">Per il **formato di file**, fare clic su **base 64** o **binario**.</span><span class="sxs-lookup"><span data-stu-id="77441-205">For **File format**, click either **Base 64** or **Binary**.</span></span> <span data-ttu-id="77441-206">Selezionare **Base 64** a meno che non venga indicato altrimenti dal fornitore per i certificati.</span><span class="sxs-lookup"><span data-stu-id="77441-206">Select **Base 64** unless you are instructed otherwise by the vendor for your certificates.</span></span>

20. <span data-ttu-id="77441-207">Individuare il file di richiesta salvato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="77441-207">Locate the request file that you saved in the previous step.</span></span> <span data-ttu-id="77441-208">Invia all'autorità di certificazione pubblica.</span><span class="sxs-lookup"><span data-stu-id="77441-208">Submit to your public certification authority.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="77441-209">Microsoft ha identificato le CA pubbliche che soddisfano i requisiti per le comunicazioni unificate.</span><span class="sxs-lookup"><span data-stu-id="77441-209">Microsoft has identified Public CAs that meets the requirements for Unified Communications purposes.</span></span> <span data-ttu-id="77441-210">Un elenco viene mantenuto nell'articolo della Knowledge Base seguente.</span><span class="sxs-lookup"><span data-stu-id="77441-210">A list is maintained in the following knowledge base article.</span></span> <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

