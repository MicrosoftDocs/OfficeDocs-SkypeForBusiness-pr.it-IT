---
title: "Lync Server 2013: configurazione dei certificati per l'individuazione automatica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e2f39db761462f2f92ebde377fc9c9ecc5c27b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="64f8d-102">Configurazione dei certificati per l'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64f8d-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64f8d-103">_**Ultimo argomento modificato:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="64f8d-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="64f8d-104">I certificati per il pool di server Director, per il pool Front end e per il proxy inverso richiedono ulteriori voci del nome alternativo del soggetto per il supporto delle connessioni sicure con i client Lync.</span><span class="sxs-lookup"><span data-stu-id="64f8d-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="64f8d-105">È possibile utilizzare il cmdlet <STRONG>Get-CsCertificate</STRONG> per visualizzare le informazioni sui certificati attualmente assegnati.</span><span class="sxs-lookup"><span data-stu-id="64f8d-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="64f8d-106">Tuttavia, la visualizzazione predefinita tronca le proprietà del certificato e non Visualizza tutti i valori della proprietà SubjectAlternativeNames.</span><span class="sxs-lookup"><span data-stu-id="64f8d-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="64f8d-107">È possibile utilizzare i cmdlet <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate e <STRONG>Set-CsCertificate</STRONG> per visualizzare alcune informazioni e per richiedere e assegnare i certificati.</span><span class="sxs-lookup"><span data-stu-id="64f8d-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="64f8d-108">Tuttavia, non è il metodo migliore da utilizzare se non si è sicuri delle proprietà dei nomi alternativi del soggetto (SAN) nel certificato corrente.</span><span class="sxs-lookup"><span data-stu-id="64f8d-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="64f8d-109">Per visualizzare il certificato e tutti i membri della proprietà, è consigliabile utilizzare lo snap-in certificati di <EM>Microsoft Management Console (MMC)</EM> o utilizzare la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64f8d-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="64f8d-110">Nella distribuzione guidata di Lync Server, è possibile utilizzare la configurazione guidata certificati per visualizzare le proprietà del certificato.</span><span class="sxs-lookup"><span data-stu-id="64f8d-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="64f8d-111">Le procedure per la visualizzazione, la richiesta e l'assegnazione di un certificato tramite Lync Server Management Shell e <EM>Microsoft Management Console (MMC)</EM> sono descritte nelle procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="64f8d-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="64f8d-112">Per utilizzare la distribuzione guidata di Lync Server, vedere informazioni dettagliate in questo articolo se è stato distribuito il pool di Director o Director facoltativo: <A href="lync-server-2013-configure-certificates-for-the-director.md">configurare i certificati per il server Director in Lync 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="64f8d-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="64f8d-113">Per il front end server o il pool Front End, vedere i dettagli qui: <A href="lync-server-2013-configure-certificates-for-servers.md">configurare i certificati per i server in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="64f8d-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="64f8d-114">I passaggi iniziali di questa procedura sono i passaggi di preparazione, per orientare il ruolo che i certificati correnti risuonano.</span><span class="sxs-lookup"><span data-stu-id="64f8d-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="64f8d-115">Per impostazione predefinita, i certificati non avranno un lyncdiscover. &lt;SipDomain&gt; o LyncdiscoverInternal. &lt;la voce del&gt; nome di dominio interno, a meno che non siano stati precedentemente installati servizi per dispositivi mobili o che i certificati siano stati preparati in anticipo.</span><span class="sxs-lookup"><span data-stu-id="64f8d-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="64f8d-116">In questa procedura viene utilizzato il nome di dominio SIP ' contoso.com ' e il nome di dominio interno ' contoso.net ' di esempio.</span><span class="sxs-lookup"><span data-stu-id="64f8d-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="64f8d-117">La configurazione predefinita dei certificati per Lync Server 2013 e Lync Server 2010 prevede l'utilizzo di un singolo certificato (denominato ' default ') con l'impostazione predefinita per tutti gli scopi, ad eccezione dei servizi Web, WebServicesExternal e WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="64f8d-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="64f8d-118">Una configurazione facoltativa consiste nell'utilizzare certificati distinti per ogni scopo.</span><span class="sxs-lookup"><span data-stu-id="64f8d-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="64f8d-119">I certificati possono essere gestiti utilizzando i cmdlet di Lync Server Management Shell e Windows PowerShell oppure utilizzando la procedura guidata certificate nella distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64f8d-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="64f8d-120">Per aggiornare i certificati con i nuovi nomi alternativi del soggetto mediante Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="64f8d-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="64f8d-121">Accedere al computer utilizzando un account che disponga dei diritti e delle autorizzazioni di amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="64f8d-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="64f8d-122">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="64f8d-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="64f8d-123">Individuare quali certificati sono stati assegnati al server e per quale tipo di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="64f8d-123">Find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="64f8d-124">Per assegnare il certificato aggiornato, è necessario utilizzare queste informazioni nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="64f8d-124">You need this information in the next step to assign the updated certificate.</span></span> <span data-ttu-id="64f8d-125">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="64f8d-125">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="64f8d-126">Esaminare l'output del passaggio precedente per verificare se un singolo certificato è assegnato a più utilizzi o se è stato assegnato un certificato diverso per ogni utilizzo.</span><span class="sxs-lookup"><span data-stu-id="64f8d-126">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="64f8d-127">Esaminare il parametro Use per scoprire come viene utilizzato un certificato.</span><span class="sxs-lookup"><span data-stu-id="64f8d-127">Look in the Use parameter to find out how a certificate is used.</span></span> <span data-ttu-id="64f8d-128">Confrontare il parametro identificazione personale per i certificati visualizzati per vedere se lo stesso certificato dispone di più utilizzi.</span><span class="sxs-lookup"><span data-stu-id="64f8d-128">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="64f8d-129">Aggiornare il certificato.</span><span class="sxs-lookup"><span data-stu-id="64f8d-129">Update the certificate.</span></span> <span data-ttu-id="64f8d-130">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="64f8d-130">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="64f8d-131">Ad esempio, se il cmdlet **Get-CsCertificate** ha visualizzato un certificato con l'utilizzo di default, un altro con un utilizzo di WebServicesInternal e un altro con un utilizzo di WebServicesExternal e tutti avevano lo stesso valore di identificazione personale, nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="64f8d-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="64f8d-132">**Importante:**</span><span class="sxs-lookup"><span data-stu-id="64f8d-132">**Important:**</span></span>
    
    <span data-ttu-id="64f8d-133">Se per ogni utilizzo viene assegnato un certificato separato (il valore di identificazione personale è diverso per ogni certificato), è importante non eseguire il cmdlet **Set-CsCertificate** con più tipi.</span><span class="sxs-lookup"><span data-stu-id="64f8d-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="64f8d-134">In questo caso, eseguire il cmdlet **Set-CsCertificate** separatamente per ogni utilizzo.</span><span class="sxs-lookup"><span data-stu-id="64f8d-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="64f8d-135">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="64f8d-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="64f8d-136">Per visualizzare il certificato, fare clic sul pulsante **Start**, scegliere **Esegui...**.</span><span class="sxs-lookup"><span data-stu-id="64f8d-136">To view the certificate, click **Start**, click **Run…**.</span></span> <span data-ttu-id="64f8d-137">Digitare MMC per aprire Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="64f8d-137">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="64f8d-138">Scegliere **file**dal menu MMC, selezionare **Aggiungi/Rimuovi snap-in...**, selezionare certificati.</span><span class="sxs-lookup"><span data-stu-id="64f8d-138">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="64f8d-139">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="64f8d-139">Click **Add**.</span></span> <span data-ttu-id="64f8d-140">Quando richiesto, selezionare **account computer**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="64f8d-140">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="64f8d-141">Se il certificato è presente nel computer in cui si trova, selezionare **computer locale**.</span><span class="sxs-lookup"><span data-stu-id="64f8d-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="64f8d-142">Se il certificato si trova in un altro computer, selezionare **un altro computer**, digitare il nome di dominio completo del computer oppure fare clic su **Sfoglia** in **immettere il nome dell'oggetto da selezionare**, digitare il nome del computer.</span><span class="sxs-lookup"><span data-stu-id="64f8d-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="64f8d-143">Fare clic su **Controlla nomi**.</span><span class="sxs-lookup"><span data-stu-id="64f8d-143">Click **Check Names**.</span></span> <span data-ttu-id="64f8d-144">Quando il nome del computer viene risolto, verrà sottolineato.</span><span class="sxs-lookup"><span data-stu-id="64f8d-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="64f8d-145">Fare clic su **OK**, quindi su **fine**.</span><span class="sxs-lookup"><span data-stu-id="64f8d-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="64f8d-146">Fare clic su **OK** per eseguire il commit della selezione e chiudere la finestra di dialogo **Aggiungi o Rimuovi snap-** in.</span><span class="sxs-lookup"><span data-stu-id="64f8d-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="64f8d-147">Se il certificato non viene visualizzato nella console, verificare che l'utente o il servizio non sia stato selezionato.</span><span class="sxs-lookup"><span data-stu-id="64f8d-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="64f8d-148">È necessario selezionare il computer oppure non sarà possibile individuare il certificato probper.</span><span class="sxs-lookup"><span data-stu-id="64f8d-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="64f8d-149">Per visualizzare le proprietà del certificato, espandere **certificati**, espandere **personale**e selezionare **certificati**.</span><span class="sxs-lookup"><span data-stu-id="64f8d-149">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="64f8d-150">Selezionare il certificato da visualizzare, fare clic con il pulsante destro del mouse sul certificato e scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="64f8d-150">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="64f8d-151">Nella visualizzazione **certificato** selezionare **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="64f8d-151">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="64f8d-152">Da qui, è possibile selezionare il nome del soggetto del certificato selezionando **oggetto** e vengono visualizzati il nome del soggetto assegnato e le proprietà associate.</span><span class="sxs-lookup"><span data-stu-id="64f8d-152">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="64f8d-153">Per visualizzare i nomi alternativi del soggetto assegnati, selezionare **nome alternativo soggetto**.</span><span class="sxs-lookup"><span data-stu-id="64f8d-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="64f8d-154">Vengono visualizzati tutti i nomi alternativi del soggetto assegnati.</span><span class="sxs-lookup"><span data-stu-id="64f8d-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="64f8d-155">Per impostazione predefinita, i nomi alternativi del soggetto trovati nella proprietà sono di tipo **DNS Name** .</span><span class="sxs-lookup"><span data-stu-id="64f8d-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="64f8d-156">Verranno visualizzati i membri seguenti (tutti i nomi di dominio completi rappresentati nei record host DNS (A o, se IPv6 AAAA):</span><span class="sxs-lookup"><span data-stu-id="64f8d-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="64f8d-157">Nome del pool per il pool o nome del server singolo se non si tratta di un pool</span><span class="sxs-lookup"><span data-stu-id="64f8d-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="64f8d-158">Nome del server a cui è assegnato il certificato</span><span class="sxs-lookup"><span data-stu-id="64f8d-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="64f8d-159">Simple URL Records, in genere Meet e dialin</span><span class="sxs-lookup"><span data-stu-id="64f8d-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="64f8d-160">Servizi Web interni e nomi esterni dei servizi Web (ad esempio, webpool01.contoso.net, webpool01.contoso.com), in base alle scelte effettuate in Generatore di topologie e le selezioni dei servizi Web in corso.</span><span class="sxs-lookup"><span data-stu-id="64f8d-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="64f8d-161">Se è già stato assegnato, il lyncdiscover. \<SipDomain\> e lyncdiscoverinternal. \<record\> di SipDomain.</span><span class="sxs-lookup"><span data-stu-id="64f8d-161">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="64f8d-162">L'ultimo elemento è quello che più ti interessa: se è presente una voce di SAN Lyncdiscover e lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="64f8d-162">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="64f8d-163">Dopo aver apportato queste informazioni, è possibile chiudere la visualizzazione certificati e MMC.</span><span class="sxs-lookup"><span data-stu-id="64f8d-163">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="64f8d-164">Se si tratta di un servizio di individuazione automatica, ovvero lyncdiscover. \>nome\> di dominio e lyncdiscoverinternal. \<nome\> di dominio (a seconda se si tratta di un certificato esterno o interno) il nome alternativo del soggetto è mancante e si utilizza un singolo certificato predefinito per i tipi default, WebServicesInternal e WebServiceExternal, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="64f8d-164">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\> (based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="64f8d-165">Al prompt dei comandi della riga di comando di Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="64f8d-165">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="64f8d-166">Se si dispone di molti domini SIP, non è possibile utilizzare il nuovo parametro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="64f8d-166">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="64f8d-167">Al contrario, è necessario utilizzare il parametro DomainName.</span><span class="sxs-lookup"><span data-stu-id="64f8d-167">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="64f8d-168">Quando si utilizza il parametro DomainName, è necessario definire il nome di dominio completo per i record LyncdiscoverInternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="64f8d-168">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="64f8d-169">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="64f8d-169">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="64f8d-170">Per assegnare il certificato, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="64f8d-170">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="64f8d-171">Dove "identificazione personale" è l'identificazione digitale visualizzata per il certificato appena emesso.</span><span class="sxs-lookup"><span data-stu-id="64f8d-171">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="64f8d-172">Per un nome alternativo del soggetto di individuazione automatica mancante quando si utilizzano certificati distinti per default, WebServicesInternal e WebServicesExternal, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="64f8d-172">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="64f8d-173">Al prompt dei comandi della riga di comando di Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="64f8d-173">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="64f8d-174">Se si dispone di molti domini SIP, non è possibile utilizzare il nuovo parametro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="64f8d-174">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="64f8d-175">Al contrario, è necessario utilizzare il parametro DomainName.</span><span class="sxs-lookup"><span data-stu-id="64f8d-175">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="64f8d-176">Quando si utilizza il parametro DomainName, è necessario utilizzare un prefisso appropriato per il nome FQDN del dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="64f8d-176">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="64f8d-177">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="64f8d-177">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="64f8d-178">Per un nome alternativo del soggetto di individuazione automatica esterno mancante, nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="64f8d-178">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="64f8d-179">Se si dispone di molti domini SIP, non è possibile utilizzare il nuovo parametro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="64f8d-179">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="64f8d-180">Al contrario, è necessario utilizzare il parametro DomainName.</span><span class="sxs-lookup"><span data-stu-id="64f8d-180">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="64f8d-181">Quando si utilizza il parametro DomainName, è necessario utilizzare un prefisso appropriato per il nome FQDN del dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="64f8d-181">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="64f8d-182">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="64f8d-182">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="64f8d-183">Per assegnare i singoli tipi di certificato, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="64f8d-183">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="64f8d-184">Dove "identificazione personale" è l'identificazione digitale visualizzata per i singoli certificati appena emessi.</span><span class="sxs-lookup"><span data-stu-id="64f8d-184">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

