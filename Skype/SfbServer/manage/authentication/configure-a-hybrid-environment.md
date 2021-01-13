---
title: Configurare l'autenticazione da server a server per un ambiente ibrido di Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: "Sintesi: configurare l'autenticazione da server a server per un ambiente ibrido di Skype for Business Server."
ms.openlocfilehash: 6f4e11b54f0292b1ccb91ab486e2e638a4dcceb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828486"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="717ad-103">Configurare l'autenticazione da server a server per un ambiente ibrido di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="717ad-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="717ad-104">**Riepilogo:** Configurare l'autenticazione da server a server per l'ambiente ibrido di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="717ad-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="717ad-105">In una configurazione ibrida, alcuni utenti sono ospitati in un'installazione locale di Skype for Business Server, mentre altri utenti sono ospitati nella versione Microsoft 365 o Office 365 di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="717ad-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Microsoft 365 or Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="717ad-106">Per configurare l'autenticazione da server a server in un ambiente ibrido, è innanzitutto necessario configurare l'installazione locale di Skype for Business Server in modo che consideri attendibile il server di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="717ad-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the authorization server.</span></span> <span data-ttu-id="717ad-107">Il passaggio iniziale di questo processo può essere eseguito eseguendo il seguente script per la gestione di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="717ad-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

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

<span data-ttu-id="717ad-p102">Tenere a mente che il nome dell'area di autenticazione di un tenant è solitamente diverso da quello dell'organizzazione. Quasi mai il nome dell'area di autenticazione corrisponde a quello dell'ID del tenant. Per questo motivo, la prima riga dello script è utilizzata per restituire il valore della proprietà TenantId del tenant specificato (in questo caso, fabrikam.com) e per poi assegnare il nome alla variabile $TenantId:</span><span class="sxs-lookup"><span data-stu-id="717ad-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="717ad-110">Per eseguire questo script, è necessario aver installato il modulo di PowerShell per Skype for business online e connettersi al tenant con questo modulo.</span><span class="sxs-lookup"><span data-stu-id="717ad-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="717ad-111">Se i cmdlet non sono stati installati, lo script avrà esito negativo perché il cmdlet Get-CsTenant non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="717ad-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="717ad-112">Al termine dell'esecuzione dello script, è necessario configurare una relazione di trust tra Skype for Business Server e il server di autorizzazione, nonché una seconda relazione di trust tra Exchange 2013/2016 e il server di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="717ad-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="717ad-113">È possibile farlo soltanto attraverso i cmdlet di Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="717ad-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="717ad-114">Se i cmdlet dei Microsoft Online Services non sono stati installati, sarà necessario installarlo dal repository di PowerShell con il cmdlet `install-module MSOnline` .</span><span class="sxs-lookup"><span data-stu-id="717ad-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="717ad-115">Informazioni dettagliate per l'installazione e l'utilizzo del modulo dei Microsoft Online Services sono disponibili nel sito Web Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="717ad-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Microsoft 365 web site.</span></span> <span data-ttu-id="717ad-116">Queste istruzioni illustrano inoltre come configurare il servizio Single Sign-on, la Federazione e la sincronizzazione tra Microsoft 365 o Office 365 e Active Directory.</span><span class="sxs-lookup"><span data-stu-id="717ad-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Microsoft 365 or Office 365 and Active Directory.</span></span> 



<span data-ttu-id="717ad-117">Dopo aver configurato Microsoft 365 o Office 365 e dopo aver creato Microsoft 365 o le entità di servizio di Office 365 per Skype for Business Server e Exchange 2013, sarà necessario registrare le credenziali con queste entità di servizio.</span><span class="sxs-lookup"><span data-stu-id="717ad-117">After you have configured Microsoft 365 or Office 365, and after you have created Microsoft 365 or Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="717ad-118">Per eseguire questa operazione, è innanzitutto necessario ottenere un certificato X. 509 Base64 salvato come a. File CER.</span><span class="sxs-lookup"><span data-stu-id="717ad-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="717ad-119">Questo certificato verrà quindi applicato alle entità di servizio Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="717ad-119">This certificate will then be applied to the Microsoft 365 or Office 365 service principals.</span></span>

<span data-ttu-id="717ad-120">Dopo aver ottenuto il certificato X. 509, aprire console PowerShell e importare il modulo Microsoft online di Windows PowerShell contenente i cmdlet che è possibile utilizzare per gestire le entità di servizio:</span><span class="sxs-lookup"><span data-stu-id="717ad-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```PowerShell
Import-Module MSOnline
```

<span data-ttu-id="717ad-121">Quando il modulo è stato importato, digitare il comando seguente e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="717ad-121">When the module has been imported, type the following command and then press ENTER:</span></span>

```PowerShell
Connect-MsolService
```

<span data-ttu-id="717ad-122">A questo punto, viene visualizzata una finestra di dialogo delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="717ad-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="717ad-123">Immettere il nome utente e la password di Microsoft 365 o Office 365 nella finestra di dialogo e quindi fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="717ad-123">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="717ad-124">Non appena si è connessi a Microsoft 365 o Office 365, è possibile eseguire il comando seguente per restituire le informazioni sulle entità di servizio:</span><span class="sxs-lookup"><span data-stu-id="717ad-124">As soon as you are connected to Microsoft 365 or Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```PowerShell
Get-MsolServicePrincipal
```

<span data-ttu-id="717ad-125">Si dovrebbero ottenere informazioni simili alle seguenti, per tutti i nomi del servizio principale:</span><span class="sxs-lookup"><span data-stu-id="717ad-125">You should get back information similar to this for all your service principals:</span></span>

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

<span data-ttu-id="717ad-126">Il passaggio successivo consiste nell'importazione, codifica e assegnazione del certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="717ad-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="717ad-127">Per importare e codificare il certificato, utilizzare i seguenti comandi di Windows PowerShell, assicurandosi di specificare il percorso completo del file. File CER quando si chiama il metodo Import:</span><span class="sxs-lookup"><span data-stu-id="717ad-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

<span data-ttu-id="717ad-128">Dopo che il certificato è stato importato e codificato, è possibile assegnare il certificato alle entità di servizio Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="717ad-128">After the certificate has been imported and encoded, you can then assign the certificate to your Microsoft 365 or Office 365 service principals.</span></span> <span data-ttu-id="717ad-129">A tale scopo, utilizzare prima la Get-MsolServicePrincipal per recuperare il valore della proprietà AppPrincipalId sia per le entità di servizio Skype for Business Server che di Microsoft Exchange. il valore della proprietà AppPrincipalId verrà utilizzato per identificare l'entità di servizio a cui è assegnato il certificato.</span><span class="sxs-lookup"><span data-stu-id="717ad-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="717ad-130">Con il valore della proprietà AppPrincipalId per Skype for Business Server in mano, utilizzare il seguente comando per assegnare il certificato alla versione di Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="717ad-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="717ad-131">È quindi necessario ripetere il comando, stavolta utilizzando il valore della proprietà AppPrincipalId per Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="717ad-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="717ad-132">Se in seguito è necessario eliminare il certificato, ad esempio se è scaduto, è possibile farlo recuperando prima il KeyId per il certificato:</span><span class="sxs-lookup"><span data-stu-id="717ad-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="717ad-133">Il comando restituisce dati simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="717ad-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="717ad-134">È possibile eliminare il certificato utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="717ad-134">You can then delete the certificate by using a command similar to this:</span></span>

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="717ad-135">Oltre all'assegnazione di un certificato, è necessario configurare anche l'entità servizio Exchange Online e configurare la versione locale degli URL dei servizi Web esterni di Skype for Business Server come entità di servizio Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="717ad-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as a Microsoft 365 or Office 365 service principal.</span></span> <span data-ttu-id="717ad-136">Questa operazione può essere eseguita eseguendo i due comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="717ad-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="717ad-137">Nell'esempio seguente, Pool1ExternalWebFQDN.contoso.com è l'URL dei servizi Web esterni per il pool di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="717ad-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="717ad-138">È necessario ripetere questi passaggi per aggiungere tutti gli URL dei servizi Web esterni nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="717ad-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
