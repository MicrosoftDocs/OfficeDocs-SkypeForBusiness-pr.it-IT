---
title: 'Lync Server 2013: configurazione di collegamenti di sito di rete'
description: 'Lync Server 2013: configurazione di collegamenti di sito di rete.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68b4ecce15b8f3ba5a5717c73a8f97f8a0633b58
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572932"
---
# <a name="configuring-network-site-links-in-lync-server-2013"></a>Configurazione di collegamenti di sito di rete in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

In una configurazione di controllo di ammissione di chiamata è possibile creare criteri intersito di rete che definiscono le limitazioni della larghezza di banda tra i siti collegati direttamente. Se due siti di rete condividono un collegamento diretto, è possibile definire dei limiti della larghezza di banda per le connessioni audio e video tra tali siti. Non è possibile utilizzare il pannello di controllo di Lync Server per configurare i criteri sito di rete, è possibile eseguire questa operazione solo utilizzando i cmdlet di Lync Server Management Shell. È possibile creare, modificare e rimuovere un collegamento di sito di rete (noto anche come criterio tra siti di rete) da Lync Server Management Shell.

<div>

## <a name="to-create-a-network-site-link"></a>Per creare un collegamento di sito di rete

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Al prompt dei comandi digitare il comando seguente, utilizzando valori validi per la configurazione in uso:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    In questo esempio viene creato un nuovo collegamento di sito di rete denominato Reno \_ Portland che imposta le limitazioni della larghezza di banda tra i siti di rete Reno e Portland. Il profilo dei criteri di larghezza di banda e siti di rete deve essere già presente prima dell'esecuzione di questo comando.

Per le descrizioni dettagliate dei parametri, vedere [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) nella documentazione di Lync Server Management Shell. Per ottenere un elenco dei profili dei criteri di larghezza di banda che è possibile applicare al collegamento di sito di rete, chiamare il cmdlet **Get-CsNetworkBandwidthPolicyProfile**. Per informazioni dettagliate, vedere [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) nella documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>Per modificare un collegamento di sito di rete

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Utilizzare il cmdlet **CsNetworkInterSitePolicy Set** per modificare le proprietà di un collegamento di sito di rete specifico. È possibile modificare uno dei siti connessi o entrambi ed è possibile modificare il profilo dei criteri di larghezza di banda associato al collegamento. Di seguito è riportato un esempio di modifica del profilo dei criteri di larghezza di banda di un collegamento di sito denominato Reno \_ Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Per le descrizioni dettagliate dei parametri, vedere [set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) nella documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>Per eliminare un collegamento di sito di rete

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Utilizzare il cmdlet **Remove-CsNetworkInterSitePolicy** per rimuovere un collegamento di sito di rete. Nell'esempio seguente viene eliminato il \_ collegamento al sito di rete di Reno Portland:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Per le descrizioni dettagliate dei parametri, vedere [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) nella documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Cmdlet per il controllo di ammissione di chiamata in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)  


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

