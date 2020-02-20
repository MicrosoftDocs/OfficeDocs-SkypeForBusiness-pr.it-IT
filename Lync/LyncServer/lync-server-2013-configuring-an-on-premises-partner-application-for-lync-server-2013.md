---
title: Configurazione di un'applicazione partner locale per Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring an on-premises partner application for Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48184412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a460b887e161cd1dd89e3953dcfb0c2fce76813
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a>Configurazione di un'applicazione partner locale per Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-04_

Dopo aver assegnato il certificato OAuthTokenIssuer, è necessario configurare le applicazioni partner di Microsoft Lync Server 2013. La procedura per la discussione configura sia Microsoft Exchange Server 2013 che Microsoft SharePoint per fungere da applicazioni partner. Per configurare un'applicazione partner locale, è necessario iniziare copiando lo script di Windows PowerShell seguente e incollando il codice nel blocco note (o in qualsiasi altro editor di testo):

    if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
       {
           Remove-CsPartnerApplication app
       }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
    New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
               }
         }
    
    $shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
            
    if ($shp -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
        }
    else
        {
           if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.sharepoint
      
                 New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
                }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Dopo aver copiato il codice, salvare lo script utilizzando un. Estensione di file PS1, ad esempio C:\\Scripts\\ServerToServerAuth. ps1. Tenere presente che, prima di eseguire lo script, è necessario sostituire gli URL https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 dei http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx metadati e gli URL dei metadati utilizzati rispettivamente dai server Exchange 2013 e SharePoint. Per informazioni su come identificare l'URL dei metadati del prodotto rispettivo, vedere la documentazione del prodotto per Exchange 2013 e SharePoint.

Nell'ultima riga dello script si potrà notare che il cmdlet di Set-CsOAuthConfiguration viene chiamato con questa sintassi:

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Dato che il parametro Realm non è stato utilizzato per la chiamata di Set-CsOAuthConfiguration, l'area di autenticazione verrà impostata automaticamente sul nome di dominio completo (FQDN) dell'organizzazione (ad esempio, litwareinc.com). Se il nome dell'area di autenticazione è diverso dal nome dell'organizzazione, è necessario includere il nome dell'area di autenticazione nel modo seguente:

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

Dopo aver apportato queste modifiche, è possibile eseguire lo script e configurare sia Exchange 2013 che SharePoint come applicazioni partner, eseguendo il file di script all'interno di Lync Server 2013 Management Shell. Ad esempio:

    C:\Scripts\ServerToServerAuth.ps1

Si noti che è possibile eseguire questo script anche se non sono installati sia Exchange 2013 che SharePoint Server:, non si verificherà alcun problema se, ad esempio, si configura SharePoint Server come applicazione partner anche se non è installato SharePoint Server.

Quando si esegue lo script potrebbe essere visualizzato un messaggio di errore simile al seguente:

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

Questo messaggio di errore indica in genere uno di due problemi: 1) uno degli URL specificati nello script non è valido (ovvero uno degli URL dei metadati non è corretto) oppure 2) non è possibile contattare uno degli URL dei metadati. In questi casi, verificare che gli URL siano corretti e accessibili, quindi rieseguire lo script.

Dopo aver creato l'applicazione partner per Lync Server 2013, è necessario configurare Lync Server come applicazione partner per Exchange 2013. È possibile configurare le applicazioni partner per Exchange 2013 eseguendo lo script Configure-EnterprisePartnerApplication. ps1. è sufficiente specificare l'URL dei metadati per Lync Server e indicare che Lync Server è la nuova applicazione partner.

Per configurare Lync Server come applicazione partner per Exchange, aprire Exchange Management Shell ed eseguire un comando simile al seguente.

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

