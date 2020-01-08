---
title: Assegnazione di un certificato di autenticazione server-server a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63d4e5e3ac8c544e83ab9cfb8f82a5c70f86131b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a><span data-ttu-id="5397b-102">Assegnazione di un certificato di autenticazione da server a server a Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5397b-102">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5397b-103">_**Argomento Ultima modifica:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="5397b-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="5397b-104">Per determinare se un certificato di autenticazione da server a server è già stato assegnato a Microsoft Lync Server 2013, eseguire il comando seguente da Lync Server 2013 Management Shell:</span><span class="sxs-lookup"><span data-stu-id="5397b-104">To determine whether or not a server-to-server authentication certificate has already been assigned to Microsoft Lync Server 2013, run the following command from the Lync Server 2013 Management Shell:</span></span>

    Get-CsCertificate -Type OAuthTokenIssuer

<span data-ttu-id="5397b-105">Se non vengono restituite informazioni di certificato, è necessario assegnare un certificato dell'autorità di certificazione per poter usare l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="5397b-105">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="5397b-106">Come regola generale, qualsiasi certificato di Lync Server 2013 può essere usato come certificato di OAuthTokenIssuer; ad esempio, il certificato predefinito di Lync Server 2013 può essere usato anche come certificato OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="5397b-106">As a general rule, any Lync Server 2013 certificate can be used as your OAuthTokenIssuer certificate; for example, your Lync Server 2013 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="5397b-107">Il certificato OAUthTokenIssuer può essere anche qualsiasi certificato del server Web che include il nome del dominio SIP nel campo oggetto. I due requisiti principali per il certificato usato per l'autenticazione da server a server sono i seguenti: 1) lo stesso certificato deve essere configurato come certificato OAuthTokenIssuer in tutti i server front-end. e 2) il certificato deve essere di almeno 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="5397b-107">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>

<span data-ttu-id="5397b-108">Se non si dispone di un certificato che può essere usato per l'autenticazione da server a server, è possibile ottenere un nuovo certificato, importare il nuovo certificato e quindi usare tale certificato per l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="5397b-108">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication.</span></span> <span data-ttu-id="5397b-109">Dopo aver richiesto e ottenuto il nuovo certificato, è possibile accedere a uno dei server front-end e usare un comando di Windows PowerShell simile a quello per importare e assegnare il certificato:</span><span class="sxs-lookup"><span data-stu-id="5397b-109">After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

<span data-ttu-id="5397b-110">Nel comando precedente il parametro path rappresenta il percorso completo del file di certificato e il parametro password rappresenta la password assegnata al certificato.</span><span class="sxs-lookup"><span data-stu-id="5397b-110">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="5397b-111">Questa procedura deve essere eseguita una sola volta: il servizio di replica di Lync Server creerà automaticamente un set di attività pianificate che decriptano e distribuiscono il certificato in tutti i server front-end.</span><span class="sxs-lookup"><span data-stu-id="5397b-111">This procedure should be run just one time: Lync Server's replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>

<span data-ttu-id="5397b-112">In alternativa, puoi usare un certificato esistente come certificato di autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="5397b-112">Alternatively, you can use an existing certificate as your server-to-server authentication certificate.</span></span> <span data-ttu-id="5397b-113">Come indicato, il certificato predefinito può essere usato come certificato di autenticazione da server a server. La coppia di comandi di Windows PowerShell seguente recupera il valore della proprietà identificazione personale del certificato predefinito, quindi usa questo valore per rendere il certificato predefinito il certificato di autenticazione da server a server:</span><span class="sxs-lookup"><span data-stu-id="5397b-113">(As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

<span data-ttu-id="5397b-114">Nel comando precedente il certificato recuperato è configurato per funzionare come certificato di autenticazione server-server globale; Ciò significa che il certificato verrà replicato e usato da tutti i server front-end.</span><span class="sxs-lookup"><span data-stu-id="5397b-114">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="5397b-115">Anche in questo caso, questo comando deve essere eseguito solo una volta e solo in uno dei server front-end.</span><span class="sxs-lookup"><span data-stu-id="5397b-115">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="5397b-116">Anche se tutti i server front-end devono usare lo stesso certificato, non è necessario configurare il certificato OAuthTokenIssuer in ogni server front-end.</span><span class="sxs-lookup"><span data-stu-id="5397b-116">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="5397b-117">Configurare invece il certificato una sola volta, quindi consentire al server di replica di Lync Server di eseguire la copia di tale certificato in ogni server.</span><span class="sxs-lookup"><span data-stu-id="5397b-117">Instead, configure the certificate once, then let Lync Server's replication server take care of copying that certificate to each server.</span></span>

<span data-ttu-id="5397b-118">Il cmdlet Set-CsCertificate accetta il certificato in questione e configura immediatamente il certificato in modo che agisca come certificato OAuthTokenIssuer corrente.</span><span class="sxs-lookup"><span data-stu-id="5397b-118">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="5397b-119">Lync Server 2013 mantiene due copie di un tipo di certificato: il certificato corrente e il certificato precedente. Se è necessario che il nuovo certificato cominci subito ad agire come certificato OAuthTokenIssuer, è necessario usare il cmdlet Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="5397b-119">(Lync Server 2013 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="5397b-120">Puoi anche usare il cmdlet Set-CsCertificate per "eseguire il rollback" di un nuovo certificato.</span><span class="sxs-lookup"><span data-stu-id="5397b-120">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="5397b-121">"Rotolare" un certificato significa semplicemente configurare un nuovo certificato per diventare il certificato corrente di OAuthTokenIssuer in un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="5397b-121">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="5397b-122">Ad esempio, questo comando Recupera il certificato predefinito e quindi configura tale certificato per subentrare come certificato OAuthTokenIssuer corrente al 1 ° luglio 2012:</span><span class="sxs-lookup"><span data-stu-id="5397b-122">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2012:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

<span data-ttu-id="5397b-123">Il 1 ° luglio 2012 il nuovo certificato verrà configurato come certificato OAuthTokenIssuer corrente e il certificato di OAuthTokenIssuer "vecchio" verrà configurato come certificato precedente.</span><span class="sxs-lookup"><span data-stu-id="5397b-123">On July 1, 2012 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>

<span data-ttu-id="5397b-124">Se non si vuole usare Windows PowerShell, è anche possibile usare la console MMC certificati per esportare un certificato da un server front-end e quindi importare lo stesso certificato in tutti gli altri server front-end.</span><span class="sxs-lookup"><span data-stu-id="5397b-124">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers.</span></span> <span data-ttu-id="5397b-125">In questo caso, assicurati di esportare la chiave privata insieme al certificato stesso.</span><span class="sxs-lookup"><span data-stu-id="5397b-125">If you do this, make sure that you export the private key along with the certificate itself.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="5397b-126">In questo caso, la procedura deve essere eseguita su ogni server front-end.</span><span class="sxs-lookup"><span data-stu-id="5397b-126">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="5397b-127">Quando si esportano e si importano certificati in questo modo, Lync Server 2013 non replica tale certificato in ogni server front-end.</span><span class="sxs-lookup"><span data-stu-id="5397b-127">When exporting and importing certificates in this manner Lync Server 2013 will not replicate that certificate to each Front End Server.</span></span>



</div>

<span data-ttu-id="5397b-128">Dopo aver importato il certificato in tutti i server front-end, tale certificato può essere assegnato tramite la distribuzione guidata di Lync Server anziché Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5397b-128">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Lync Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="5397b-129">Per assegnare un certificato tramite la distribuzione guidata, eseguire la procedura seguente in un computer in cui è stata installata la distribuzione guidata:</span><span class="sxs-lookup"><span data-stu-id="5397b-129">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>

1.  <span data-ttu-id="5397b-130">Fare clic sul pulsante Start, scegliere tutti i programmi, **Microsoft Lync server 2013**e quindi fare clic su **distribuzione guidata Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5397b-130">Click Start, click All Programs, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="5397b-131">Nella distribuzione guidata fare clic su **Installa o aggiorna Lync Server System**.</span><span class="sxs-lookup"><span data-stu-id="5397b-131">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="5397b-132">Nella pagina Microsoft Lync Server 2013 fare clic sul pulsante **Esegui** sotto il titolo **passaggio 3: Richiedi, installa o assegna certificati**.</span><span class="sxs-lookup"><span data-stu-id="5397b-132">On the Microsoft Lync Server 2013 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="5397b-133">Nota: se sono già stati installati certificati in questo computer, il pulsante **Esegui** verrà etichettato di **nuovo in esecuzione**.</span><span class="sxs-lookup"><span data-stu-id="5397b-133">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>

4.  <span data-ttu-id="5397b-134">Nella procedura guidata certificato selezionare il certificato **OAuthTokenIssuer** e quindi fare clic su **assegna**.</span><span class="sxs-lookup"><span data-stu-id="5397b-134">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>

5.  <span data-ttu-id="5397b-135">Nella pagina **assegnazione** certificato della procedura guidata assegnazione certificati fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5397b-135">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>

6.  <span data-ttu-id="5397b-136">Nella pagina **archivio certificati** selezionare il certificato da usare per l'autenticazione da server a server e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5397b-136">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>

7.  <span data-ttu-id="5397b-137">Nella pagina Riepilogo assegnazione certificati fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5397b-137">On the Certificate Assignment Summary page, click **Next**.</span></span>

8.  <span data-ttu-id="5397b-138">Nella pagina esecuzione dei comandi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="5397b-138">On the Executing Commands page, click **Finish**.</span></span>

9.  <span data-ttu-id="5397b-139">Chiudere la procedura guidata certificato e la distribuzione guidata.</span><span class="sxs-lookup"><span data-stu-id="5397b-139">Close the Certificate Wizard and the Deployment Wizard.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

