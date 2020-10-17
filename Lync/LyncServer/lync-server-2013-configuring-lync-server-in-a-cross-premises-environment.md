---
title: 'Lync Server 2013: configurazione di Lync Server in un ambiente cross-premise'
description: 'Lync Server 2013: configurazione di Lync Server in un ambiente cross-premise.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1ec978cd8e0e34c01c1d5cabb5bba42debd16fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570862"
---
# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a><span data-ttu-id="1c5b6-103">Configurazione di Microsoft Lync Server 2013 in un ambiente cross-premise</span><span class="sxs-lookup"><span data-stu-id="1c5b6-103">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c5b6-104">_**Ultimo argomento modificato:** 2017-02-21_</span><span class="sxs-lookup"><span data-stu-id="1c5b6-104">_**Topic Last Modified:** 2017-02-21_</span></span>

<span data-ttu-id="1c5b6-105">In una configurazione cross-premise, alcuni utenti sono ospitati in un'installazione locale di Microsoft Lync Server 2013 mentre altri utenti sono ospitati nella versione Microsoft 365 o Office 365 di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-105">In a cross-premise configuration, some of your users are homed on an on-premises installation of Microsoft Lync Server 2013 while other users are homed on the Microsoft 365 or Office 365 version of Lync Server.</span></span> <span data-ttu-id="1c5b6-106">Per configurare l'autenticazione da server a server in un ambiente cross-premise, è innanzitutto necessario configurare l'installazione locale di Lync Server 2013 in modo che consideri attendibile il server di autorizzazione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-106">In order to configure server-to-server authentication in a cross-premises environment, you must first configure your on-premises installation of Lync Server 2013 to trust the Microsoft 365 Authorization server.</span></span> <span data-ttu-id="1c5b6-107">È possibile eseguire il passaggio iniziale di questo processo eseguendo il seguente script di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="1c5b6-107">The initial step in this process can be carried out by running the following Lync Server Management Shell script:</span></span>

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

<span data-ttu-id="1c5b6-p102">Tenere a mente che il nome dell'area di autenticazione di un tenant è solitamente diverso da quello dell'organizzazione. Quasi mai il nome dell'area di autenticazione corrisponde a quello dell'ID del tenant. Per questo motivo, la prima riga dello script è utilizzata per restituire il valore della proprietà TenantId del tenant specificato (in questo caso, fabrikam.com) e per poi assegnare il nome alla variabile $TenantId:</span><span class="sxs-lookup"><span data-stu-id="1c5b6-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

<span data-ttu-id="1c5b6-110">Dopo aver completato lo script, è necessario configurare una relazione di trust tra Lync Server 2013 e il server di autorizzazione, nonché una seconda relazione di trust tra Exchange 2013 e il server di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-110">After the script completes you must then configure a trust relationship between Lync Server 2013 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="1c5b6-111">È possibile farlo soltanto attraverso i cmdlet di Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-111">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c5b6-112">Se i cmdlet di Microsoft Online Services non sono installati, è necessario eseguire due operazioni prima di procedere.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-112">If you have not installed the Microsoft Online Services cmdlets you will need to do two things before proceeding.</span></span> <span data-ttu-id="1c5b6-113">Per prima cosa, scaricare e installare la versione a 64 bit di Microsoft Online Services Sign-in Assistant.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-113">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="1c5b6-114">Al termine dell'installazione, scaricare e installare la versione 64 bit del modulo dei Microsoft Online Services per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-114">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="1c5b6-115">Informazioni dettagliate per l'installazione e l'utilizzo del modulo dei Microsoft Online Services sono disponibili nel sito Web Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Microsoft 365 or Office 365 web site.</span></span> <span data-ttu-id="1c5b6-116">Queste istruzioni illustrano inoltre come configurare il servizio Single Sign-on, la Federazione e la sincronizzazione tra Microsoft 365 o Office 36 e Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Microsoft 365 or Office 36 and Active Directory.</span></span><BR><span data-ttu-id="1c5b6-117">Se i cmdlet non sono stati installati, lo script avrà esito negativo perché il cmdlet Get-CsTenant non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-117">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>



</div>

<span data-ttu-id="1c5b6-118">Dopo aver configurato Microsoft 365 e dopo aver creato le entità di servizio di Microsoft 365 o Office 365 per Lync Server 2013 ed Exchange 2013, sarà necessario registrare le credenziali con queste entità di servizio.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-118">After you have configured Microsoft 365, and after you have created Microsoft 365 or Office 365 service principals for Lync Server 2013 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="1c5b6-119">Per farlo, è necessario ottenere un certificato base64 X.509 salvato come file .CER.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-119">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="1c5b6-120">Questo certificato verrà quindi applicato alle entità di servizio Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-120">This certificate will then be applied to the Microsoft 365 or Office 365 service principals.</span></span>

<span data-ttu-id="1c5b6-121">Dopo aver ottenuto il certificato X. 509, avviare il modulo dei Microsoft Online Services (fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Online Services**e quindi fare clic su **modulo dei Microsoft Online Services per Windows PowerShell**).</span><span class="sxs-lookup"><span data-stu-id="1c5b6-121">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="1c5b6-122">Dopo l'apertura del modulo servizi, digitare il comando seguente per importare il modulo Microsoft online di Windows PowerShell contenente i cmdlet che possono essere utilizzati per gestire le entità di servizio:</span><span class="sxs-lookup"><span data-stu-id="1c5b6-122">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

    Import-Module MSOnlineExtended

<span data-ttu-id="1c5b6-123">Quando il modulo è stato importato, digitare il comando seguente e quindi premere INVIO per connettersi a Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="1c5b6-123">When the module has been imported, type the following command and then press ENTER in order to connect to Microsoft 365:</span></span>

    Connect-MsolService

<span data-ttu-id="1c5b6-124">A questo punto, viene visualizzata una finestra di dialogo delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-124">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="1c5b6-125">Immettere il nome utente e la password di Microsoft 365 o Office 365 nella finestra di dialogo e quindi fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-125">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="1c5b6-126">Non appena si è connessi a Microsoft 365, è possibile eseguire il comando seguente per restituire le informazioni sulle entità di servizio:</span><span class="sxs-lookup"><span data-stu-id="1c5b6-126">As soon as you are connected to Microsoft 365 you can then run the following command in order to return information about your service principals:</span></span>

    Get-MsolServicePrincipal

<span data-ttu-id="1c5b6-127">Si dovrebbero ottenere informazioni simili alle seguenti, per tutti i nomi del servizio principale:</span><span class="sxs-lookup"><span data-stu-id="1c5b6-127">You should get back information similar to this for all your service principals:</span></span>

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

<span data-ttu-id="1c5b6-128">Il passaggio successivo consiste nell'importazione, codifica e assegnazione del certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-128">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="1c5b6-129">Per importare e codificare il certificato, utilizzare i seguenti comandi di Windows PowerShell, assicurandosi di specificare il percorso completo del file. File CER quando si chiama il metodo Import:</span><span class="sxs-lookup"><span data-stu-id="1c5b6-129">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

<span data-ttu-id="1c5b6-130">Dopo che il certificato è stato importato e codificato, è possibile assegnare il certificato alle entità di servizio Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-130">After the certificate has been imported and encoded, you can then assign the certificate to your Microsoft 365 service principals.</span></span> <span data-ttu-id="1c5b6-131">A tale scopo, utilizzare prima la Get-MsolServicePrincipal per recuperare il valore della proprietà AppPrincipalId per le entità dei servizi Lync Server e Microsoft Exchange. il valore della proprietà AppPrincipalId verrà utilizzato per identificare l'entità di servizio a cui è assegnato il certificato.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-131">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Lync Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="1c5b6-132">Con il valore della proprietà AppPrincipalId per Lync Server 2013 in mano, utilizzare il seguente comando per assegnare il certificato alla versione Microsoft 365 di Lync Server (le proprietà StartDate e EndDate devono corrispondere al periodo di validità del certificato):</span><span class="sxs-lookup"><span data-stu-id="1c5b6-132">With the AppPrincipalId property value for Lync Server 2013 in hand, use the following command to assign the certificate to the Microsoft 365 version of Lync Server (the StartDate and EndDate properties should correspond to the validity period for the certificate):</span></span>

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

<span data-ttu-id="1c5b6-133">È quindi necessario ripetere il comando, stavolta utilizzando il valore della proprietà AppPrincipalId per Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-133">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="1c5b6-134">Se successivamente si ha bisogno di eliminare il certificato, è possibile farlo recuperando il KeyId per il certificato:</span><span class="sxs-lookup"><span data-stu-id="1c5b6-134">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="1c5b6-135">Il comando restituisce dati simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c5b6-135">That command will return data like this one:</span></span>

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

<span data-ttu-id="1c5b6-136">È possibile eliminare il certificato utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="1c5b6-136">You can then delete the certificate by using a command similar to this:</span></span>

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

<span data-ttu-id="1c5b6-137">Oltre all'assegnazione di un certificato, è necessario configurare anche l'entità servizio Microsoft 365 per Exchange Online aggiungendo il nome dell'entità server per la versione locale di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c5b6-137">In addition to assigning a certificate you must also configure the Microsoft 365 Service Principal for Exchange Online by adding the Server Principal Name for your on-premise version of Lync Server 2013.</span></span> <span data-ttu-id="1c5b6-138">A tale scopo, è possibile eseguire le quattro righe seguenti in una sessione di PowerShell dei Microsoft Online Services:</span><span class="sxs-lookup"><span data-stu-id="1c5b6-138">This can be done by running the following four lines in a Microsoft Online Services PowerShell session:</span></span>

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

