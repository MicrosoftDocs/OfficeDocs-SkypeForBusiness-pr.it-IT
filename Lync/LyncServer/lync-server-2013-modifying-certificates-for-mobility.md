---
title: 'Lync Server 2013: modifica dei certificati per i dispositivi mobili'
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
ms.openlocfilehash: f64676494916bf2c2bd71399bbdd04642da50cee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="97196-102">Modifica dei certificati per i dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97196-102">Modifying certificates for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97196-103">_**Ultimo argomento modificato:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="97196-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="97196-104">Per supportare connessioni sicure tra l'ambiente Lync e i client mobili, i certificati SSL (Secure Socket Layer) per il pool di server Director, il pool Front end e il proxy inverso devono essere aggiornati con qualche altro nome alternativo del soggetto ( SAN).</span><span class="sxs-lookup"><span data-stu-id="97196-104">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="97196-105">Se è necessario estrarre ulteriori informazioni sui requisiti dei certificati per i dispositivi mobili, vedere la sezione requisiti dei certificati in [requisiti tecnici per i dispositivi mobili in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), ma in pratica è necessario ottenere nuovi certificati dall'autorità di certificazione con le voci di San aggiuntive incluse e quindi aggiungere tali certificati utilizzando i passaggi di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="97196-105">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="97196-106">Naturalmente, prima di iniziare, è consigliabile sapere quali nomi alternativi del soggetto sono già presenti nei certificati.</span><span class="sxs-lookup"><span data-stu-id="97196-106">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="97196-107">Se non si è sicuri di cosa è già stato configurato, è possibile scoprirlo in molti modi. Mentre l'opzione è disponibile per l'esecuzione dei comandi **Get-CsCertificate** e di altri PowerShell per visualizzare queste informazioni, (che è possibile esaminare in basso) per impostazione predefinita, i dati verranno troncati, pertanto potrebbe non essere possibile visualizzare tutte le proprietà necessarie.</span><span class="sxs-lookup"><span data-stu-id="97196-107">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="97196-108">Per ottenere un buon aspetto del certificato e di tutte le relative proprietà, è possibile accedere a Microsoft Management Console (MMC) e caricare lo snap-in certificati (che è anche possibile esaminare in basso) oppure è sufficiente archiviare la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="97196-108">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="97196-109">Come indicato in questo esempio, la procedura seguente consente di eseguire l'aggiornamento dei certificati mediante Lync Server Management Shell e MMC.</span><span class="sxs-lookup"><span data-stu-id="97196-109">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="97196-110">Se si è interessati all'utilizzo della procedura guidata di certificazione nella distribuzione guidata di Lync Server, è possibile controllare la [configurazione dei certificati per il Director in Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) out per il Director o il pool di Director, se ne è stata configurata una (potrebbe non essere possibile).</span><span class="sxs-lookup"><span data-stu-id="97196-110">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="97196-111">Per il front end server o il pool Front End, è necessario vedere [Configure Certificates for Servers in Lync server 2013](lync-server-2013-configure-certificates-for-servers.md).</span><span class="sxs-lookup"><span data-stu-id="97196-111">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="97196-112">Un'ultima cosa da tenere in considerazione consiste nel fatto che è possibile disporre di un singolo certificato predefinito nell'ambiente Lync Server 2013 oppure che si disponga di certificati distinti per il valore predefinito (ovvero tutto tranne che per i servizi Web), WebServicesExternal e WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="97196-112">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="97196-113">Qualunque sia la configurazione, questi passaggi dovrebbero risultare utili.</span><span class="sxs-lookup"><span data-stu-id="97196-113">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="97196-114">Per aggiornare i certificati con i nuovi nomi alternativi del soggetto mediante Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="97196-114">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="97196-115">È necessario eseguire l'accesso al server Lync Server 2013 utilizzando un account che disponga dei diritti e delle autorizzazioni di amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="97196-115">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="97196-116">Inoltre, se si esegue la richiesta di PowerShell **-CsCertificate** nei passaggi 12 e oltre, l'account deve disporre dei diritti per l'autorità di certificazione (CA) specificata.</span><span class="sxs-lookup"><span data-stu-id="97196-116">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="97196-117">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="97196-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="97196-118">Prima di poter assegnare un certificato aggiornato, è necessario scoprire quali certificati sono stati assegnati al server e per quale tipo di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="97196-118">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="97196-119">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="97196-119">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="97196-120">Esaminare l'output del passaggio precedente per verificare se è stato assegnato un singolo certificato per più utilizzi o se è stato assegnato un certificato diverso per ogni utilizzo.</span><span class="sxs-lookup"><span data-stu-id="97196-120">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="97196-121">Esaminare il parametro Use per individuare il modo in cui viene utilizzato un certificato.</span><span class="sxs-lookup"><span data-stu-id="97196-121">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="97196-122">Confrontare il parametro identificazione personale per i certificati visualizzati per vedere se lo stesso certificato dispone di più utilizzi.</span><span class="sxs-lookup"><span data-stu-id="97196-122">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="97196-123">Tenere d'occhio il parametro identificazione personale.</span><span class="sxs-lookup"><span data-stu-id="97196-123">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="97196-124">Aggiornare il certificato.</span><span class="sxs-lookup"><span data-stu-id="97196-124">Update the certificate.</span></span> <span data-ttu-id="97196-125">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="97196-125">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="97196-126">Ad esempio, se il cmdlet **Get-CsCertificate** ha visualizzato un certificato con l'utilizzo di default, un altro con un utilizzo di WebServicesInternal e un altro con un utilizzo di WebServicesExternal e tutti avevano lo stesso valore di identificazione personale, nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="97196-126">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="97196-127">**Importante:**</span><span class="sxs-lookup"><span data-stu-id="97196-127">**Important:**</span></span>
    
    <span data-ttu-id="97196-128">Se per ogni utilizzo viene assegnato un certificato distinto, in modo che il valore di identificazione personale controllato in alto sia diverso per ogni certificato, è importante che **non** venga eseguito il cmdlet **Set-CsCertificate** con più tipi, come nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="97196-128">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="97196-129">In questo caso, eseguire il cmdlet **Set-CsCertificate** separatamente per ogni utilizzo.</span><span class="sxs-lookup"><span data-stu-id="97196-129">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="97196-130">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="97196-130">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="97196-131">Per visualizzare il certificato (o i certificati), fare clic sul pulsante **Start**, scegliere **Esegui...**.</span><span class="sxs-lookup"><span data-stu-id="97196-131">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="97196-132">Digitare MMC per aprire Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="97196-132">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="97196-133">Scegliere **file**dal menu MMC, selezionare **Aggiungi/Rimuovi snap-in...**, selezionare certificati.</span><span class="sxs-lookup"><span data-stu-id="97196-133">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="97196-134">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="97196-134">Click **Add**.</span></span> <span data-ttu-id="97196-135">Quando richiesto, selezionare **account computer**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="97196-135">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="97196-136">Se si tratta del server in cui si trova il certificato, selezionare **computer locale**.</span><span class="sxs-lookup"><span data-stu-id="97196-136">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="97196-137">Se il certificato è posizionato in un altro computer, è necessario selezionare **un altro computer**, quindi è possibile digitare il nome di dominio completo del computer oppure fare clic su **Sfoglia** in **immettere il nome dell'oggetto da selezionare**e digitare il nome del computer.</span><span class="sxs-lookup"><span data-stu-id="97196-137">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="97196-138">Fare clic su **Controlla nomi**.</span><span class="sxs-lookup"><span data-stu-id="97196-138">Click **Check Names**.</span></span> <span data-ttu-id="97196-139">Quando il nome del computer viene risolto, verrà sottolineato.</span><span class="sxs-lookup"><span data-stu-id="97196-139">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="97196-140">Fare clic su **OK**, quindi su **fine**.</span><span class="sxs-lookup"><span data-stu-id="97196-140">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="97196-141">Fare clic su **OK** per eseguire il commit della selezione e chiudere la finestra di dialogo **Aggiungi o Rimuovi snap-** in.</span><span class="sxs-lookup"><span data-stu-id="97196-141">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="97196-142">Per visualizzare le proprietà del certificato, espandere **certificati**, espandere **personale**e selezionare **certificati**.</span><span class="sxs-lookup"><span data-stu-id="97196-142">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="97196-143">Selezionare il certificato da visualizzare, fare clic con il pulsante destro del mouse sul certificato e scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="97196-143">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="97196-144">Nella visualizzazione **certificato** selezionare **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="97196-144">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="97196-145">Da qui, è possibile selezionare il nome del soggetto del certificato selezionando **oggetto** e vengono visualizzati il nome del soggetto assegnato e le proprietà associate.</span><span class="sxs-lookup"><span data-stu-id="97196-145">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="97196-146">Per visualizzare i nomi alternativi del soggetto assegnati, selezionare **nome alternativo soggetto**.</span><span class="sxs-lookup"><span data-stu-id="97196-146">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="97196-147">Vengono visualizzati tutti i nomi alternativi del soggetto assegnati.</span><span class="sxs-lookup"><span data-stu-id="97196-147">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="97196-148">Per impostazione predefinita, i nomi alternativi del soggetto trovati qui sono di tipo **DNS Name** .</span><span class="sxs-lookup"><span data-stu-id="97196-148">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="97196-149">Verranno visualizzati i membri seguenti (tutti i nomi di dominio completi rappresentati nei record host DNS (A o, se IPv6 AAAA):</span><span class="sxs-lookup"><span data-stu-id="97196-149">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="97196-150">Nome del pool per il pool o il nome del server singolo se non si tratta di un pool</span><span class="sxs-lookup"><span data-stu-id="97196-150">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="97196-151">Nome del server a cui è assegnato il certificato</span><span class="sxs-lookup"><span data-stu-id="97196-151">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="97196-152">Simple URL Records, in genere Meet e dialin</span><span class="sxs-lookup"><span data-stu-id="97196-152">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="97196-153">Servizi Web interni e nomi esterni dei servizi Web (ad esempio, webpool01.contoso.net, webpool01.contoso.com), in base alle scelte effettuate in Generatore di topologie e le selezioni dei servizi Web in corso.</span><span class="sxs-lookup"><span data-stu-id="97196-153">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="97196-154">Se è già stato assegnato, il lyncdiscover. \<SipDomain\> e lyncdiscoverinternal. \<record\> di SipDomain.</span><span class="sxs-lookup"><span data-stu-id="97196-154">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="97196-155">L'ultimo elemento è quello che più ti interessa: se c'è una voce di Lyncdiscover e lyncdiscoverinternal SAN.</span><span class="sxs-lookup"><span data-stu-id="97196-155">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="97196-156">Ripetere questi passaggi se si dispone di più certificati da controllare.</span><span class="sxs-lookup"><span data-stu-id="97196-156">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="97196-157">Dopo aver apportato queste informazioni, è possibile chiudere la visualizzazione certificati e MMC.</span><span class="sxs-lookup"><span data-stu-id="97196-157">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="97196-158">Se non è presente un nome alternativo del soggetto del servizio di individuazione automatica e si utilizza un singolo certificato predefinito per i tipi default, WebServicesInternal e WebServiceExternal, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="97196-158">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="97196-159">Al prompt dei comandi della riga di comando di Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="97196-159">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="97196-160">Se si dispone di molti domini SIP, non è possibile utilizzare il nuovo parametro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="97196-160">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="97196-161">Al contrario, è necessario utilizzare il parametro DomainName.</span><span class="sxs-lookup"><span data-stu-id="97196-161">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="97196-162">Quando si utilizza il parametro DomainName, è necessario definire il nome di dominio completo per i record LyncdiscoverInternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="97196-162">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="97196-163">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="97196-163">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="97196-164">Per assegnare il certificato, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="97196-164">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="97196-165">Dove "identificazione personale" è l'identificazione digitale visualizzata per il certificato appena emesso.</span><span class="sxs-lookup"><span data-stu-id="97196-165">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="97196-166">Per una rete SAN di individuazione automatica mancante quando si utilizzano certificati distinti per default, WebServicesInternal e WebServicesExternal, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="97196-166">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="97196-167">Al prompt dei comandi della riga di comando di Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="97196-167">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="97196-168">Se si dispone di molti domini SIP, non è possibile utilizzare il nuovo parametro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="97196-168">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="97196-169">Al contrario, è necessario utilizzare il parametro DomainName.</span><span class="sxs-lookup"><span data-stu-id="97196-169">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="97196-170">Quando si utilizza il parametro DomainName, è necessario utilizzare un prefisso appropriato per il nome FQDN del dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="97196-170">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="97196-171">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="97196-171">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="97196-172">Per un nome alternativo del soggetto di individuazione automatica esterno mancante, nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="97196-172">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="97196-173">Se si dispone di molti domini SIP, non è possibile utilizzare il nuovo parametro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="97196-173">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="97196-174">Al contrario, è necessario utilizzare il parametro DomainName.</span><span class="sxs-lookup"><span data-stu-id="97196-174">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="97196-175">Quando si utilizza il parametro DomainName, è necessario utilizzare un prefisso appropriato per il nome FQDN del dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="97196-175">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="97196-176">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="97196-176">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="97196-177">Per assegnare i singoli tipi di certificato, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="97196-177">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="97196-178">Dove "identificazione personale" è l'identificazione digitale visualizzata per i singoli certificati appena emessi.</span><span class="sxs-lookup"><span data-stu-id="97196-178">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="97196-179">Solo per tenere presente che i passaggi 12 e 13 devono essere eseguiti solo se l'account che esegue tali operazioni ha accesso all'autorità di certificazione con le autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="97196-179">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="97196-180">Se non si è in grado di eseguire l'accesso con un account che dispone di tali autorizzazioni o se si utilizza un'autorità di certificazione pubblica o remota per i certificati, è necessario richiederli tramite la distribuzione guidata di Lync Server, che è stata toccata nella parte superiore della articolo.</span><span class="sxs-lookup"><span data-stu-id="97196-180">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

