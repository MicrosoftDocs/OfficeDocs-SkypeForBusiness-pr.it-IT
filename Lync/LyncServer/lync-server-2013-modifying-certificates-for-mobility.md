---
title: 'Lync Server 2013: Modifica dei certificati per i dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 150dc8c7b4021e1e2c7ccab6ccc71823c01c388e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="a6423-102">Modifica dei certificati per i dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6423-102">Modifying certificates for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6423-103">_**Argomento Ultima modifica:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="a6423-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="a6423-104">Per supportare connessioni sicure tra l'ambiente Lync e i client mobili, i certificati SSL (Secure Socket Layer) per il pool di Director, il pool Front end e il proxy inverso devono essere aggiornati con un altro nome alternativo soggetto ( SAN).</span><span class="sxs-lookup"><span data-stu-id="a6423-104">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="a6423-105">Per altre informazioni sui requisiti di certificato per la mobilità, vedere la sezione requisiti dei certificati nei [requisiti tecnici per la mobilità in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), ma in pratica è necessario ottenere nuovi certificati dall'autorità di certificazione con le altre voci di San incluse e quindi aggiungere questi certificati usando i passaggi di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a6423-105">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="a6423-106">Naturalmente, prima di iniziare, in genere è consigliabile conoscere i nomi alternativi del soggetto che i certificati hanno già.</span><span class="sxs-lookup"><span data-stu-id="a6423-106">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="a6423-107">Se non si è sicuri di cosa è già stato configurato, è possibile scoprirlo in molti modi. Mentre l'opzione è disponibile per eseguire il comando **Get-CsCertificate** e altri comandi di PowerShell per visualizzare queste informazioni, (che percorriamo di seguito) per impostazione predefinita, i dati verranno troncati, quindi potrebbe non essere possibile visualizzare tutte le proprietà necessarie.</span><span class="sxs-lookup"><span data-stu-id="a6423-107">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="a6423-108">Per ottenere una buona occhiata al certificato e a tutte le sue proprietà, è possibile passare a Microsoft Management Console (MMC) e caricare lo snap-in certificati (che si può anche seguire) oppure è sufficiente archiviare la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a6423-108">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="a6423-109">Come indicato in precedenza, la procedura seguente consente di eseguire l'aggiornamento dei certificati tramite Lync Server Management Shell e MMC.</span><span class="sxs-lookup"><span data-stu-id="a6423-109">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="a6423-110">Se si è interessati all'uso della procedura guidata certificati nella distribuzione guidata di Lync Server, è possibile selezionare la casella di controllo [Configura i certificati per il Director in Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) per il pool di Director o Director, se ne è stato configurato uno (non è possibile).</span><span class="sxs-lookup"><span data-stu-id="a6423-110">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="a6423-111">Per il server front-end o per il pool Front-End, è consigliabile vedere [configurare i certificati per i server in Lync server 2013](lync-server-2013-configure-certificates-for-servers.md).</span><span class="sxs-lookup"><span data-stu-id="a6423-111">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="a6423-112">Un'ultima cosa da ricordare è che potresti avere un singolo certificato predefinito nell'ambiente Lync Server 2013 oppure puoi avere certificati distinti per impostazione predefinita (che è tutto tranne i servizi Web), WebServicesExternal e WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="a6423-112">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="a6423-113">Qualunque sia la configurazione, questi passaggi dovrebbero essere utili.</span><span class="sxs-lookup"><span data-stu-id="a6423-113">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="a6423-114">Per aggiornare i certificati con i nuovi nomi alternativi del soggetto tramite Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a6423-114">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="a6423-115">È necessario accedere al server Lync Server 2013 usando un account che disponga dei diritti e delle autorizzazioni di amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="a6423-115">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="a6423-116">Inoltre, se si sta usando la richiesta di PowerShell **-CsCertificate** nei passaggi 12 e oltre, l'account deve avere diritti per l'autorità di certificazione (CA) specificata.</span><span class="sxs-lookup"><span data-stu-id="a6423-116">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="a6423-117">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a6423-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a6423-118">Per poter assegnare un certificato aggiornato, è necessario verificare quali certificati sono stati assegnati al server e per quale tipo di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="a6423-118">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="a6423-119">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="a6423-119">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="a6423-120">Esaminare l'output del passaggio precedente per verificare se un singolo certificato è stato assegnato per più usi o se è stato assegnato un certificato diverso per ogni utilizzo.</span><span class="sxs-lookup"><span data-stu-id="a6423-120">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="a6423-121">Cerca nel parametro Use per scoprire in che modo viene usato un certificato.</span><span class="sxs-lookup"><span data-stu-id="a6423-121">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="a6423-122">Confrontare il parametro identificazione personale per i certificati visualizzati per verificare se lo stesso certificato ha più usi.</span><span class="sxs-lookup"><span data-stu-id="a6423-122">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="a6423-123">Tieni d'occhio il parametro identificazione personale.</span><span class="sxs-lookup"><span data-stu-id="a6423-123">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="a6423-124">Aggiornare il certificato.</span><span class="sxs-lookup"><span data-stu-id="a6423-124">Update the certificate.</span></span> <span data-ttu-id="a6423-125">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="a6423-125">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="a6423-126">Ad esempio, se il cmdlet **Get-CsCertificate** Visualizza un certificato con l'uso di default, un altro con l'uso di WebServicesInternal e un altro con l'uso di WebServicesExternal e tutti avevano lo stesso valore di identificazione personale, nella riga di comando devi digitare:</span><span class="sxs-lookup"><span data-stu-id="a6423-126">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="a6423-127">**Importante:**</span><span class="sxs-lookup"><span data-stu-id="a6423-127">**Important:**</span></span>
    
    <span data-ttu-id="a6423-128">Se per ogni uso viene assegnato un certificato distinto (in modo che il valore di identificazione personale selezionato in precedenza sia diverso per ogni certificato), è fondamentale **non** eseguire il cmdlet **Set-CsCertificate** con più tipi, come nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="a6423-128">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="a6423-129">In questo caso, eseguire il cmdlet **Set-CsCertificate** separatamente per ogni utilizzo.</span><span class="sxs-lookup"><span data-stu-id="a6423-129">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="a6423-130">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a6423-130">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="a6423-131">Per visualizzare il certificato (o i certificati), fare clic sul pulsante **Start**, scegliere **Esegui...**.</span><span class="sxs-lookup"><span data-stu-id="a6423-131">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="a6423-132">Digitare MMC per aprire Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="a6423-132">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="a6423-133">Nel menu MMC selezionare **file**, selezionare **Aggiungi/Rimuovi snap-in...**, selezionare certificati.</span><span class="sxs-lookup"><span data-stu-id="a6423-133">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="a6423-134">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a6423-134">Click **Add**.</span></span> <span data-ttu-id="a6423-135">Quando richiesto, selezionare **account computer**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a6423-135">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="a6423-136">Se si tratta del server in cui si trova il certificato, selezionare **computer locale**.</span><span class="sxs-lookup"><span data-stu-id="a6423-136">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="a6423-137">Se il certificato si trova in un altro computer, è necessario selezionare **un altro computer**, quindi è possibile digitare il nome di dominio completo del computer oppure fare clic su **Sfoglia** in **immettere il nome dell'oggetto da selezionare**e digitare il nome del computer.</span><span class="sxs-lookup"><span data-stu-id="a6423-137">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="a6423-138">Fare clic su **Controlla nomi**.</span><span class="sxs-lookup"><span data-stu-id="a6423-138">Click **Check Names**.</span></span> <span data-ttu-id="a6423-139">Quando il nome del computer viene risolto, sarà sottolineato.</span><span class="sxs-lookup"><span data-stu-id="a6423-139">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="a6423-140">Fare clic su **OK**e quindi su **fine**.</span><span class="sxs-lookup"><span data-stu-id="a6423-140">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="a6423-141">Fare clic su **OK** per confermare la selezione e chiudere la finestra di dialogo **Aggiungi o Rimuovi snap-** in.</span><span class="sxs-lookup"><span data-stu-id="a6423-141">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="a6423-142">Per visualizzare le proprietà del certificato, espandere **certificati**, espandere **personale**e selezionare **certificati**.</span><span class="sxs-lookup"><span data-stu-id="a6423-142">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="a6423-143">Selezionare il certificato da visualizzare, fare clic con il pulsante destro del mouse sul certificato e scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="a6423-143">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="a6423-144">Nella visualizzazione **certificato** selezionare **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="a6423-144">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="a6423-145">Da qui è possibile selezionare il nome del soggetto del certificato selezionando **oggetto** e il nome del soggetto assegnato e le proprietà associate verranno visualizzate.</span><span class="sxs-lookup"><span data-stu-id="a6423-145">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="a6423-146">Per visualizzare i nomi alternativi oggetto assegnati, selezionare **nome alternativo soggetto**.</span><span class="sxs-lookup"><span data-stu-id="a6423-146">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="a6423-147">Vengono visualizzati tutti i nomi alternativi assegnati al soggetto.</span><span class="sxs-lookup"><span data-stu-id="a6423-147">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="a6423-148">I nomi alternativi oggetto trovati qui sono di tipo **DNS Name** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a6423-148">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="a6423-149">Dovrebbero essere visualizzati i membri seguenti (che dovrebbero essere tutti nomi di dominio completi rappresentati nei record host DNS (A o, se IPv6 AAAA):</span><span class="sxs-lookup"><span data-stu-id="a6423-149">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="a6423-150">Nome del pool per il pool o nome del server singolo se non si tratta di un pool</span><span class="sxs-lookup"><span data-stu-id="a6423-150">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="a6423-151">Nome del server a cui è assegnato il certificato</span><span class="sxs-lookup"><span data-stu-id="a6423-151">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="a6423-152">Record URL semplici, in genere incontra e componi</span><span class="sxs-lookup"><span data-stu-id="a6423-152">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="a6423-153">Servizi Web Internal e Web Services External names (ad esempio, webpool01.contoso.net, webpool01.contoso.com), in base alle scelte effettuate in Generatore di topologia e alle selezioni di servizi Web sovrascritte.</span><span class="sxs-lookup"><span data-stu-id="a6423-153">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="a6423-154">Se è già stata assegnata, Lyncdiscover. \<SipDomain\> e lyncdiscoverinternal. \<record\> di SipDomain.</span><span class="sxs-lookup"><span data-stu-id="a6423-154">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="a6423-155">L'ultimo elemento è quello che ti interessa di più: se c'è una voce di SAN Lyncdiscover e lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="a6423-155">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="a6423-156">Ripetere questi passaggi se si hanno più certificati da controllare.</span><span class="sxs-lookup"><span data-stu-id="a6423-156">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="a6423-157">Dopo aver ottenuto queste informazioni, è possibile chiudere la visualizzazione certificato e la console MMC.</span><span class="sxs-lookup"><span data-stu-id="a6423-157">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="a6423-158">Se non è presente un nome alternativo dell'oggetto del servizio di individuazione automatica e si usa un singolo certificato predefinito per i tipi default, WebServicesInternal e WebServiceExternal, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6423-158">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="a6423-159">Al prompt della riga di comando di Lync Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="a6423-159">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="a6423-160">Se si hanno molti domini SIP, non è possibile usare il nuovo parametro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="a6423-160">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="a6423-161">Devi invece usare il parametro DomainName.</span><span class="sxs-lookup"><span data-stu-id="a6423-161">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="a6423-162">Quando si usa il parametro DomainName, è necessario definire il nome di dominio completo per i record LyncdiscoverInternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="a6423-162">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="a6423-163">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a6423-163">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="a6423-164">Per assegnare il certificato, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a6423-164">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="a6423-165">Dove "identificazione personale" è l'identificazione digitale visualizzata per il certificato appena emesso.</span><span class="sxs-lookup"><span data-stu-id="a6423-165">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="a6423-166">Per una SAN automatica interna mancante quando si usano certificati distinti per default, WebServicesInternal e WebServicesExternal, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6423-166">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="a6423-167">Al prompt della riga di comando di Lync Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="a6423-167">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="a6423-168">Se si hanno molti domini SIP, non è possibile usare il nuovo parametro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="a6423-168">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="a6423-169">Devi invece usare il parametro DomainName.</span><span class="sxs-lookup"><span data-stu-id="a6423-169">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="a6423-170">Quando usi il parametro DomainName, devi usare un prefisso appropriato per l'FQDN del dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="a6423-170">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="a6423-171">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a6423-171">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="a6423-172">Per un nome alternativo dell'oggetto individuazione automatica esterno mancante, nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="a6423-172">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="a6423-173">Se si hanno molti domini SIP, non è possibile usare il nuovo parametro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="a6423-173">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="a6423-174">Devi invece usare il parametro DomainName.</span><span class="sxs-lookup"><span data-stu-id="a6423-174">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="a6423-175">Quando usi il parametro DomainName, devi usare un prefisso appropriato per l'FQDN del dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="a6423-175">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="a6423-176">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a6423-176">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="a6423-177">Per assegnare i singoli tipi di certificato, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a6423-177">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="a6423-178">Dove "identificazione personale" è l'identificazione digitale visualizzata per i singoli certificati appena emessi.</span><span class="sxs-lookup"><span data-stu-id="a6423-178">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6423-179">Solo per notare che i passaggi 12 e 13 devono essere eseguiti solo se l'account che li esegue può accedere all'autorità di certificazione con le autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="a6423-179">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="a6423-180">Se non si riesce ad accedere con un account che contiene tali autorizzazioni o se si usa un'autorità di certificazione pubblica o remota per i certificati, è necessario richiederli tramite la distribuzione guidata di Lync Server, che è stata toccata nella parte superiore della articolo.</span><span class="sxs-lookup"><span data-stu-id="a6423-180">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

