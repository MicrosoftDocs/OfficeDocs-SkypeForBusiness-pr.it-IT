---
title: Richiedere e configurare un certificato per il proxy inverso HTTP
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
ms.openlocfilehash: 2597bf31c9f0cc9f4316f505811426f2c9948a6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a><span data-ttu-id="68464-102">Richiedere e configurare un certificato per il proxy inverso HTTP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68464-102">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68464-103">_**Argomento Ultima modifica:** 2014-02-14_</span><span class="sxs-lookup"><span data-stu-id="68464-103">_**Topic Last Modified:** 2014-02-14_</span></span>

<span data-ttu-id="68464-104">È necessario installare il certificato della CA (Root Certification Authority) nel server che ha eseguito Microsoft Forefront Threat Management Gateway 2010 o IIS ARR per l'infrastruttura CA che ha emesso i certificati del server nei server interni che hanno eseguito Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68464-104">You need to install the root certification authority (CA) certificate on the server running Microsoft Forefront Threat Management Gateway 2010 or IIS ARR for the CA infrastructure that issued the server certificates to the internal servers running Microsoft Lync Server 2013.</span></span>

<span data-ttu-id="68464-105">È inoltre necessario installare un certificato del server Web pubblico nel server proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="68464-105">You also must install a public web server certificate on your reverse proxy server.</span></span> <span data-ttu-id="68464-106">I nomi alternativi dell'oggetto del certificato devono contenere i nomi di dominio completi esterni pubblicati di ogni pool che ospita gli utenti abilitati per l'accesso remoto e gli FQDN esterni di tutti i direttori o i pool di Director che verranno usati all'interno infrastruttura Edge.</span><span class="sxs-lookup"><span data-stu-id="68464-106">This certificate’s subject alternative names should contain the published external fully qualified domain names (FQDNs) of each pool that is home to users enabled for remote access, and the external FQDNs of all Directors or Director pools that will be used within that Edge infrastructure.</span></span> <span data-ttu-id="68464-107">Il nome alternativo soggetto deve contenere anche l'URL semplice della riunione, l'URL semplice per la chiamata in accesso esterno e, se si distribuiscono le applicazioni mobili e si prevede di usare l'individuazione automatica, l'URL del servizio di rilevamento automatico esterni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="68464-107">The subject alternative name must also contain the meeting simple URL, the dial-in simple URL, and, if you are deploying mobile applications and plan to use automatic discovery, the external Autodiscover Service URL as shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="68464-108">Valore</span><span class="sxs-lookup"><span data-stu-id="68464-108">Value</span></span></th>
<th><span data-ttu-id="68464-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="68464-109">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68464-110">Nome oggetto</span><span class="sxs-lookup"><span data-stu-id="68464-110">Subject name</span></span></p></td>
<td><p><span data-ttu-id="68464-111">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="68464-111">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="68464-112">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="68464-112">webext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68464-113">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="68464-113">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="68464-114">FQDN del pool</span><span class="sxs-lookup"><span data-stu-id="68464-114">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="68464-115">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="68464-115">webext.contoso.com</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="68464-116">Il nome dell'oggetto deve essere presente anche nel nome dell'oggetto alternativo.</span><span class="sxs-lookup"><span data-stu-id="68464-116">The subject name must also be present in the subject alternative name.</span></span>

</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68464-117">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="68464-117">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="68464-118">Servizi Web di Director facoltativi (se Director è distribuito)</span><span class="sxs-lookup"><span data-stu-id="68464-118">Optional Director Web Services (if Director is deployed)</span></span></p></td>
<td><p><span data-ttu-id="68464-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="68464-119">webdirext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68464-120">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="68464-120">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="68464-121">URL semplice della riunione</span><span class="sxs-lookup"><span data-stu-id="68464-121">Meeting simple URL</span></span></p>



> [!NOTE]
> <span data-ttu-id="68464-122">Tutti gli URL semplici della riunione devono essere nel nome dell'oggetto alternativo.</span><span class="sxs-lookup"><span data-stu-id="68464-122">All meeting simple URLs must be in the subject alternative name.</span></span> <span data-ttu-id="68464-123">Ogni dominio SIP deve avere almeno un URL semplice della riunione attiva.</span><span class="sxs-lookup"><span data-stu-id="68464-123">Each SIP domain must have at least one active meeting simple URL.</span></span>

</td>
<td><p><span data-ttu-id="68464-124">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="68464-124">meet.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68464-125">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="68464-125">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="68464-126">URL semplice con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="68464-126">Dial-in simple URL</span></span></p></td>
<td><p><span data-ttu-id="68464-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="68464-127">dialin.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68464-128">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="68464-128">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="68464-129">Server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="68464-129">Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="68464-130">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="68464-130">officewebapps01.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68464-131">Nome alternativo soggetto</span><span class="sxs-lookup"><span data-stu-id="68464-131">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="68464-132">URL del servizio di individuazione automatica esterna</span><span class="sxs-lookup"><span data-stu-id="68464-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="68464-133">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="68464-133">lyncdiscover.contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="68464-134">Se si usa anche Microsoft Exchange Server, sarà anche necessario configurare le regole per il proxy inverso per gli URL di Exchange Autodiscover e servizi Web.</span><span class="sxs-lookup"><span data-stu-id="68464-134">If you are also using Microsoft Exchange Server you will also need to configure reverse proxy rules for the Exchange autodiscover and web services URLs.</span></span>

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="68464-135">Se la distribuzione interna è costituita da più server standard o pool Front-End, è necessario configurare le regole di pubblicazione Web per ogni FQDN della Web farm esterna e si avrà bisogno di un certificato e di un listener Web per ogni utente oppure è necessario ottenere un certificato il cui nome alternativo soggetto contiene i nomi usati da tutti i pool, assegnarlo a un listener Web e condividerlo tra più regole di pubblicazione Web.</span><span class="sxs-lookup"><span data-stu-id="68464-135">If your internal deployment consists of more than one Standard Edition server or Front End pool, you must configure web publishing rules for each external web farm FQDN and you will either need a certificate and web listener for each, or you must obtain a certificate whose subject alternative name contains the names used by all of the pools, assign it to a web listener, and share it among multiple web publishing rules.</span></span>



</div>

<div>

## <a name="create-a-certificate-request"></a><span data-ttu-id="68464-136">Creare una richiesta di certificato</span><span class="sxs-lookup"><span data-stu-id="68464-136">Create a Certificate Request</span></span>

<span data-ttu-id="68464-137">Si crea una richiesta di certificato nel proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="68464-137">You create a certificate request on the reverse proxy.</span></span> <span data-ttu-id="68464-138">Si crea una richiesta in un altro computer, ma è necessario esportare il certificato firmato con la chiave privata e importarlo nel proxy inverso dopo averlo ricevuto dall'autorità di certificazione pubblica.</span><span class="sxs-lookup"><span data-stu-id="68464-138">You create a request on another computer, but you must export the signed certificate with the private key and import it onto the reverse proxy once you have received it from the public certification authority.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="68464-139">Una richiesta di certificato o una richiesta di firma del certificato (CSR) è una richiesta a un'autorità di certificazione pubblica (CA) attendibile per la convalida e la firma della chiave pubblica del computer richiedente.</span><span class="sxs-lookup"><span data-stu-id="68464-139">A certificate request or a certificate signing request (CSR) is a request to a trusted public certification authority (CA) to validate and sign the requesting computer’s public key.</span></span> <span data-ttu-id="68464-140">Quando viene generato un certificato, viene creata una chiave pubblica e una chiave privata.</span><span class="sxs-lookup"><span data-stu-id="68464-140">When a certificate is generated, a public key and a private key are created.</span></span> <span data-ttu-id="68464-141">Solo la chiave pubblica è condivisa e firmata.</span><span class="sxs-lookup"><span data-stu-id="68464-141">Only the public key is shared and signed.</span></span> <span data-ttu-id="68464-142">Come suggerisce il nome, la chiave pubblica viene resa disponibile per qualsiasi richiesta pubblica.</span><span class="sxs-lookup"><span data-stu-id="68464-142">As the name implies, the public key is made available to any public request.</span></span> <span data-ttu-id="68464-143">La chiave pubblica è destinata all'uso da parte di client, server e altri richiedenti che devono scambiare informazioni in modo sicuro e convalidare l'identità di un computer.</span><span class="sxs-lookup"><span data-stu-id="68464-143">The public key is for use by clients, servers and other requesters that need to exchange information securely and validate a computer’s identity.</span></span> <span data-ttu-id="68464-144">La chiave privata viene mantenuta protetta e viene usata solo dal computer che ha creato la coppia di chiavi per decrittografare i messaggi crittografati con la relativa chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="68464-144">The private key is kept secured and is used only by the computer that created the key pair to decrypt messages encrypted with its public key.</span></span> <span data-ttu-id="68464-145">La chiave privata può essere usata per altri scopi.</span><span class="sxs-lookup"><span data-stu-id="68464-145">The private key can be used for other purposes.</span></span> <span data-ttu-id="68464-146">Per scopi di proxy inverso, la crittografia dei dati è l'uso principale.</span><span class="sxs-lookup"><span data-stu-id="68464-146">For reverse proxy purposes, data encipherment is the primary use.</span></span> <span data-ttu-id="68464-147">In secondo luogo, l'autenticazione del certificato a livello di chiave del certificato è un altro uso ed è limitata solo alla convalida che un richiedente ha la chiave pubblica del computer o che il computer in cui è presente una chiave pubblica è in realtà il computer che dichiara di essere.</span><span class="sxs-lookup"><span data-stu-id="68464-147">Secondarily, the certificate authentication at the certificate key level is another use, and is limited only to validation that a requester has the computer’s public key, or that the computer that you have a public key for is actually the computer that it claims to be.</span></span>



</div>

<div>


> [!TIP]
> <span data-ttu-id="68464-148">Se si pianificano contemporaneamente i certificati Edge Server e i certificati di proxy inverso, è necessario notare che esiste una notevole somiglianza tra i due requisiti di certificato.</span><span class="sxs-lookup"><span data-stu-id="68464-148">If you plan your Edge Server certificates and your reverse proxy certificates at the same time, you should notice that there is a great deal of similarity between the two certificate requirements.</span></span> <span data-ttu-id="68464-149">Quando si configura e richiede il certificato Edge Server, combinare il server perimetrale e i nomi alternativi dell'oggetto proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="68464-149">When you configure and request your Edge Server certificate, combine the Edge Server and the reverse proxy subject alternative names.</span></span> <span data-ttu-id="68464-150">È possibile usare lo stesso certificato per il proxy inverso se si esportano il certificato e la chiave privata e si copia il file esportato nel proxy inverso e quindi si importano le coppie di certificati e chiavi e le si assegnano le necessarie nelle procedure successive.</span><span class="sxs-lookup"><span data-stu-id="68464-150">You can use the same certificate for your reverse proxy if you export the certificate and the private key and copy the exported file to the reverse proxy and then import the certificate/key pair and assign it as needed in the upcoming procedures.</span></span> <span data-ttu-id="68464-151">Fare riferimento ai requisiti di certificato per il piano&nbsp;Edge Server<A href="lync-server-2013-plan-for-edge-server-certificates.md">per i certificati Edge Server in Lync Server 2013</A> e il riepilogo del proxy inverso per il <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Reverse del certificato in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="68464-151">Refer to the certificate requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A> and the reverse proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate summary - Reverse proxy in Lync Server 2013</A>.</span></span> <span data-ttu-id="68464-152">Assicurarsi di creare il certificato con una chiave privata esportabile.</span><span class="sxs-lookup"><span data-stu-id="68464-152">Make sure that you create the certificate with an exportable private key.</span></span> <span data-ttu-id="68464-153">La creazione della richiesta di certificato e certificato con una chiave privata esportabile è necessaria per i server perimetrali in pool, quindi si tratta di una pratica normale e la procedura guidata certificato nella distribuzione guidata di Lync Server per il server perimetrale consentirà di impostare il contrassegno di <STRONG>creazione della chiave privata esportabile</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="68464-153">Creating the certificate and certificate request with an exportable private key is required for pooled Edge Servers, so this is a normal practice and the Certificate Wizard in the Lync Server Deployment Wizard for the Edge Server will allow you to set the <STRONG>Make private key exportable</STRONG> flag.</span></span> <span data-ttu-id="68464-154">Dopo aver ricevuto la richiesta di certificato dall'autorità di certificazione pubblica, si esporterà il certificato e la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="68464-154">Once you receive the certificate request back from the public certification authority, you will export the certificate and the private key.</span></span> <span data-ttu-id="68464-155">Vedere la sezione "per esportare il certificato con la chiave privata per i server perimetrali in un pool" nell'argomento <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">configurare i certificati per l'interfaccia esterna di Edge per Lync Server 2013</A> per informazioni dettagliate su come creare ed esportare il certificato con una chiave privata.</span><span class="sxs-lookup"><span data-stu-id="68464-155">See the section “To export the certificate with the private key for Edge Servers in a pool” in the topic <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Set up certificates for the external edge interface for Lync Server 2013</A> for details on how to create and export your certificate with a private key.</span></span> <span data-ttu-id="68464-156">L'estensione del certificato deve essere di tipo <STRONG>PFX</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="68464-156">The extension of the certificate should be of type <STRONG>.pfx</STRONG>.</span></span>



</div>

<span data-ttu-id="68464-157">Per generare una richiesta di firma del certificato nel computer in cui verrà assegnato il certificato e la chiave privata, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="68464-157">To generate a certificate signing request on the computer where the certificate and private key will be assigned, you do the following:</span></span>

<span data-ttu-id="68464-158">**Creazione di una richiesta di firma del certificato**</span><span class="sxs-lookup"><span data-stu-id="68464-158">**Creating a certificate signing request**</span></span>

1.  <span data-ttu-id="68464-159">Aprire Microsoft Management Console (MMC) e aggiungere lo snap-in certificati e selezionare **computer**, quindi espandere **personale**.</span><span class="sxs-lookup"><span data-stu-id="68464-159">Open the Microsoft Management Console (MMC) and add the Certificates snap-in and select **Computers**, then expand **Personal**.</span></span> <span data-ttu-id="68464-160">Per informazioni dettagliate su come creare una console certificati in Microsoft Management Console (MMC), vedere [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616).</span><span class="sxs-lookup"><span data-stu-id="68464-160">For details on how to create a certificates console in the Microsoft Management Console (MMC), see [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616).</span></span>

2.  <span data-ttu-id="68464-161">Fare clic con il pulsante destro del mouse su **certificati**, scegliere **tutte le attività**, fare clic su **operazioni avanzate**e su **Crea richiesta personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="68464-161">Right-click **Certificates**, click **All Tasks**, click **Advanced Operations**, click **Create Custom Request**.</span></span>

3.  <span data-ttu-id="68464-162">Nella pagina **registrazione certificati** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="68464-162">On the **Certificate Enrollment** page, click **Next**.</span></span>

4.  <span data-ttu-id="68464-163">Nella pagina **selezionare i criteri di registrazione dei certificati** in **richiesta personalizzata**Selezionare **continua senza criteri di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="68464-163">On the **Select Certificate Enrollment Policy** page under **Custom Request**, select **Proceed without enrollment policy**.</span></span> <span data-ttu-id="68464-164">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="68464-164">Click **Next**.</span></span>

5.  <span data-ttu-id="68464-165">Nella pagina **richiesta personalizzata** , per il **modello** Selezionare **(nessun modello) chiave legacy**.</span><span class="sxs-lookup"><span data-stu-id="68464-165">On the **Custom Request** page, for **Template** select **(No template) Legacy key**.</span></span> <span data-ttu-id="68464-166">Se non diversamente specificato dal provider di certificati, escludere le **estensioni predefinite** deselezionate e la selezione del **formato della richiesta** in **PKCS \#10**.</span><span class="sxs-lookup"><span data-stu-id="68464-166">Unless otherwise directed by your certificate provider, leave **Suppress default extensions** unchecked and the **Request format** selection on **PKCS \#10**.</span></span> <span data-ttu-id="68464-167">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="68464-167">Click **Next**.</span></span>

6.  <span data-ttu-id="68464-168">Nella pagina **informazioni certificato** fare clic su **Dettagli**e quindi su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="68464-168">On the **Certificate Information** page, click **Details**, then click **Properties**.</span></span>

7.  <span data-ttu-id="68464-169">Nella pagina **Proprietà certificato** della scheda **generale** del campo **nome descrittivo** digitare un nome per il certificato.</span><span class="sxs-lookup"><span data-stu-id="68464-169">On the **Certificate Properties** page on the **General** tab in the **Friendly Name** field, type a name for this certificate.</span></span> <span data-ttu-id="68464-170">Facoltativamente, digitare una descrizione nel campo **Descrizione** .</span><span class="sxs-lookup"><span data-stu-id="68464-170">Optionally, type a description in the **Description** field.</span></span> <span data-ttu-id="68464-171">Il nome descrittivo e la descrizione vengono in genere usati dall'amministratore per identificare la finalità del certificato, ad esempio il **listener del proxy inverso per Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="68464-171">The Friendly Name and description are typically used by the Administrator to identify what the certificate purpose is, such as **Reverse Proxy Listener for Lync Server**.</span></span>

8.  <span data-ttu-id="68464-172">Selezionare la scheda **oggetto** . In **nome oggetto** per il **tipo**Selezionare **nome comune** per il tipo di nome soggetto.</span><span class="sxs-lookup"><span data-stu-id="68464-172">Select the **Subject** tab. Under **Subject name** for the **Type**, select **Common name** for the Subject name type.</span></span> <span data-ttu-id="68464-173">Per il **valore**, digitare il nome dell'oggetto che verrà usato per il proxy inverso e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="68464-173">For the **Value**, type the subject name that you will use for the reverse proxy, and then click **Add**.</span></span> <span data-ttu-id="68464-174">Nell'esempio fornito nella tabella in questo argomento, il nome dell'oggetto è webext.contoso.com e verrebbe digitato nel campo valore per il nome dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="68464-174">In the example provided in the table in this topic, the subject name is webext.contoso.com and would be typed into the Value field for the Subject name.</span></span>

9.  <span data-ttu-id="68464-175">Nella scheda **oggetto** in **nome alternativo**Selezionare **DNS** nell'elenco a discesa per **tipo**.</span><span class="sxs-lookup"><span data-stu-id="68464-175">On the **Subject** tab under **Alternative name**, select **DNS** from the drop down for **Type**.</span></span> <span data-ttu-id="68464-176">Per ogni nome alternativo soggetto definito richiesto nel certificato, digitare il nome di dominio completo e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="68464-176">For each defined subject alternative name that you require on the certificate, type the fully qualified domain name, then click **Add**.</span></span> <span data-ttu-id="68464-177">Ad esempio, nella tabella sono presenti tre nomi alternativi oggetto, meet.contoso.com, dialin.contoso.com e lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="68464-177">For example, in the table there are three subject alternative names, meet.contoso.com, dialin.contoso.com, and lyncdiscover.contoso.com.</span></span> <span data-ttu-id="68464-178">Nel campo **valore** Digitare meet.contoso.com, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="68464-178">In the **Value** field, type meet.contoso.com, then click **Add**.</span></span> <span data-ttu-id="68464-179">Ripetere la procedura per ogni nome alternativo soggetto che è necessario definire.</span><span class="sxs-lookup"><span data-stu-id="68464-179">Repeat for each subject alternative names that you need to define.</span></span>

10. <span data-ttu-id="68464-180">Nella pagina **Proprietà certificato** fare clic sulla scheda **estensioni** . In questa pagina definirai gli scopi della chiave crittografica nell' **uso delle chiavi** e l'uso della chiave estesa nell'uso della chiave **estesa (criteri applicazione)**.</span><span class="sxs-lookup"><span data-stu-id="68464-180">On the **Certificate Properties** page, click the **Extensions** tab. On this page, you will define the cryptographic key purposes in **Key usage** and the extended key usage in **Extended Key Usage (application policies)**.</span></span>

11. <span data-ttu-id="68464-181">Fare clic sulla freccia **uso chiave** per visualizzare le **opzioni disponibili**.</span><span class="sxs-lookup"><span data-stu-id="68464-181">Click the **Key usage** arrow to show the **Available options**.</span></span> <span data-ttu-id="68464-182">In opzioni disponibili fare clic su **firma digitale**, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="68464-182">Under Available options, click **Digital signature**, then click **Add**.</span></span> <span data-ttu-id="68464-183">Fare clic su **crittografia chiave**, quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="68464-183">Click **Key encipherment**, then click **Add**.</span></span> <span data-ttu-id="68464-184">Se la casella di controllo per **rendere questi usi chiave Critical** è deselezionata, selezionare la casella di spunta.</span><span class="sxs-lookup"><span data-stu-id="68464-184">If the checkbox for **Make these key usages critical** is unchecked, select the checkbox.</span></span>

12. <span data-ttu-id="68464-185">Fare clic sulla freccia **uso esteso chiave (criteri applicazione)** per visualizzare le **opzioni disponibili**.</span><span class="sxs-lookup"><span data-stu-id="68464-185">Click the **Extended Key Usage (application policies)** arrow to show the **Available options**.</span></span> <span data-ttu-id="68464-186">In opzioni disponibili fare clic su **autenticazione server**e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="68464-186">Under Available options, click **Server Authentication**, then click **Add**.</span></span> <span data-ttu-id="68464-187">Fare clic su **autenticazione client**, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="68464-187">Click **Client Authentication**, then click **Add**.</span></span> <span data-ttu-id="68464-188">Se la casella di controllo per **l'uso delle chiavi estese** è selezionata, deselezionare la casella.</span><span class="sxs-lookup"><span data-stu-id="68464-188">If the check box for **Make the Extended Key Usages critical** is checked, unselect the checkbox.</span></span> <span data-ttu-id="68464-189">Contrariamente alla casella di controllo utilizzo chiave (che deve essere selezionata), è necessario assicurarsi che la casella di controllo utilizzo tasti esteso non sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="68464-189">Contrary to the Key usage checkbox (which must be checked) you must be sure that the Extended Key Usage checkbox is not checked.</span></span>

13. <span data-ttu-id="68464-190">Nella pagina **Proprietà certificato** fare clic sulla scheda **chiave privata** . fare clic sulla freccia **Opzioni chiave** .</span><span class="sxs-lookup"><span data-stu-id="68464-190">On the **Certificate Properties** page, click the **Private Key** tab. Click the **Key options** arrow.</span></span> <span data-ttu-id="68464-191">Per le **dimensioni della chiave**, selezionare **2048** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="68464-191">For **Key size**, select **2048** from the drop down.</span></span> <span data-ttu-id="68464-192">Se si sta generando questa coppia di chiavi e la RSI in un computer diverso dal proxy inverso per cui è destinato il certificato, selezionare **Rendi chiave privata esportabile**.</span><span class="sxs-lookup"><span data-stu-id="68464-192">If you are generating this key pair and CSR on a computer other than the reverse proxy that this certificate is intended for, select **Make private key exportable**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" /><span data-ttu-id="68464-194">Nota sulla sicurezza:</span><span class="sxs-lookup"><span data-stu-id="68464-194">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="68464-195">La selezione di <strong>una chiave privata esportabile</strong> viene in genere consigliata quando si hanno più proxy inversa in una farm, perché il certificato e la chiave privata vengono copiati in ogni computer della farm.</span><span class="sxs-lookup"><span data-stu-id="68464-195">Selecting <strong>Make a private key exportable</strong> is generally advised when you have more than one reverse proxy in a farm because you will copy the certificate and the private key to each machine in the farm.</span></span> <span data-ttu-id="68464-196">Se si consente la creazione di una chiave privata esportabile, è necessario prestare particolare attenzione al certificato e al computer in cui è stato generato.</span><span class="sxs-lookup"><span data-stu-id="68464-196">If you do allow for an exportable private key, you must take extra care with the certificate and the computer that it is generated on.</span></span> <span data-ttu-id="68464-197">La chiave privata, se compromessa, renderà il certificato inutile e potenzialmente esporrà il computer o i computer all'accesso esterno e ad altre vulnerabilità della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="68464-197">The private key, if compromised, will render the certificate useless as well as potentially expose the computer or computers to external access and other security vulnerabilities.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. <span data-ttu-id="68464-198">Nella scheda **chiave privata** fare clic sulla freccia del **tipo di chiave** .</span><span class="sxs-lookup"><span data-stu-id="68464-198">On the **Private Key** tab, click the **Key type** arrow.</span></span> <span data-ttu-id="68464-199">Selezionare l'opzione di **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="68464-199">Select the **Exchange** option.</span></span>

15. <span data-ttu-id="68464-200">Fare clic su **OK** per salvare le **proprietà del certificato** impostate.</span><span class="sxs-lookup"><span data-stu-id="68464-200">Click **OK** to save the **Certificate Properties** that you have set.</span></span>

16. <span data-ttu-id="68464-201">Nella pagina **registrazione certificati** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="68464-201">On the **Certificate Enrollment** page, click **Next**.</span></span>

17. <span data-ttu-id="68464-202">Nella pagina **dove si vuole salvare la richiesta offline?** , viene richiesto un **nome di file** e un **formato di file** per salvare la richiesta di firma del certificato.</span><span class="sxs-lookup"><span data-stu-id="68464-202">On the **Where do you want to save the offline request?** page, you are prompted for a **File Name** and a **File Format** for saving the certificate signing request.</span></span>

18. <span data-ttu-id="68464-203">Nel campo immissione **nome file** Digitare un percorso e un nome per la richiesta oppure fare clic su **Sfoglia** per selezionare una posizione per il file e digitare il nome file per la richiesta.</span><span class="sxs-lookup"><span data-stu-id="68464-203">In the **File Name** entry field, type a path and filename for the request, or click **Browse** to select a location for the file and type the filename for the request.</span></span>

19. <span data-ttu-id="68464-204">Per il **formato di file**, fare clic su **base 64** o **binario**.</span><span class="sxs-lookup"><span data-stu-id="68464-204">For **File format**, click either **Base 64** or **Binary**.</span></span> <span data-ttu-id="68464-205">Selezionare **Base 64** a meno che non venga indicato diversamente dal fornitore per i certificati.</span><span class="sxs-lookup"><span data-stu-id="68464-205">Select **Base 64** unless you are instructed otherwise by the vendor for your certificates.</span></span>

20. <span data-ttu-id="68464-206">Individuare il file di richiesta salvato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="68464-206">Locate the request file that you saved in the previous step.</span></span> <span data-ttu-id="68464-207">Invia alla tua autorità di certificazione pubblica.</span><span class="sxs-lookup"><span data-stu-id="68464-207">Submit to your public certification authority.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="68464-208">Microsoft ha identificato le CA pubbliche che soddisfano i requisiti per scopi di comunicazioni unificate.</span><span class="sxs-lookup"><span data-stu-id="68464-208">Microsoft has identified Public CAs that meets the requirements for Unified Communications purposes.</span></span> <span data-ttu-id="68464-209">Un elenco viene gestito nell'articolo della Knowledge Base seguente.</span><span class="sxs-lookup"><span data-stu-id="68464-209">A list is maintained in the following knowledge base article.</span></span> <A href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

