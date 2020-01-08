---
title: 'Lync Server 2013: visualizzare le informazioni sulle regole di aggiornamento dei dispositivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d873cbd80e599313b60a57cfc28eb9752d85ef66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a>Visualizzare informazioni sulle regole di aggiornamento dei dispositivi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Visualizzare i dettagli sulle regole di aggiornamento dei dispositivi già importate, incluso il tipo, il modello e la marca dei dispositivi a cui si applica l'aggiornamento; versione e tipo di aggiornamento; e impostazioni locali e pool per l'aggiornamento. Le informazioni sono disponibili per tutte le regole di aggiornamento dei dispositivi importate, ovvero quelle in attesa di approvazione, distribuite (approvate), richiamate (ripristinate) e quelle che hai deciso di non usare (Reimposta). Accedere a queste informazioni dal pannello di controllo di Lync Server o da Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate su come importare, approvare, reimpostare, ripristinare e rimuovere regole, vedere gli argomenti elencati in <A href="lync-server-2013-device-update-rules.md">regole di aggiornamento dei dispositivi in Lync Server 2013</A>.



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a>Per visualizzare le regole di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento **aggiornamento dispositivi** . Le regole importate sono elencate nella pagina di **aggiornamento del dispositivo** .

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle regole di aggiornamento dei dispositivi con i cmdlet di Windows PowerShell

Informazioni dettagliate su tutte le regole di aggiornamento dei dispositivi possono essere visualizzate anche tramite Windows PowerShell e il cmdlet **Get-CsDeviceUpdateRule** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Lync Server 2010 con Remote PowerShell" at.



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a>Per visualizzare tutte le regole di aggiornamento dei dispositivi

  - Il comando seguente restituisce informazioni su tutte le regole di aggiornamento dei dispositivi configurate per l'uso nell'organizzazione:
    
        Get-CsDeviceUpdateRule
    
    Il comando restituisce informazioni simili a quelle seguenti per ogni regola di aggiornamento del dispositivo:
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a>Per visualizzare tutte le regole di aggiornamento dei dispositivi in uno specifico server Web

  - Per visualizzare le regole di aggiornamento del dispositivo in un computer specifico, usare il parametro Filter seguito dall'identità del server e dal carattere\*jolly (). Ad esempio:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

