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
ms.openlocfilehash: 36a85ed29f6bf4838428af302904d80a2f792388
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a>Reimpostare una regola di aggiornamento del dispositivo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Se non si è soddisfatti del funzionamento di un aggiornamento nei dispositivi di test, è possibile reimpostare la regola di aggiornamento del dispositivo, che rimuove lo stato in sospeso della regola e disinstalla l'aggiornamento dai dispositivi di test.

È possibile rimuovere una regola di aggiornamento del dispositivo usando il pannello di controllo di Lync Server o Windows PowerShell.

<div>


> [!NOTE]  
> Per disinstallare una regola già approvata, ovvero distribuita, ripristinarla. Per informazioni dettagliate, vedere <A href="lync-server-2013-restore-a-device-update-rule.md">ripristinare una regola di aggiornamento dei dispositivi in Lync Server 2013</A>.



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a>Per reimpostare una regola di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento **aggiornamento dispositivi** .

4.  Nella pagina **Update Device** eseguire una delle operazioni seguenti:
    
      - Per reimpostare una regola, selezionare la regola che si vuole reimpostare.
    
      - Per reimpostare tutte le regole, scegliere **Seleziona tutto**dal menu **modifica** .
    
      - Per reimpostare tutte le regole per una sola marca, usare il menu colonna **marca** .

5.  Fare clic su **azione**e quindi su **Annulla aggiornamenti in sospeso**.
    
    <div>
    

    > [!TIP]  
    > Se si è certi di non voler più implementare le regole di aggiornamento dei dispositivi annullate, è consigliabile eliminarle. Per informazioni dettagliate, vedere <A href="lync-server-2013-remove-a-device-update-rule.md">rimuovere una regola di aggiornamento dei dispositivi in Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Reimpostazione di una regola di aggiornamento dei dispositivi con i cmdlet di Windows PowerShell

Le regole di aggiornamento dei dispositivi possono essere reimpostate anche tramite Windows PowerShell e il cmdlet **Reset-CsDeviceUpdateRule** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Lync Server 2010 con Remote PowerShell" at.



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a>Per reimpostare una regola di aggiornamento di un dispositivo specifico in un server

  - Il comando seguente reimposta la regola di aggiornamento del dispositivo d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 sul server Web atl-cs-001.litwareinc.com:
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a>Per reimpostare tutte le regole di aggiornamento dei dispositivi in un server

  - Questo comando Reimposta tutte le regole di aggiornamento dei dispositivi sul server Web atl-cs-001.litwareinc.com:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a>Per reimpostare tutte le regole di aggiornamento dei dispositivi con un marchio specifico

  - In questo esempio tutti gli aggiornamenti del dispositivo in tutta l'organizzazione che hanno un marchio uguale a Microsoft vengono reimpostati:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Approvare una regola di aggiornamento del dispositivo in Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

