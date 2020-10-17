---
title: 'Lync Server 2013: reimpostare una regola di aggiornamento del dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24f80dcd0404dfc237d1b63be378f0f333dd975b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511813"
---
# <a name="reset-a-device-update-rule-in-lync-server-2013"></a>Reimpostare una regola di aggiornamento del dispositivo in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Se non si è interessati alla modalità di funzionamento di un aggiornamento sui dispositivi di test, è possibile reimpostare la regola di aggiornamento dei dispositivi, in modo da rimuovere lo stato in sospeso della regola e disinstallare l'aggiornamento dai dispositivi di test.

È possibile rimuovere una regola di aggiornamento dei dispositivi utilizzando il pannello di controllo di Lync Server o Windows PowerShell.

<div>


> [!NOTE]  
> Per disinstallare una regola già approvata (ovvero, srotolata), ripristinarla. Per ulteriori informazioni, vedere <A href="lync-server-2013-restore-a-device-update-rule.md">ripristinare una regola di aggiornamento dei dispositivi in Lync Server 2013</A>.



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a>Per reimpostare una regola di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento **Aggiorna dispositivo** .

4.  Nella pagina **aggiornamento dispositivi** eseguire una delle operazioni seguenti:
    
      - Per reimpostare una regola, selezionare la regola che si desidera reimpostare.
    
      - Per reimpostare tutte le regole, scegliere **Seleziona tutto**dal menu **modifica** .
    
      - Per reimpostare tutte le regole per una marca, utilizzare il menu colonna **marca** .

5.  Fare clic su **azione**e quindi su **Annulla aggiornamenti in sospeso**.
    
    <div>
    

    > [!TIP]  
    > Se si è certi di non voler mai eseguire il rollback delle regole di aggiornamento dei dispositivi che sono state annullate, potrebbe essere necessario eliminarle. Per ulteriori informazioni, vedere <A href="lync-server-2013-remove-a-device-update-rule.md">rimuovere una regola di aggiornamento dei dispositivi in Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Reimpostazione di una regola di aggiornamento dei dispositivi tramite i cmdlet di Windows PowerShell

È possibile reimpostare le regole di aggiornamento dei dispositivi anche utilizzando Windows PowerShell e il cmdlet **Reset-CsDeviceUpdateRule** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a>Per reimpostare una regola di aggiornamento del dispositivo specifica in un server

  - Il seguente comando Reimposta la regola di aggiornamento dei dispositivi d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 sul server Web atl-cs-001.litwareinc.com:
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a>Per reimpostare tutte le regole di aggiornamento dei dispositivi su un server

  - Questo comando consente di reimpostare tutte le regole di aggiornamento dei dispositivi sul server Web atl-cs-001.litwareinc.com:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a>Per reimpostare tutte le regole di aggiornamento dei dispositivi che dispongono di una marca specifica

  - In questo esempio vengono reimpostati tutti gli aggiornamenti del dispositivo nell'organizzazione che dispongono di un marchio uguale a Microsoft:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Approvazione di una regola di aggiornamento del dispositivo in Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

