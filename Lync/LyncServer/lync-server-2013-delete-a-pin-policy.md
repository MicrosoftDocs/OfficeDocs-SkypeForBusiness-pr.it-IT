---
title: 'Lync Server 2013: eliminare un criterio PIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a PIN policy
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48184609
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4c64b5490e53c8ba51f7832cef9ba483b1760d1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525643"
---
# <a name="delete-a-pin-policy-in-lync-server-2013"></a>Eliminare un criterio PIN in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Eseguire la procedura seguente per eliminare criteri PIN.

<div>


> [!NOTE]  
> Non è possibile eliminare criteri PIN globali.



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a>Per eliminare un criterio PIN nel pannello di controllo di Lync Server 2013

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Criteri PIN**.

4.  Nella pagina **Criteri PIN** e nel campo di ricerca digitare il nome, o parte di esso, dei criteri che si desidera eliminare.

5.  Nell'elenco di criteri fare clic sui criteri desiderati, fare clic su **Modifica** e quindi su **Elimina**.

6.  Fare clic su **OK**.

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Rimozione dei criteri del PIN tramite i cmdlet di Windows PowerShell

È possibile eliminare i criteri PIN utilizzando Windows PowerShell e il cmdlet Remove-CsPinPolicy. È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specific-pin-policy"></a>Per rimuovere un criterio PIN specifico

  - Questo comando rimuove il criterio PIN con identità (Identity) RedmondPinPolicy:
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>Per rimuovere tutti i criteri PIN applicati all'ambito del sito

  - Questo comando rimuove tutti i criteri PIN configurati nell'ambito sito:
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>Per rimuovere tutti i criteri PIN che consentono l'utilizzo di modelli comuni

  - Questo comando rimuove tutti i criteri PIN che consentono l'utilizzo di formati comuni:G
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

