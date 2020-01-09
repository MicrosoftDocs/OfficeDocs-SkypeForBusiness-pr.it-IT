---
title: Configurare l'autenticazione da server a server per un ambiente ibrido di Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: "Riepilogo: configurare l'autenticazione da server a server per un ambiente ibrido di Skype for Business Server."
ms.openlocfilehash: 5d56f098589355b85f942a6b1eb80d8ab6c03225
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992353"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="86203-103">Configurare l'autenticazione da server a server per un ambiente ibrido di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="86203-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="86203-104">**Riepilogo:** Configurare l'autenticazione da server a server per l'ambiente ibrido di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="86203-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="86203-105">In una configurazione ibrida, alcuni utenti sono ospitati in un'installazione locale di Skype for Business Server mentre altri utenti si trovano nella versione di Office 365 di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="86203-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="86203-106">Per configurare l'autenticazione da server a server in un ambiente ibrido, è prima di tutto necessario configurare l'installazione locale di Skype for Business Server per considerare attendibile il server di autorizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="86203-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the Office 365 authorization server.</span></span> <span data-ttu-id="86203-107">Il passaggio iniziale di questo processo può essere eseguito eseguendo il seguente script di Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="86203-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

```PowerShell
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
```

<span data-ttu-id="86203-108">Tieni presente che il nome dell'area di autenticazione per un tenant è in genere diverso rispetto al nome dell'organizzazione; il nome Realm è infatti quasi sempre uguale all'ID tenant.</span><span class="sxs-lookup"><span data-stu-id="86203-108">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID.</span></span> <span data-ttu-id="86203-109">Per questo motivo, la prima riga nello script viene usata per restituire il valore della proprietà ID tenant per il tenant specificato (in questo caso fabrikam.com) e quindi assegnare il nome alla variabile $TenantId:</span><span class="sxs-lookup"><span data-stu-id="86203-109">Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="86203-110">Per eseguire questo script, è necessario aver installato il modulo di PowerShell di Skype for business online e connettersi al tenant con questo modulo.</span><span class="sxs-lookup"><span data-stu-id="86203-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="86203-111">Se non sono stati installati questi cmdlet, lo script non riuscirà perché il cmdlet Get-CsTenant non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="86203-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="86203-112">Al termine dell'esecuzione dello script, è necessario configurare una relazione di trust tra Skype for Business Server e il server di autorizzazione e una seconda relazione di trust tra Exchange 2013/2016 e il server di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="86203-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="86203-113">Questa operazione può essere eseguita solo usando i cmdlet dei Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="86203-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="86203-114">Se non sono stati installati i cmdlet dei Microsoft Online Services, sarà necessario installarlo dal repository di PowerShell con il cmdlet `install-module MSOnline`.</span><span class="sxs-lookup"><span data-stu-id="86203-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="86203-115">Informazioni dettagliate per l'installazione e l'uso del modulo Microsoft Online Services si trovano nel sito Web di Office 365.</span><span class="sxs-lookup"><span data-stu-id="86203-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="86203-116">Queste istruzioni spiegano anche come configurare Single Sign-on, Federation e la sincronizzazione tra Office 365 e Active Directory.</span><span class="sxs-lookup"><span data-stu-id="86203-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 



<span data-ttu-id="86203-117">Dopo aver configurato Office 365 e dopo aver creato le entità di servizio di Office 365 per Skype for Business Server ed Exchange 2013, sarà necessario registrare le credenziali con queste entità di servizio.</span><span class="sxs-lookup"><span data-stu-id="86203-117">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="86203-118">Per eseguire questa operazione, devi prima ottenere un certificato X. 509 Base64 salvato come. File CER.</span><span class="sxs-lookup"><span data-stu-id="86203-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="86203-119">Questo certificato verrà quindi applicato alle entità di servizio di Office 365.</span><span class="sxs-lookup"><span data-stu-id="86203-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="86203-120">Dopo aver ottenuto il certificato X. 509, aprire la console di PowerShell e importare il modulo Microsoft online di Windows PowerShell contenente i cmdlet che possono essere usati per gestire le entità di servizio:</span><span class="sxs-lookup"><span data-stu-id="86203-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```PowerShell
Import-Module MSOnline
```

<span data-ttu-id="86203-121">Quando il modulo è stato importato, digitare il comando seguente e quindi premere INVIO per connettersi a Office 365:</span><span class="sxs-lookup"><span data-stu-id="86203-121">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

```PowerShell
Connect-MsolService
```

<span data-ttu-id="86203-122">Dopo aver premuto INVIO, verrà visualizzata una finestra di dialogo credenziali.</span><span class="sxs-lookup"><span data-stu-id="86203-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="86203-123">Immettere il nome utente e la password di Office 365 nella finestra di dialogo e quindi fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="86203-123">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="86203-124">Non appena si è connessi a Office 365, è possibile eseguire il comando seguente per restituire informazioni sulle entità di servizio:</span><span class="sxs-lookup"><span data-stu-id="86203-124">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```PowerShell
Get-MsolServicePrincipal
```

<span data-ttu-id="86203-125">È consigliabile recuperare informazioni simili a quelle per tutte le entità di servizio:</span><span class="sxs-lookup"><span data-stu-id="86203-125">You should get back information similar to this for all your service principals:</span></span>

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

<span data-ttu-id="86203-126">Il passaggio successivo consiste nell'importare, codificare e assegnare il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="86203-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="86203-127">Per importare e codificare il certificato, usare i comandi di Windows PowerShell seguenti, in modo da specificare il percorso completo del file. File CER quando si chiama il metodo di importazione:</span><span class="sxs-lookup"><span data-stu-id="86203-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="86203-128">Dopo aver importato e codificato il certificato, è possibile assegnare il certificato alle entità di servizio di Office 365.</span><span class="sxs-lookup"><span data-stu-id="86203-128">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="86203-129">A questo scopo, USA prima di tutto Get-MsolServicePrincipal viene per recuperare il valore della proprietà AppPrincipalId sia per Skype for Business Server che per le entità dei servizi di Microsoft Exchange. il valore della proprietà AppPrincipalId verrà usato per identificare l'entità del servizio a cui è stato assegnato il certificato.</span><span class="sxs-lookup"><span data-stu-id="86203-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="86203-130">Con il valore della proprietà AppPrincipalId per Skype for Business Server in mano, usa il comando seguente per assegnare il certificato alla versione Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="86203-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="86203-131">Devi quindi ripetere il comando, questa volta usando il valore della proprietà AppPrincipalId per Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="86203-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="86203-132">Se in seguito è necessario eliminare il certificato, ad esempio se è scaduto, è possibile eseguire prima di tutto il recupero di KeyId per il certificato:</span><span class="sxs-lookup"><span data-stu-id="86203-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="86203-133">Il comando restituirà dati come questo:</span><span class="sxs-lookup"><span data-stu-id="86203-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="86203-134">È quindi possibile eliminare il certificato usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="86203-134">You can then delete the certificate by using a command similar to this:</span></span>

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="86203-135">Oltre ad assegnare un certificato, è necessario configurare anche l'entità del servizio Exchange Online e configurare la versione locale degli URL dei servizi Web esterni di Skype for Business Server come entità di servizio di Office 365.</span><span class="sxs-lookup"><span data-stu-id="86203-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="86203-136">Questa operazione può essere eseguita eseguendo i due comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="86203-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="86203-137">Nell'esempio seguente, Pool1ExternalWebFQDN.contoso.com è l'URL dei servizi Web esterni per il pool di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="86203-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="86203-138">È consigliabile ripetere questi passaggi per aggiungere tutti gli URL dei servizi Web esterni nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="86203-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
