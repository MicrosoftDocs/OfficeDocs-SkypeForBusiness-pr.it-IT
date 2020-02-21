---
title: Assegnazione di un certificato di autenticazione da server a server a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 952f4c1b14ce7260d4b320ea7feacddb9a85a8f0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a><span data-ttu-id="84109-102">Assegnazione di un certificato di autenticazione da server a server a Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84109-102">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84109-103">_**Ultimo argomento modificato:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="84109-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="84109-104">Per determinare se un certificato di autenticazione da server a server è già stato assegnato a Microsoft Lync Server 2013, eseguire il comando seguente da Lync Server 2013 Management Shell:</span><span class="sxs-lookup"><span data-stu-id="84109-104">To determine whether or not a server-to-server authentication certificate has already been assigned to Microsoft Lync Server 2013, run the following command from the Lync Server 2013 Management Shell:</span></span>

    Get-CsCertificate -Type OAuthTokenIssuer

<span data-ttu-id="84109-105">Se non vengono restituite informazioni sui certificati, è necessario assegnare un certificato dell'autorità emittente di token prima di poter utilizzare l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="84109-105">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="84109-106">Come regola generale, qualsiasi certificato di Lync Server 2013 può essere utilizzato come certificato di OAuthTokenIssuer. ad esempio, il certificato predefinito di Lync Server 2013 può essere utilizzato anche come certificato di OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="84109-106">As a general rule, any Lync Server 2013 certificate can be used as your OAuthTokenIssuer certificate; for example, your Lync Server 2013 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="84109-107">Il certificato OAUthTokenIssuer può anche essere qualsiasi certificato del server Web che include il nome del dominio SIP nel campo Subject. I due requisiti principali per il certificato utilizzato per l'autenticazione da server a server sono i seguenti: 1) lo stesso certificato deve essere configurato come certificato OAuthTokenIssuer su tutti i Front End Server; 2) il certificato deve essere almeno pari a 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="84109-107">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>

<span data-ttu-id="84109-p102">Se non si dispone di un certificato da utilizzare per l'autenticazione da server a server, è possibile ottenere un nuovo certificato, importarlo e quindi utilizzarlo per l'autenticazione da server a server. Dopo aver richiesto e ottenuto il nuovo certificato, è possibile accedere a uno dei Front End Server e utilizzare un comando di Windows PowerShell simile al seguente per importare e assegnare il certificato:</span><span class="sxs-lookup"><span data-stu-id="84109-p102">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication. After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

<span data-ttu-id="84109-p103">Nel comando precedente il parametro Path rappresenta il percorso completo del file di certificato e il parametro Password rappresenta la password assegnata al certificato. Questa procedura deve essere eseguita una sola volta. Il servizio di replica di Lync Server creerà quindi automaticamente un insieme di attività pianificate per decrittografare e distribuire il certificato in tutti i Front End Server.</span><span class="sxs-lookup"><span data-stu-id="84109-p103">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate. This procedure should be run just one time: Lync Server's replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>

<span data-ttu-id="84109-p104">In alternativa, è possibile utilizzare come certificato di autenticazione da server a server un certificato esistente. Come già specificato, è possibile utilizzare a tale scopo il certificato predefinito. La coppia seguente di comandi di Windows PowerShell recupera il valore della proprietà Thumbprint del certificato predefinito e quindi utilizza tale valore per impostare il certificato predefinito come certificato di autenticazione da server a server:</span><span class="sxs-lookup"><span data-stu-id="84109-p104">Alternatively, you can use an existing certificate as your server-to-server authentication certificate. (As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

<span data-ttu-id="84109-p105">Nel comando precedente il certificato recuperato viene configurato in modo da funzionare come certificato di autenticazione da server a server globale. In questo modo il certificato verrà replicato in tutti i Front End Server e da essi utilizzato. Come già specificato, questo comando deve essere eseguito una sola volta e solo in un Front End Server. Anche se tutti i Front End Server devono utilizzare lo stesso certificato, non è necessario configurare il certificato OAuthTokenIssuer in ognuno di essi. Sarà sufficiente configurarlo una volta e quindi il server di replica di Lync Server lo copierà in ogni server.</span><span class="sxs-lookup"><span data-stu-id="84109-p105">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers. Again, this command should only be run one time, and only on one of your Front End Servers. Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server. Instead, configure the certificate once, then let Lync Server's replication server take care of copying that certificate to each server.</span></span>

<span data-ttu-id="84109-118">Il cmdlet Set-CsCertificate accetta il certificato in questione e configura immediatamente il certificato in modo che funga da certificato OAuthTokenIssuer corrente.</span><span class="sxs-lookup"><span data-stu-id="84109-118">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="84109-119">(Lync Server 2013 conserva due copie di un tipo di certificato: il certificato corrente e il certificato precedente). Se è necessario che il nuovo certificato cominci subito a fungere da certificato OAuthTokenIssuer, è necessario utilizzare il cmdlet Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="84109-119">(Lync Server 2013 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="84109-p107">È inoltre possibile utilizzare il cmdlet Set-CsCertificate per distribuire un nuovo certificato, ovvero configurare un nuovo certificato in modo che diventi il certificato OAuthTokenIssuer corrente in un determinato momento. Il comando seguente ad esempio recupera il certificato predefinito e quindi lo configura in modo che subentri come certificato OAuthTokenIssuer corrente a partire dal 1° luglio 2012:</span><span class="sxs-lookup"><span data-stu-id="84109-p107">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate. "Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time. For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2012:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

<span data-ttu-id="84109-123">Il 1° luglio 2012 il nuovo certificato verrà configurato come certificato OAuthTokenIssuer corrente e il certificato OAuthTokenIssuer attivo fino a quel momento verrà configurato come certificato precedente.</span><span class="sxs-lookup"><span data-stu-id="84109-123">On July 1, 2012 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>

<span data-ttu-id="84109-p108">Se non si desidera utilizzare Windows PowerShell, è possibile utilizzare la console MMC Certificati per esportare un certificato da un Front End Server e quindi importarlo in tutti gli altri Front End Server. Se si sceglie questa soluzione, esportare la chiave privata insieme al certificato.</span><span class="sxs-lookup"><span data-stu-id="84109-p108">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers. If you do this, make sure that you export the private key along with the certificate itself.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="84109-126">In questo caso, la procedura deve essere eseguita in ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="84109-126">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="84109-127">Quando si esporta e si importano certificati in questo modo, Lync Server 2013 non replica il certificato in ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="84109-127">When exporting and importing certificates in this manner Lync Server 2013 will not replicate that certificate to each Front End Server.</span></span>



</div>

<span data-ttu-id="84109-128">Dopo che il certificato è stato importato in tutti i Front End Server, tale certificato può essere assegnato tramite la distribuzione guidata di Lync Server anziché Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84109-128">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Lync Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="84109-129">Per assegnare un certificato utilizzando la Distribuzione guidata, eseguire le operazioni seguenti in un computer in cui è stata installata la Distribuzione guidata:</span><span class="sxs-lookup"><span data-stu-id="84109-129">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>

1.  <span data-ttu-id="84109-130">Fare clic sul pulsante Start, scegliere tutti i programmi, **Microsoft Lync server 2013**e quindi **distribuzione guidata di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="84109-130">Click Start, click All Programs, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="84109-131">Nella Distribuzione guidata fare clic su **Installa o aggiorna il sistema Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="84109-131">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="84109-132">Nella pagina Microsoft Lync Server 2013 fare clic sul pulsante **Esegui** al di sotto del titolo **passaggio 3: richiesta, installazione o assegnazione dei certificati**.</span><span class="sxs-lookup"><span data-stu-id="84109-132">On the Microsoft Lync Server 2013 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="84109-133">Nota: se nel computer sono stati già installati certificati, anziché il pulsante **Esegui** sarà disponibile il pulsante **Riesegui**.</span><span class="sxs-lookup"><span data-stu-id="84109-133">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>

4.  <span data-ttu-id="84109-134">Nella Configurazione guidata certificati selezionare il certificato **OAuthTokenIssuer** e quindi fare clic su **Assegna certificato**.</span><span class="sxs-lookup"><span data-stu-id="84109-134">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>

5.  <span data-ttu-id="84109-135">Nella pagina **Assegnazione certificato** della procedura guidata Assegnazione certificato fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="84109-135">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>

6.  <span data-ttu-id="84109-136">Nella pagina **Archivio certificati** selezionare il certificato da utilizzare per l'autenticazione da server a server e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="84109-136">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>

7.  <span data-ttu-id="84109-137">Nella pagina Riepilogo assegnazione certificato fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="84109-137">On the Certificate Assignment Summary page, click **Next**.</span></span>

8.  <span data-ttu-id="84109-138">Nella pagina Esecuzione comandi in corso fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="84109-138">On the Executing Commands page, click **Finish**.</span></span>

9.  <span data-ttu-id="84109-139">Chiudere la Creazione guidata certificati e la Distribuzione guidata.</span><span class="sxs-lookup"><span data-stu-id="84109-139">Close the Certificate Wizard and the Deployment Wizard.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

