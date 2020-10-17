---
title: 'Lync Server 2013: configurare la Federazione con Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfeffc8a72d26167b9771e6437d21ba55c8f5636
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525953"
---
# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a><span data-ttu-id="efcd1-102">Configurare la Federazione di Lync Server 2013 con Lync Online</span><span class="sxs-lookup"><span data-stu-id="efcd1-102">Configure federation of Lync Server 2013 with Lync Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efcd1-103">_**Ultimo argomento modificato:** 2016-08-15_</span><span class="sxs-lookup"><span data-stu-id="efcd1-103">_**Topic Last Modified:** 2016-08-15_</span></span>

<span data-ttu-id="efcd1-104">Seguire la procedura descritta in questa sezione per configurare l'interoperabilità tra la distribuzione locale e Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="efcd1-104">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="efcd1-105">Configurare il servizio perimetrale locale per la Federazione con Skype for business online</span><span class="sxs-lookup"><span data-stu-id="efcd1-105">Configure Your On-Premises Edge Service for Federation with Skype for Business Online</span></span>

<span data-ttu-id="efcd1-106">La federazione consente agli utenti della distribuzione locale di comunicare con gli utenti di Microsoft 365 o Office 365 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="efcd1-106">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="efcd1-107">Per configurare la Federazione, eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="efcd1-107">To configure federation, run the following cmdlets:</span></span>

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="efcd1-108">Configurare il tenant di Skype for business online per uno spazio di indirizzi SIP condiviso</span><span class="sxs-lookup"><span data-stu-id="efcd1-108">Configure Your Skype for Business Online Tenant for a Shared SIP Address Space</span></span>

<span data-ttu-id="efcd1-109">Un indirizzo SIP (Session Initiation Protocol) è un identificatore univoco per ogni utente in una rete, simile a un numero di telefono o a un indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="efcd1-109">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="efcd1-110">Prima di provare a spostare gli utenti di Lync da locale a Skype for business online, è necessario configurare l'organizzazione Microsoft 365 o Office 365 per condividere lo spazio degli indirizzi SIP (Session Initiation Protocol) condiviso con la distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="efcd1-110">Before you try to move Lync users from on-premises to Skype for Business Online, you’ll need to configure your Microsoft 365 or Office 365 organization to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="efcd1-111">Se questa operazione non è configurata, è possibile che venga visualizzato il messaggio di errore seguente:</span><span class="sxs-lookup"><span data-stu-id="efcd1-111">If this is not configured, you may see the following error message:</span></span>

<span data-ttu-id="efcd1-112">Move-CsUser: HostedMigration fault: Error = (510), Description = (il tenant di questo utente non è abilitato per lo spazio di indirizzi SIP condiviso).</span><span class="sxs-lookup"><span data-stu-id="efcd1-112">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user’s tenant is not enabled for shared sip address space.)</span></span>

<span data-ttu-id="efcd1-113">Per configurare uno spazio di indirizzi SIP condiviso, stabilire una sessione remota di PowerShell con Skype for business online e quindi eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="efcd1-113">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
<span data-ttu-id="efcd1-114">Per creare una sessione remota di PowerShell con Skype for business online, è necessario prima di tutto installare il modulo Skype for business online per Windows PowerShell, che è possibile ottenere qui: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) .</span><span class="sxs-lookup"><span data-stu-id="efcd1-114">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>

<span data-ttu-id="efcd1-115">Dopo aver installato il modulo, è possibile stabilire una sessione remota con i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="efcd1-115">After you install the module, you can establish a remote session with the following cmdlets:</span></span>

   ```powershell
    Import-Module LyncOnlineConnector
   ```

   ```powershell
    $cred = Get-Credential
   ``` 

   ```powershell
    $CSSession = New-CsOnlineSession -Credential $cred
   ```

   ```powershell
    Import-PSSession $CSSession -AllowClobber
   ```

<span data-ttu-id="efcd1-116">Per ulteriori informazioni su come stabilire una sessione remota di PowerShell con Skype for business online, vedere [Connecting to Skype for business online tramite Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="efcd1-116">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Skype for Business Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

<span data-ttu-id="efcd1-117">Per ulteriori informazioni sull'utilizzo del modulo di PowerShell per Skype for business online, vedere [using Windows PowerShell to Manage Skype for business online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="efcd1-117">For more information about using the Skype for Business Online PowerShell module, see [Using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="efcd1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efcd1-118">See Also</span></span>


[<span data-ttu-id="efcd1-119">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="efcd1-119">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
