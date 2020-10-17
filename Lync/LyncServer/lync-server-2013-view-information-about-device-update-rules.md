---
title: 'Lync Server 2013: visualizzare le informazioni sulle regole di aggiornamento dei dispositivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79fef5d58116da6b8cbc07ce2b16f3dd4f6b28ac
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506383"
---
# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a>Visualizzare informazioni sulle regole di aggiornamento dei dispositivi in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Visualizzare i dettagli sulle regole di aggiornamento dei dispositivi che sono già state importate, tra cui il tipo, il modello e la marca dei dispositivi a cui si applica l'aggiornamento; versione e tipo di aggiornamento; e le impostazioni locali e il pool per l'aggiornamento. Le informazioni sono disponibili per tutte le regole di aggiornamento dei dispositivi importate, ovvero quelle che sono in attesa di approvazione, distribuite (approvate), richiamate (ripristinate) e quelle che si è deciso di non utilizzare (reset). Accedere a queste informazioni dal pannello di controllo di Lync Server o Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'importazione, l'approvazione, la reimpostazione, il ripristino e la rimozione di regole, vedere gli argomenti elencati in informazioni sulle <A href="lync-server-2013-device-update-rules.md">regole di aggiornamento dei dispositivi in Lync Server 2013</A>.



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a>Per visualizzare le regole di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento **Aggiorna dispositivo** . Le regole importate sono elencate nella pagina **aggiornamento dispositivi** .

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle regole di aggiornamento dei dispositivi tramite i cmdlet di Windows PowerShell

Informazioni dettagliate su tutte le regole di aggiornamento dei dispositivi possono essere visualizzate anche utilizzando Windows PowerShell e il cmdlet **Get-CsDeviceUpdateRule** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a>Per visualizzare tutte le regole di aggiornamento dei dispositivi

  - Il comando seguente restituisce informazioni su tutte le regole di aggiornamento dei dispositivi configurate per l'utilizzo nell'organizzazione:
    
        Get-CsDeviceUpdateRule
    
    Il comando restituisce informazioni simili alle seguenti per ogni regola di aggiornamento del dispositivo:
    
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

  - Per visualizzare le regole di aggiornamento dei dispositivi in un computer specifico, utilizzare il parametro Filter seguito dall'identità del server e dal carattere jolly ( \* ). Ad esempio:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

