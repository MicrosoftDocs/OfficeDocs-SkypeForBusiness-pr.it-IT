---
title: "Lync Server 2013: Verificare o configurare l'autenticazione e la certificazione nelle directory virtuali IIS"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48399ed2a6eba53707218295adcd1cbd11a5e32c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="903f4-102">Verificare o configurare l'autenticazione e la certificazione nelle directory virtuali IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="903f4-102">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="903f4-103">_**Argomento Ultima modifica:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="903f4-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="903f4-104">Usare la procedura seguente per configurare il certificato nelle directory virtuali di Internet Information Services (IIS) oppure verificare che il certificato sia configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="903f4-104">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="903f4-105">Eseguire la procedura seguente in ogni server che esegue IIS nel pool di Lync Server interno e nei server di pool Director o Director facoltativi.</span><span class="sxs-lookup"><span data-stu-id="903f4-105">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="903f4-106">La procedura seguente definisce una procedura per richiedere un certificato combinato usato per tutti gli scopi Lync Server, sito Web interno e sito Web esterno in IIS.</span><span class="sxs-lookup"><span data-stu-id="903f4-106">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="903f4-107">Lync Server 2010 ha introdotto un set di cmdlet di Windows&nbsp;PowerShell per Lync Server Management Shell per l'esplicito scopo di gestire la richiesta di certificato, l'importazione e l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="903f4-107">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="903f4-108">La procedura presuppone che sia presente un'autorità di certificazione (CA) distribuita internamente in grado di elaborare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="903f4-108">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="903f4-109">Se si usano certificati pubblici per scopi di Lync Server o la CA richiede una richiesta offline, vedere la sintassi dettagliata in questo argomento per informazioni sul parametro – output.</span><span class="sxs-lookup"><span data-stu-id="903f4-109">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="903f4-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="903f4-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="903f4-111">Per configurare l'autenticazione e i certificati nelle directory virtuali di IIS</span><span class="sxs-lookup"><span data-stu-id="903f4-111">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="903f4-112">Per completare correttamente le operazioni seguenti, è necessario avere effettuato l'accesso al computer (front end server o Director) in cui sono installati i servizi Web e essere un amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="903f4-112">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="903f4-113">È necessario disporre delle autorizzazioni di **lettura** e **registrazione** per l'autorità di certificazione di cui si richiederanno i certificati, se l'autorità di certificazione è l'autorità di certificazione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="903f4-113">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="903f4-114">Non è necessario disporre delle autorizzazioni per l'autorità di certificazione se si vuole configurare e inviare una richiesta di certificato offline.</span><span class="sxs-lookup"><span data-stu-id="903f4-114">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="903f4-115">Fare clic sul pulsante **Start**, selezionare **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **Gestione Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="903f4-115">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="903f4-116">In **Gestione Internet Information Services (IIS)** selezionare **nomeserver**.</span><span class="sxs-lookup"><span data-stu-id="903f4-116">In **Internet Information Services (IIS) Manager**, select **ServerName**.</span></span> <span data-ttu-id="903f4-117">In **visualizzazione funzionalità**selezionare **certificati server**, fare clic con il pulsante destro del mouse e scegliere **Apri funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="903f4-117">In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="903f4-118">Nella visualizzazione funzionalità certificati server, se sono stati assegnati certificati al server, verranno visualizzati qui.</span><span class="sxs-lookup"><span data-stu-id="903f4-118">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here.</span></span> <span data-ttu-id="903f4-119">Se è presente un certificato che corrisponde ai requisiti per il sito Web esterno in IIS, è possibile riutilizzare tale certificato.</span><span class="sxs-lookup"><span data-stu-id="903f4-119">If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate.</span></span> <span data-ttu-id="903f4-120">Per visualizzare un certificato, fare clic con il pulsante destro del mouse sul certificato e scegliere <STRONG>Visualizza.</STRONG> ..</span><span class="sxs-lookup"><span data-stu-id="903f4-120">To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="903f4-121">Nel server front-end o nel Director di cui si richiede il certificato, fare clic sul pulsante **Start**, selezionare **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="903f4-121">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="903f4-122">In Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="903f4-122">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="903f4-123">L'output è un elenco dei certificati attualmente presenti nel server nell'archivio certificati del computer personale.</span><span class="sxs-lookup"><span data-stu-id="903f4-123">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store.</span></span> <span data-ttu-id="903f4-124">Tieni presente che nel certificato combinato (ovvero in cui i servizi Web predefiniti interni e Web Services esterni usano lo stesso certificato) vedrai che la proprietà Use verrà popolata con default, WebServicesInternal e WebServicesExternal.</span><span class="sxs-lookup"><span data-stu-id="903f4-124">Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal.</span></span> <span data-ttu-id="903f4-125">La proprietà identificazione personale sarà inoltre uguale per ogni tipo di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="903f4-125">Also, the Thumbprint property will be the same for each of the Use types.</span></span> <span data-ttu-id="903f4-126">In questo esempio viene illustrato un output di esempio di Get-CsCertificate:</span><span class="sxs-lookup"><span data-stu-id="903f4-126">An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="903f4-127">![Informazioni Get-CsCertificate sullo stato del certificato corrente](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Informazioni Get-CsCertificate sullo stato del certificato corrente")</span><span class="sxs-lookup"><span data-stu-id="903f4-127">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="903f4-128">In Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="903f4-128">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="903f4-129">In cui il comando completo verrà visualizzato come esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="903f4-129">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="903f4-130">Per impostazione predefinita, Request-CsCertificate compilerà il nome del soggetto con il nome del server o del pool e compilerà le voci nel nome dell'oggetto alternativo con l'FQDN del server, il FQDN del pool, gli FQDN degli URL semplici e gli FQDN dei servizi Web interni ed esterni.</span><span class="sxs-lookup"><span data-stu-id="903f4-130">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs.</span></span> <span data-ttu-id="903f4-131">A questo scopo, fai riferimento al documento della topologia nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="903f4-131">It does this by referencing to the topology document in your deployment.</span></span> <span data-ttu-id="903f4-132">Se è presente un valore mancante ed è stato specificato il parametro – Verbose, si riceverà una notifica che i valori calcolati e effettivi per i nomi alternativi sono diversi, ma non informa i valori mancanti.</span><span class="sxs-lookup"><span data-stu-id="903f4-132">If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing.</span></span> <span data-ttu-id="903f4-133">Fornisce l'intero valore calcolato a cui fa riferimento il cmdlet.</span><span class="sxs-lookup"><span data-stu-id="903f4-133">It does supply you with the entire computed value that the cmdlet references.</span></span> <span data-ttu-id="903f4-134">Usare la stringa di nomi alternativi calcolati nell'output per richiedere nuovamente un nuovo certificato che includa tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="903f4-134">Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="903f4-135">![Output della richiesta di certificato tramite Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output della richiesta di certificato tramite Request-CsCertifica")</span><span class="sxs-lookup"><span data-stu-id="903f4-135">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="903f4-136">In Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="903f4-136">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="903f4-137">In cui il comando completo verrà visualizzato come esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="903f4-137">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="903f4-138">L'output del cmdlet Set-CsCertificate mostrerà che viene assegnato lo stesso certificato (identificato dall'identificazione personale del certificato) per l'utilizzo predefinito, WebServicesExternal e WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="903f4-138">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="903f4-139">![Output di Set-CsCertificate su IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output di Set-CsCertificate su IIS WebExt")</span><span class="sxs-lookup"><span data-stu-id="903f4-139">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="903f4-140">Per verificare o configurare l'autenticazione e i certificati nelle directory virtuali di IIS</span><span class="sxs-lookup"><span data-stu-id="903f4-140">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="903f4-141">Fare clic sul pulsante **Start**, selezionare **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **Gestione Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="903f4-141">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="903f4-142">In **Gestione Internet Information Services (IIS)** espandere **nomeserver**e quindi espandere **siti**.</span><span class="sxs-lookup"><span data-stu-id="903f4-142">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="903f4-143">Fare clic con il pulsante destro del mouse su **sito Web esterno di Lync Server**e quindi scegliere **Modifica binding**</span><span class="sxs-lookup"><span data-stu-id="903f4-143">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="903f4-144">Verificare che HTTPS sia associato alla porta 4443 e quindi fare clic su **https**.</span><span class="sxs-lookup"><span data-stu-id="903f4-144">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="903f4-145">Selezionare la voce HTTPS, fare clic su **modifica**e quindi verificare che Lync Server WebServicesExternalCertificate sia associato al protocollo.</span><span class="sxs-lookup"><span data-stu-id="903f4-145">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="903f4-146">Confrontare l'identificazione personale del cmdlet Set-CsCertificate per assicurarsi che il certificato previsto sia associato correttamente al binding HTTPS.</span><span class="sxs-lookup"><span data-stu-id="903f4-146">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="903f4-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="903f4-147">See Also</span></span>


[<span data-ttu-id="903f4-148">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="903f4-148">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="903f4-149">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="903f4-149">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

