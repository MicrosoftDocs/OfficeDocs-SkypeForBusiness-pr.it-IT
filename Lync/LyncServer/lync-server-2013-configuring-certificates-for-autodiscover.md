---
title: "Lync Server 2013: configurazione dei certificati per l'individuazione automatica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d0270aa76adb7cef2a6da8f6a4f9cb6db090e78
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="8afa3-102">Configurazione dei certificati per l'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8afa3-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8afa3-103">_**Argomento Ultima modifica:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="8afa3-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="8afa3-104">I certificati per il pool di Director, il pool Front-end e il proxy inverso richiedono ulteriori voci di nomi alternativi per supportare connessioni sicure con i client Lync.</span><span class="sxs-lookup"><span data-stu-id="8afa3-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8afa3-105">Puoi usare il cmdlet <STRONG>Get-CsCertificate</STRONG> per visualizzare le informazioni sui certificati attualmente assegnati.</span><span class="sxs-lookup"><span data-stu-id="8afa3-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="8afa3-106">La visualizzazione predefinita, tuttavia, tronca le proprietà del certificato e non Visualizza tutti i valori nella proprietà SubjectAlternativeNames.</span><span class="sxs-lookup"><span data-stu-id="8afa3-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="8afa3-107">È possibile usare i cmdlet <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate e <STRONG>Set-CsCertificate</STRONG> per visualizzare alcune informazioni e per richiedere e assegnare certificati.</span><span class="sxs-lookup"><span data-stu-id="8afa3-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="8afa3-108">Tuttavia, non è il metodo migliore da usare se non si è certi delle proprietà dei nomi alternativi oggetto (SAN) del certificato corrente.</span><span class="sxs-lookup"><span data-stu-id="8afa3-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="8afa3-109">Per visualizzare il certificato e tutti i membri della proprietà, è consigliabile usare lo snap-in certificati di <EM>Microsoft Management Console (MMC)</EM> o usare la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8afa3-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="8afa3-110">Nella distribuzione guidata di Lync Server è possibile usare la procedura guidata certificato per visualizzare le proprietà del certificato.</span><span class="sxs-lookup"><span data-stu-id="8afa3-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="8afa3-111">Le procedure per la visualizzazione, la richiesta e l'assegnazione di un certificato tramite Lync Server Management Shell e <EM>Microsoft Management Console (MMC)</EM> sono descritte in dettaglio nelle procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="8afa3-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="8afa3-112">Per usare la distribuzione guidata di Lync Server, vedere i dettagli qui se è stato distribuito il pool di Director o Director facoltativi: <A href="lync-server-2013-configure-certificates-for-the-director.md">configurare i certificati per il Director in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8afa3-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="8afa3-113">Per il server front-end o il pool Front-End, vedere i dettagli qui: <A href="lync-server-2013-configure-certificates-for-servers.md">configurare i certificati per i server in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8afa3-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="8afa3-114">I passaggi iniziali di questa procedura sono i passaggi di preparazione per orientare l'utente sul ruolo riprodotto dai certificati correnti.</span><span class="sxs-lookup"><span data-stu-id="8afa3-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="8afa3-115">Per impostazione predefinita, i certificati non avranno un lyncdiscover. &lt;SipDomain&gt; o LyncdiscoverInternal. &lt;inserimento di un&gt; nome di dominio interno a meno che non siano stati installati in precedenza i servizi di mobilità o non siano stati preparati preventivamente i certificati.</span><span class="sxs-lookup"><span data-stu-id="8afa3-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="8afa3-116">Questa procedura usa il nome di dominio SIP di esempio "contoso.com" e il nome di dominio interno di esempio "contoso.net".</span><span class="sxs-lookup"><span data-stu-id="8afa3-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="8afa3-117">La configurazione predefinita dei certificati per Lync Server 2013 e Lync Server 2010 consiste nell'usare un singolo certificato (denominato "default") con l'impostazione predefinita per tutti gli scopi, ad eccezione dei servizi Web, WebServicesExternal e WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="8afa3-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="8afa3-118">Una configurazione facoltativa prevede l'uso di certificati distinti per ogni scopo.</span><span class="sxs-lookup"><span data-stu-id="8afa3-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="8afa3-119">I certificati possono essere gestiti usando i cmdlet di Lync Server Management Shell e Windows PowerShell oppure usando la creazione guidata certificati nella distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8afa3-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="8afa3-120">Per aggiornare i certificati con i nuovi nomi alternativi del soggetto tramite Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8afa3-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="8afa3-121">Accedere al computer usando un account che disponga dei diritti e delle autorizzazioni di amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="8afa3-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="8afa3-122">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8afa3-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8afa3-123">Individuare i certificati assegnati al server e per il tipo di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="8afa3-123">Find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="8afa3-124">Queste informazioni sono necessarie nel passaggio successivo per assegnare il certificato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="8afa3-124">You need this information in the next step to assign the updated certificate.</span></span> <span data-ttu-id="8afa3-125">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="8afa3-125">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="8afa3-126">Esaminare l'output del passaggio precedente per verificare se è stato assegnato un singolo certificato per più usi o se è stato assegnato un certificato diverso per ogni utilizzo.</span><span class="sxs-lookup"><span data-stu-id="8afa3-126">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="8afa3-127">Esaminare il parametro Use per scoprire in che modo viene usato un certificato.</span><span class="sxs-lookup"><span data-stu-id="8afa3-127">Look in the Use parameter to find out how a certificate is used.</span></span> <span data-ttu-id="8afa3-128">Confrontare il parametro identificazione personale per i certificati visualizzati per verificare se lo stesso certificato ha più usi.</span><span class="sxs-lookup"><span data-stu-id="8afa3-128">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="8afa3-129">Aggiornare il certificato.</span><span class="sxs-lookup"><span data-stu-id="8afa3-129">Update the certificate.</span></span> <span data-ttu-id="8afa3-130">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="8afa3-130">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="8afa3-131">Ad esempio, se il cmdlet **Get-CsCertificate** Visualizza un certificato con l'uso di default, un altro con l'uso di WebServicesInternal e un altro con l'uso di WebServicesExternal e tutti avevano lo stesso valore di identificazione personale, nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="8afa3-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="8afa3-132">**Importante:**</span><span class="sxs-lookup"><span data-stu-id="8afa3-132">**Important:**</span></span>
    
    <span data-ttu-id="8afa3-133">Se per ogni uso viene assegnato un certificato distinto (il valore di identificazione personale è diverso per ogni certificato), è importante non eseguire il cmdlet **Set-CsCertificate** con più tipi.</span><span class="sxs-lookup"><span data-stu-id="8afa3-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="8afa3-134">In questo caso, eseguire il cmdlet **Set-CsCertificate** separatamente per ogni utilizzo.</span><span class="sxs-lookup"><span data-stu-id="8afa3-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="8afa3-135">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8afa3-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="8afa3-136">Per visualizzare il certificato, fare clic sul pulsante **Start**, scegliere **Esegui...**.</span><span class="sxs-lookup"><span data-stu-id="8afa3-136">To view the certificate, click **Start**, click **Run…**.</span></span> <span data-ttu-id="8afa3-137">Digitare MMC per aprire Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="8afa3-137">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="8afa3-138">Nel menu MMC selezionare **file**, selezionare **Aggiungi/Rimuovi snap-in...**, selezionare certificati.</span><span class="sxs-lookup"><span data-stu-id="8afa3-138">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="8afa3-139">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8afa3-139">Click **Add**.</span></span> <span data-ttu-id="8afa3-140">Quando richiesto, selezionare **account computer**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8afa3-140">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="8afa3-141">Se il certificato si trova in questo computer, selezionare **computer locale**.</span><span class="sxs-lookup"><span data-stu-id="8afa3-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="8afa3-142">Se il certificato si trova in un altro computer, selezionare **un altro computer**, digitare il nome di dominio completo del computer o fare clic su **Sfoglia** in immettere il nome dell' **oggetto da selezionare**, digitare il nome del computer.</span><span class="sxs-lookup"><span data-stu-id="8afa3-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="8afa3-143">Fare clic su **Controlla nomi**.</span><span class="sxs-lookup"><span data-stu-id="8afa3-143">Click **Check Names**.</span></span> <span data-ttu-id="8afa3-144">Quando il nome del computer viene risolto, sarà sottolineato.</span><span class="sxs-lookup"><span data-stu-id="8afa3-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="8afa3-145">Fare clic su **OK**e quindi su **fine**.</span><span class="sxs-lookup"><span data-stu-id="8afa3-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="8afa3-146">Fare clic su **OK** per confermare la selezione e chiudere la finestra di dialogo **Aggiungi o Rimuovi snap-** in.</span><span class="sxs-lookup"><span data-stu-id="8afa3-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8afa3-147">Se il certificato non viene visualizzato nella console, verificare che non sia stato selezionato un utente o un servizio.</span><span class="sxs-lookup"><span data-stu-id="8afa3-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="8afa3-148">È necessario selezionare computer oppure non sarà possibile individuare il certificato probper.</span><span class="sxs-lookup"><span data-stu-id="8afa3-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="8afa3-149">Per visualizzare le proprietà del certificato, espandere **certificati**, espandere **personale**e selezionare **certificati**.</span><span class="sxs-lookup"><span data-stu-id="8afa3-149">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="8afa3-150">Selezionare il certificato da visualizzare, fare clic con il pulsante destro del mouse sul certificato e scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="8afa3-150">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="8afa3-151">Nella visualizzazione **certificato** selezionare **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="8afa3-151">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="8afa3-152">Da qui è possibile selezionare il nome del soggetto del certificato selezionando **oggetto** e il nome del soggetto assegnato e le proprietà associate verranno visualizzate.</span><span class="sxs-lookup"><span data-stu-id="8afa3-152">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="8afa3-153">Per visualizzare i nomi alternativi oggetto assegnati, selezionare **nome alternativo soggetto**.</span><span class="sxs-lookup"><span data-stu-id="8afa3-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="8afa3-154">Vengono visualizzati tutti i nomi alternativi soggetti assegnati.</span><span class="sxs-lookup"><span data-stu-id="8afa3-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="8afa3-155">I nomi alternativi oggetto trovati nella proprietà sono di tipo **DNS Name** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8afa3-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="8afa3-156">Dovrebbero essere visualizzati i membri seguenti (che dovrebbero essere tutti nomi di dominio completi rappresentati nei record host DNS (A o, se IPv6 AAAA):</span><span class="sxs-lookup"><span data-stu-id="8afa3-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="8afa3-157">Nome del pool per il pool o nome del server singolo se non si tratta di un pool</span><span class="sxs-lookup"><span data-stu-id="8afa3-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="8afa3-158">Nome del server a cui è assegnato il certificato</span><span class="sxs-lookup"><span data-stu-id="8afa3-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="8afa3-159">Record URL semplici, in genere incontra e componi</span><span class="sxs-lookup"><span data-stu-id="8afa3-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="8afa3-160">Servizi Web Internal e Web Services External names (ad esempio, webpool01.contoso.net, webpool01.contoso.com), in base alle scelte effettuate in Generatore di topologia e alle selezioni di servizi Web sovrascritte.</span><span class="sxs-lookup"><span data-stu-id="8afa3-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="8afa3-161">Se è già stata assegnata, Lyncdiscover. \<SipDomain\> e lyncdiscoverinternal. \<record\> di SipDomain.</span><span class="sxs-lookup"><span data-stu-id="8afa3-161">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="8afa3-162">L'ultimo elemento è quello che più ti interessa: se c'è una voce di SAN Lyncdiscover e lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="8afa3-162">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="8afa3-163">Dopo aver ottenuto queste informazioni, è possibile chiudere la visualizzazione certificato e la console MMC.</span><span class="sxs-lookup"><span data-stu-id="8afa3-163">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="8afa3-164">Se un servizio di individuazione automatica, ovvero lyncdiscover. \>nome\> di dominio e lyncdiscoverinternal. \<nome\> di dominio (in base a se si tratta di un certificato esterno o interno) il nome alternativo dell'oggetto non è presente e si usa un unico certificato predefinito per i tipi default, WebServicesInternal e WebServiceExternal, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8afa3-164">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\> (based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="8afa3-165">Al prompt della riga di comando di Lync Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="8afa3-165">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="8afa3-166">Se si hanno molti domini SIP, non è possibile usare il nuovo parametro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="8afa3-166">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="8afa3-167">Devi invece usare il parametro DomainName.</span><span class="sxs-lookup"><span data-stu-id="8afa3-167">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="8afa3-168">Quando si usa il parametro DomainName, è necessario definire il nome di dominio completo per i record LyncdiscoverInternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="8afa3-168">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="8afa3-169">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8afa3-169">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="8afa3-170">Per assegnare il certificato, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8afa3-170">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="8afa3-171">Dove "identificazione personale" è l'identificazione digitale visualizzata per il certificato appena emesso.</span><span class="sxs-lookup"><span data-stu-id="8afa3-171">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="8afa3-172">Per i nomi alternativi degli argomenti di individuazione automatica degli elementi interni mancanti quando si usano certificati distinti per default, WebServicesInternal e WebServicesExternal, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8afa3-172">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="8afa3-173">Al prompt della riga di comando di Lync Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="8afa3-173">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="8afa3-174">Se si hanno molti domini SIP, non è possibile usare il nuovo parametro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="8afa3-174">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="8afa3-175">Devi invece usare il parametro DomainName.</span><span class="sxs-lookup"><span data-stu-id="8afa3-175">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="8afa3-176">Quando si usa il parametro DomainName, è necessario usare un prefisso appropriato per l'FQDN del dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="8afa3-176">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="8afa3-177">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8afa3-177">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="8afa3-178">Per un nome alternativo dell'oggetto individuazione automatica esterno mancante, nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="8afa3-178">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="8afa3-179">Se si hanno molti domini SIP, non è possibile usare il nuovo parametro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="8afa3-179">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="8afa3-180">Devi invece usare il parametro DomainName.</span><span class="sxs-lookup"><span data-stu-id="8afa3-180">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="8afa3-181">Quando si usa il parametro DomainName, è necessario usare un prefisso appropriato per l'FQDN del dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="8afa3-181">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="8afa3-182">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8afa3-182">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="8afa3-183">Per assegnare i singoli tipi di certificato, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8afa3-183">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="8afa3-184">Dove "identificazione personale" è l'identificazione digitale visualizzata per i singoli certificati appena emessi.</span><span class="sxs-lookup"><span data-stu-id="8afa3-184">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

