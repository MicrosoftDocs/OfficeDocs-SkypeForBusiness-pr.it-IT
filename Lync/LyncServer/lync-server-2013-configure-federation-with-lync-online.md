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
ms.openlocfilehash: 2ce178e57b850ee4003f2596ee075d68ea14e00a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a>Configurare la Federazione di Lync Server 2013 con Lync Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-08-15_

Seguire la procedura descritta in questa sezione per configurare l'interoperabilità tra la distribuzione locale e Skype for business online.

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Configurare il servizio perimetrale locale per la Federazione con Skype for business online

La federazione consente agli utenti della distribuzione locale di comunicare con gli utenti di Microsoft 365 o Office 365 nell'organizzazione. Per configurare la Federazione, eseguire i cmdlet seguenti:

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>Configurare il tenant di Skype for business online per uno spazio di indirizzi SIP condiviso

Un indirizzo SIP (Session Initiation Protocol) è un identificatore univoco per ogni utente in una rete, simile a un numero di telefono o a un indirizzo di posta elettronica. Prima di provare a spostare gli utenti di Lync da locale a Skype for business online, è necessario configurare l'organizzazione Microsoft 365 o Office 365 per condividere lo spazio degli indirizzi SIP (Session Initiation Protocol) condiviso con la distribuzione locale. Se questa operazione non è configurata, è possibile che venga visualizzato il messaggio di errore seguente:

Move-CsUser: HostedMigration fault: Error = (510), Description = (il tenant di questo utente non è abilitato per lo spazio di indirizzi SIP condiviso).

Per configurare uno spazio di indirizzi SIP condiviso, stabilire una sessione remota di PowerShell con Skype for business online e quindi eseguire il cmdlet seguente:
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
Per creare una sessione remota di PowerShell con Skype for business online, è necessario prima di tutto installare il modulo Skype for business online per Windows PowerShell, che è possibile ottenere qui: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) .

Dopo aver installato il modulo, è possibile stabilire una sessione remota con i cmdlet seguenti:

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

Per ulteriori informazioni su come stabilire una sessione remota di PowerShell con Skype for business online, vedere [Connecting to Skype for business online tramite Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

Per ulteriori informazioni sull'utilizzo del modulo di PowerShell per Skype for business online, vedere [using Windows PowerShell to Manage Skype for business online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
