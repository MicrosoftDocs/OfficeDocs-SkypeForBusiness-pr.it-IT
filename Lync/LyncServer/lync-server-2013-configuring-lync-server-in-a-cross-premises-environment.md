---
title: 'Lync Server 2013: configurazione di Lync Server in un ambiente cross-locale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44a47dc3bf3c832819fe431cb0177bfc1a03f330
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a><span data-ttu-id="2ea24-102">Configurazione di Microsoft Lync Server 2013 in un ambiente tra più locali</span><span class="sxs-lookup"><span data-stu-id="2ea24-102">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ea24-103">_**Argomento Ultima modifica:** 2017-02-21_</span><span class="sxs-lookup"><span data-stu-id="2ea24-103">_**Topic Last Modified:** 2017-02-21_</span></span>

<span data-ttu-id="2ea24-104">In una configurazione interlocale, alcuni utenti si trovano in un'installazione locale di Microsoft Lync Server 2013 mentre altri utenti si trovano nella versione di Office 365 di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2ea24-104">In a cross-premise configuration, some of your users are homed on an on-premises installation of Microsoft Lync Server 2013 while other users are homed on the Office 365 version of Lync Server.</span></span> <span data-ttu-id="2ea24-105">Per configurare l'autenticazione da server a server in un ambiente Multilocale, è prima necessario configurare l'installazione locale di Lync Server 2013 per considerare attendibile il server di autorizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ea24-105">In order to configure server-to-server authentication in a cross-premises environment, you must first configure your on-premises installation of Lync Server 2013 to trust the Office 365 Authorization server.</span></span> <span data-ttu-id="2ea24-106">Il passaggio iniziale di questo processo può essere eseguito eseguendo il seguente script di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="2ea24-106">The initial step in this process can be carried out by running the following Lync Server Management Shell script:</span></span>

    $TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
    
    $sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue
            
       if ($sts -eq $null)
          {
             New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
          }
       else
          {
             if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
                {
                   Remove-CsOAuthServer microsoft.sts
                   New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
                }
            }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
                 New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
              }
           else
              {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
              }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="2ea24-107">Tieni presente che il nome dell'area di autenticazione per un tenant è in genere diverso rispetto al nome dell'organizzazione; il nome Realm è infatti quasi sempre uguale all'ID tenant.</span><span class="sxs-lookup"><span data-stu-id="2ea24-107">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID.</span></span> <span data-ttu-id="2ea24-108">Per questo motivo, la prima riga nello script viene usata per restituire il valore della proprietà ID tenant per il tenant specificato (in questo caso fabrikam.com) e quindi assegnare il nome alla variabile $TenantId:</span><span class="sxs-lookup"><span data-stu-id="2ea24-108">Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

<span data-ttu-id="2ea24-109">Al termine dello script, è necessario configurare una relazione di trust tra Lync Server 2013 e il server di autorizzazione e una seconda relazione di trust tra Exchange 2013 e il server di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="2ea24-109">After the script completes you must then configure a trust relationship between Lync Server 2013 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="2ea24-110">Questa operazione può essere eseguita solo usando i cmdlet dei Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="2ea24-110">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2ea24-111">Se non sono stati installati i cmdlet dei Microsoft Online Services, è necessario eseguire due operazioni prima di procedere.</span><span class="sxs-lookup"><span data-stu-id="2ea24-111">If you have not installed the Microsoft Online Services cmdlets you will need to do two things before proceeding.</span></span> <span data-ttu-id="2ea24-112">Prima di tutto, scaricare e installare la versione a 64 bit dell'assistente per l'accesso ai Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="2ea24-112">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="2ea24-113">Al termine dell'installazione, scaricare e installare la versione a 64 bit del modulo Microsoft Online Services per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ea24-113">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="2ea24-114">Informazioni dettagliate per l'installazione e l'uso del modulo Microsoft Online Services si trovano nel sito Web di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ea24-114">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="2ea24-115">Queste istruzioni spiegano anche come configurare Single Sign-on, Federation e la sincronizzazione tra Office 365 e Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2ea24-115">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span><BR><span data-ttu-id="2ea24-116">Se non sono stati installati questi cmdlet, lo script non riuscirà perché il cmdlet Get-CsTenant non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="2ea24-116">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>



</div>

<span data-ttu-id="2ea24-117">Dopo aver configurato Office 365 e dopo aver creato le entità di servizio di Office 365 per Lync Server 2013 ed Exchange 2013, sarà necessario registrare le credenziali con queste entità di servizio.</span><span class="sxs-lookup"><span data-stu-id="2ea24-117">After you have configured Office 365, and after you have created Office 365 service principals for Lync Server 2013 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="2ea24-118">Per eseguire questa operazione, devi prima ottenere un X. 509 Base64 salvato come. File CER.</span><span class="sxs-lookup"><span data-stu-id="2ea24-118">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="2ea24-119">Questo certificato verrà quindi applicato alle entità di servizio di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ea24-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="2ea24-120">Dopo aver ottenuto il certificato X. 509, avviare il modulo Microsoft Online Services (fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft Online Services**e quindi su **modulo Microsoft Online Services per Windows PowerShell**).</span><span class="sxs-lookup"><span data-stu-id="2ea24-120">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="2ea24-121">Dopo l'apertura del modulo servizi, digitare quanto segue per importare il modulo Microsoft online di Windows PowerShell contenente i cmdlet che possono essere usati per gestire le entità di servizio:</span><span class="sxs-lookup"><span data-stu-id="2ea24-121">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

    Import-Module MSOnlineExtended

<span data-ttu-id="2ea24-122">Quando il modulo è stato importato, digitare il comando seguente e quindi premere INVIO per connettersi a Office 365:</span><span class="sxs-lookup"><span data-stu-id="2ea24-122">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

    Connect-MsolService

<span data-ttu-id="2ea24-123">Dopo aver premuto INVIO, verrà visualizzata una finestra di dialogo credenziali.</span><span class="sxs-lookup"><span data-stu-id="2ea24-123">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="2ea24-124">Immettere il nome utente e la password di Office 365 nella finestra di dialogo e quindi fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2ea24-124">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="2ea24-125">Non appena si è connessi a Office 365, è possibile eseguire il comando seguente per restituire informazioni sulle entità di servizio:</span><span class="sxs-lookup"><span data-stu-id="2ea24-125">As soon as you are connected to Office 365 you can then run the following command in order to return information about your service principals:</span></span>

    Get-MsolServicePrincipal

<span data-ttu-id="2ea24-126">È consigliabile recuperare informazioni simili a quelle per tutte le entità di servizio:</span><span class="sxs-lookup"><span data-stu-id="2ea24-126">You should get back information similar to this for all your service principals:</span></span>

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

<span data-ttu-id="2ea24-127">Il passaggio successivo consiste nell'importare, codificare e assegnare il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="2ea24-127">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="2ea24-128">Per importare e codificare il certificato, usare i comandi di Windows PowerShell seguenti, in modo da specificare il percorso completo del file. File CER quando si chiama il metodo di importazione:</span><span class="sxs-lookup"><span data-stu-id="2ea24-128">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

<span data-ttu-id="2ea24-129">Dopo aver importato e codificato il certificato, è possibile assegnare il certificato alle entità di servizio di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ea24-129">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="2ea24-130">A questo scopo, USA prima di tutto Get-MsolServicePrincipal viene per recuperare il valore della proprietà AppPrincipalId sia per il server Lync che per le entità dei servizi di Microsoft Exchange. il valore della proprietà AppPrincipalId verrà usato per identificare l'entità del servizio a cui è stato assegnato il certificato.</span><span class="sxs-lookup"><span data-stu-id="2ea24-130">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Lync Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="2ea24-131">Con il valore della proprietà AppPrincipalId per Lync Server 2013 in mano, usare il comando seguente per assegnare il certificato alla versione di Office 365 di Lync Server (le proprietà StartDate ed EndDate devono corrispondere al periodo di validità del certificato):</span><span class="sxs-lookup"><span data-stu-id="2ea24-131">With the AppPrincipalId property value for Lync Server 2013 in hand, use the following command to assign the certificate to the Office 365 version of Lync Server (the StartDate and EndDate properties should correspond to the validity period for the certificate):</span></span>

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

<span data-ttu-id="2ea24-132">Devi quindi ripetere il comando, questa volta usando il valore della proprietà AppPrincipalId per Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2ea24-132">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="2ea24-133">Se in seguito è necessario eliminare il certificato, è possibile eseguire prima di tutto il recupero di KeyId per il certificato:</span><span class="sxs-lookup"><span data-stu-id="2ea24-133">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="2ea24-134">Il comando restituirà dati come questo:</span><span class="sxs-lookup"><span data-stu-id="2ea24-134">That command will return data like this one:</span></span>

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

<span data-ttu-id="2ea24-135">È quindi possibile eliminare il certificato usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="2ea24-135">You can then delete the certificate by using a command similar to this:</span></span>

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

<span data-ttu-id="2ea24-136">Oltre ad assegnare un certificato, è necessario configurare anche l'entità di servizio di Office 365 per Exchange Online aggiungendo il nome dell'entità server per la versione locale di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ea24-136">In addition to assigning a certificate you must also configure the Office 365 Service Principal for Exchange Online by adding the Server Principal Name for your on-premise version of Lync Server 2013.</span></span> <span data-ttu-id="2ea24-137">Questa operazione può essere eseguita eseguendo le quattro righe seguenti in una sessione di PowerShell di Microsoft Online Services:</span><span class="sxs-lookup"><span data-stu-id="2ea24-137">This can be done by running the following four lines in a Microsoft Online Services PowerShell session:</span></span>

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

