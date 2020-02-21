---
title: 'Lync Server 2013: configurazione di Lync Server in un ambiente cross-premise'
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
ms.openlocfilehash: a95f2fba2d65f0d25f1fa9b843dd7bb47240aa6c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a><span data-ttu-id="e2988-102">Configurazione di Microsoft Lync Server 2013 in un ambiente cross-premise</span><span class="sxs-lookup"><span data-stu-id="e2988-102">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2988-103">_**Ultimo argomento modificato:** 2017-02-21_</span><span class="sxs-lookup"><span data-stu-id="e2988-103">_**Topic Last Modified:** 2017-02-21_</span></span>

<span data-ttu-id="e2988-104">In una configurazione cross-premise, alcuni utenti sono ospitati in un'installazione locale di Microsoft Lync Server 2013 mentre altri utenti sono ospitati nella versione Office 365 di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e2988-104">In a cross-premise configuration, some of your users are homed on an on-premises installation of Microsoft Lync Server 2013 while other users are homed on the Office 365 version of Lync Server.</span></span> <span data-ttu-id="e2988-105">Per configurare l'autenticazione da server a server in un ambiente cross-premise, è innanzitutto necessario configurare l'installazione locale di Lync Server 2013 in modo che consideri attendibile il server di autorizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2988-105">In order to configure server-to-server authentication in a cross-premises environment, you must first configure your on-premises installation of Lync Server 2013 to trust the Office 365 Authorization server.</span></span> <span data-ttu-id="e2988-106">È possibile eseguire il passaggio iniziale di questo processo eseguendo il seguente script di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="e2988-106">The initial step in this process can be carried out by running the following Lync Server Management Shell script:</span></span>

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

<span data-ttu-id="e2988-p102">Tenere a mente che il nome dell'area di autenticazione di un tenant è solitamente diverso da quello dell'organizzazione. Quasi mai il nome dell'area di autenticazione corrisponde a quello dell'ID del tenant. Per questo motivo, la prima riga dello script è utilizzata per restituire il valore della proprietà TenantId del tenant specificato (in questo caso, fabrikam.com) e per poi assegnare il nome alla variabile $TenantId:</span><span class="sxs-lookup"><span data-stu-id="e2988-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

<span data-ttu-id="e2988-109">Dopo aver completato lo script, è necessario configurare una relazione di trust tra Lync Server 2013 e il server di autorizzazione, nonché una seconda relazione di trust tra Exchange 2013 e il server di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="e2988-109">After the script completes you must then configure a trust relationship between Lync Server 2013 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="e2988-110">È possibile farlo soltanto attraverso i cmdlet di Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="e2988-110">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e2988-111">Se i cmdlet di Microsoft Online Services non sono installati, è necessario eseguire due operazioni prima di procedere.</span><span class="sxs-lookup"><span data-stu-id="e2988-111">If you have not installed the Microsoft Online Services cmdlets you will need to do two things before proceeding.</span></span> <span data-ttu-id="e2988-112">Per prima cosa, scaricare e installare la versione a 64 bit di Microsoft Online Services Sign-in Assistant.</span><span class="sxs-lookup"><span data-stu-id="e2988-112">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="e2988-113">Al termine dell'installazione, scaricare e installare la versione 64 bit del modulo dei Microsoft Online Services per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2988-113">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="e2988-114">Nel sito Web di Office 365 è possibile trovare informazioni sull'installazione e l'utilizzo del modulo dei Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="e2988-114">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="e2988-115">Le istruzioni illustrano inoltre come configurare l'accesso single sign-on, la federazione e la sincronizzazione tra Office 365 e Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e2988-115">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span><BR><span data-ttu-id="e2988-116">Se i cmdlet non sono stati installati, lo script avrà esito negativo perché il cmdlet Get-CsTenant non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="e2988-116">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>



</div>

<span data-ttu-id="e2988-117">Dopo aver configurato Office 365 e dopo aver creato le entità di servizio di Office 365 per Lync Server 2013 ed Exchange 2013, sarà necessario registrare le credenziali con tali entità di servizio.</span><span class="sxs-lookup"><span data-stu-id="e2988-117">After you have configured Office 365, and after you have created Office 365 service principals for Lync Server 2013 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="e2988-118">Per farlo, è necessario ottenere un certificato base64 X.509 salvato come file .CER.</span><span class="sxs-lookup"><span data-stu-id="e2988-118">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="e2988-119">Questo certificato sarà quindi applicato ai nomi del servizio principale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2988-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="e2988-120">Dopo aver ottenuto il certificato X. 509, avviare il modulo dei Microsoft Online Services (fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Online Services**e quindi fare clic su **modulo dei Microsoft Online Services per Windows PowerShell**).</span><span class="sxs-lookup"><span data-stu-id="e2988-120">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="e2988-121">Dopo l'apertura del modulo servizi, digitare il comando seguente per importare il modulo Microsoft online di Windows PowerShell contenente i cmdlet che possono essere utilizzati per gestire le entità di servizio:</span><span class="sxs-lookup"><span data-stu-id="e2988-121">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

    Import-Module MSOnlineExtended

<span data-ttu-id="e2988-122">Dopo avere importato il modulo, digitare il comando seguente e premere Invio, per connettersi a Office 365:</span><span class="sxs-lookup"><span data-stu-id="e2988-122">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

    Connect-MsolService

<span data-ttu-id="e2988-p107">A questo punto, viene visualizzata una finestra di dialogo delle credenziali. Digitare il nome utente e la password di Office 365 nella finestra di dialogo, quindi scegliere OK.</span><span class="sxs-lookup"><span data-stu-id="e2988-p107">After you press ENTER, a credentials dialog box will appear. Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="e2988-125">Quando si è connessi a Office 365, è possibile eseguire il comando seguente per ottenere le informazioni relative ai nomi del servizio principale:</span><span class="sxs-lookup"><span data-stu-id="e2988-125">As soon as you are connected to Office 365 you can then run the following command in order to return information about your service principals:</span></span>

    Get-MsolServicePrincipal

<span data-ttu-id="e2988-126">Si dovrebbero ottenere informazioni simili alle seguenti, per tutti i nomi del servizio principale:</span><span class="sxs-lookup"><span data-stu-id="e2988-126">You should get back information similar to this for all your service principals:</span></span>

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

<span data-ttu-id="e2988-127">Il passaggio successivo consiste nell'importazione, codifica e assegnazione del certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="e2988-127">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="e2988-128">Per importare e codificare il certificato, utilizzare i seguenti comandi di Windows PowerShell, assicurandosi di specificare il percorso completo del file. File CER quando si chiama il metodo Import:</span><span class="sxs-lookup"><span data-stu-id="e2988-128">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

<span data-ttu-id="e2988-129">Dopo che il certificato è stato importato e codificato, è possibile assegnare il certificato alle entità di servizio di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2988-129">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="e2988-130">A tale scopo, utilizzare prima il Get-MsolServicePrincipal viene per recuperare il valore della proprietà AppPrincipalId sia per le entità di servizio di Lync Server che di Microsoft Exchange. il valore della proprietà AppPrincipalId verrà utilizzato per identificare l'entità di servizio a cui è assegnato il certificato.</span><span class="sxs-lookup"><span data-stu-id="e2988-130">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Lync Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="e2988-131">Con il valore della proprietà AppPrincipalId per Lync Server 2013 in mano, utilizzare il seguente comando per assegnare il certificato alla versione Office 365 di Lync Server (le proprietà StartDate e EndDate devono corrispondere al periodo di validità del certificato):</span><span class="sxs-lookup"><span data-stu-id="e2988-131">With the AppPrincipalId property value for Lync Server 2013 in hand, use the following command to assign the certificate to the Office 365 version of Lync Server (the StartDate and EndDate properties should correspond to the validity period for the certificate):</span></span>

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

<span data-ttu-id="e2988-132">È quindi necessario ripetere il comando, stavolta utilizzando il valore della proprietà AppPrincipalId per Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="e2988-132">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="e2988-133">Se successivamente si ha bisogno di eliminare il certificato, è possibile farlo recuperando il KeyId per il certificato:</span><span class="sxs-lookup"><span data-stu-id="e2988-133">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="e2988-134">Il comando restituisce dati simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2988-134">That command will return data like this one:</span></span>

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

<span data-ttu-id="e2988-135">È possibile eliminare il certificato utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e2988-135">You can then delete the certificate by using a command similar to this:</span></span>

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

<span data-ttu-id="e2988-136">Oltre ad assegnare un certificato, è inoltre necessario configurare l'entità servizio di Office 365 per Exchange Online aggiungendo il nome dell'entità server per la versione locale di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2988-136">In addition to assigning a certificate you must also configure the Office 365 Service Principal for Exchange Online by adding the Server Principal Name for your on-premise version of Lync Server 2013.</span></span> <span data-ttu-id="e2988-137">A tale scopo, è possibile eseguire le quattro righe seguenti in una sessione di PowerShell dei Microsoft Online Services:</span><span class="sxs-lookup"><span data-stu-id="e2988-137">This can be done by running the following four lines in a Microsoft Online Services PowerShell session:</span></span>

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

