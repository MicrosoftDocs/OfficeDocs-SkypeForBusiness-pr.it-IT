---
title: "Lync Server 2013: verificare o configurare l'autenticazione e la certificazione nelle directory virtuali di IIS"
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
ms.openlocfilehash: ca51a3c597be40c679a7b131f87775876a63811d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="88402-102">Verificare o configurare l'autenticazione e la certificazione nelle directory virtuali di IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88402-102">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88402-103">_**Ultimo argomento modificato:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="88402-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="88402-104">Utilizzare la procedura seguente per configurare il certificato nelle directory virtuali di Internet Information Services (IIS) o verificare che il certificato sia configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="88402-104">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="88402-105">Eseguire la procedura seguente in ogni server che esegue IIS nel pool interno di Lync Server e nei server del pool Director o Director opzionali.</span><span class="sxs-lookup"><span data-stu-id="88402-105">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88402-106">La procedura seguente consente di definire una procedura per richiedere un certificato combinato utilizzato per tutti gli scopi Lync Server, il sito Web interno e il sito Web esterno in IIS.</span><span class="sxs-lookup"><span data-stu-id="88402-106">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="88402-107">Lync Server 2010 ha introdotto un set di cmdlet di Windows&nbsp;PowerShell di Lync Server Management Shell per lo scopo esplicito di gestire la richiesta di certificato, l'importazione e l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="88402-107">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="88402-108">La procedura parte dal presupposto che ci sia un'Autorità di certificazione (CA) distribuita internamente in grado di elaborare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="88402-108">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="88402-109">Se si utilizzano certificati pubblici per gli scopi di Lync Server o la CA richiede una richiesta offline, vedere la sintassi dettagliata in questo argomento per informazioni sul parametro – output.</span><span class="sxs-lookup"><span data-stu-id="88402-109">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="88402-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="88402-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="88402-111">Per configurare l'autenticazione e i certificati nelle directory virtuali di IIS</span><span class="sxs-lookup"><span data-stu-id="88402-111">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="88402-112">Per eseguire correttamente le operazioni seguenti, è necessario essere connessi al computer (front end server o Director) in cui sono installati i servizi Web e essere un amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="88402-112">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="88402-113">È necessario disporre delle autorizzazioni di **lettura** e **iscrizione** per l'Autorità di certificazione a cui verranno richiesti i certificati, se l'autorità di certificazione è quella dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="88402-113">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="88402-114">Non sono necessarie autorizzazioni per l'Autorità di certificazione se si intende configurare e inviare una richiesta di certificato offline.</span><span class="sxs-lookup"><span data-stu-id="88402-114">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="88402-115">Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **Gestione Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="88402-115">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="88402-p104">In **Gestione Internet Information Services (IIS)** selezionare **NomeServer**. In **Visualizzazione funzionalità** selezionare **Certificati server**, fare clic con il pulsante destro del mouse e scegliere **Apri funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="88402-p104">In **Internet Information Services (IIS) Manager**, select **ServerName**. In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="88402-p105">Eventuali certificati assegnati al server appariranno nella visualizzazione delle funzionalità dei certificati server. Se un certificato corrisponde ai requisiti del sito Web esterno in IIS, è possibile riutilizzarlo. Per visualizzare un certificato, fare clic con il pulsante destro del mouse su di esso e scegliere <STRONG>Visualizza</STRONG></span><span class="sxs-lookup"><span data-stu-id="88402-p105">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here. If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate. To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="88402-121">Nel server front-end o nel Director che si desidera richiedere il certificato, fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="88402-121">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="88402-122">In Lync Server Management Shell, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="88402-122">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="88402-p106">L'output è dato da un elenco dei certificati attualmente presenti nel server nell'archivio certificati personali del computer. Si noti che nel caso di un certificato combinato, in cui i servizi Web interni ed esterni predefiniti utilizzano lo stesso certificato, il valore della proprietà Use sarà Default, WebServicesInternal e WebServicesExternal. Inoltre, la proprietà Thumbprint sarà uguale per ogni tipo di Use. Di seguito viene mostrato un output di esempio per Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="88402-p106">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store. Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal. Also, the Thumbprint property will be the same for each of the Use types. An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="88402-127">![Get-CsCertificate info sullo stato SCERT corrente](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info sullo stato SCERT corrente")</span><span class="sxs-lookup"><span data-stu-id="88402-127">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="88402-128">In Lync Server Management Shell, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="88402-128">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="88402-129">Dove il comando completo sarà simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="88402-129">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="88402-p107">Per impostazione predefinita, Request-CsCertificate inserirà nel nome soggetto il nome del server o del pool e nelle voci del nome soggetto alternativo gli FQDN del server, del pool, degli URL semplici e dei servizi Web interni ed esterni facendo riferimento al documento relativo alla topologia presente nella distribuzione. Se si specifica il parametro –Verbose nel caso di un valore mancante, l'utente verrà informato che i valori calcolati ed effettivi dei nomi alternativi sono diversi, ma non di quali siano i valori mancanti. All'utente viene fornito il valore intero calcolato cui fa riferimento il cmdlet. Utilizzare la stringa dei nomi alternativi calcolati nell'output per richiedere un nuovo certificato che includa tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="88402-p107">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs. It does this by referencing to the topology document in your deployment. If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing. It does supply you with the entire computed value that the cmdlet references. Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="88402-135">![Output dalla richiesta CERT tramite Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output dalla richiesta CERT tramite Request-CsCertifica")</span><span class="sxs-lookup"><span data-stu-id="88402-135">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="88402-136">In Lync Server Management Shell, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="88402-136">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="88402-137">Dove il comando completo sarà simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="88402-137">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="88402-138">L'output del cmdlet Set-CsCertificate mostrerà che lo stesso certificato (con identificazione digitale) viene assegnato per l'utilizzo di Default, WebServicesExternal e WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="88402-138">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="88402-139">![Output da Set-CsCertificate in IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output da Set-CsCertificate in IIS WebExt")</span><span class="sxs-lookup"><span data-stu-id="88402-139">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="88402-140">Per verificare o configurare l'autenticazione e i certificati nelle directory virtuali di IIS</span><span class="sxs-lookup"><span data-stu-id="88402-140">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="88402-141">Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **Gestione Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="88402-141">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="88402-142">In **Gestione Internet Information Services (IIS)** espandere **nomeserver**e quindi espandere **siti**.</span><span class="sxs-lookup"><span data-stu-id="88402-142">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="88402-143">Fare clic con il pulsante destro del mouse su **Lync Server External Web Site** e quindi scegliere **Modifica binding**.</span><span class="sxs-lookup"><span data-stu-id="88402-143">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="88402-144">Verificare che https sia associato alla porta 4443 e quindi fare clic su **https**.</span><span class="sxs-lookup"><span data-stu-id="88402-144">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="88402-145">Selezionare la voce HTTPS, fare clic su **modifica**e quindi verificare che Lync Server WebServicesExternalCertificate sia associato a questo protocollo.</span><span class="sxs-lookup"><span data-stu-id="88402-145">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="88402-146">Confrontare l'identificazione digitale fornita dal cmdlet Set-CsCertificate per essere certi che il certificato previsto sia correttamente associato con binding HTTPS.</span><span class="sxs-lookup"><span data-stu-id="88402-146">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88402-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88402-147">See Also</span></span>


[<span data-ttu-id="88402-148">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="88402-148">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="88402-149">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="88402-149">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

