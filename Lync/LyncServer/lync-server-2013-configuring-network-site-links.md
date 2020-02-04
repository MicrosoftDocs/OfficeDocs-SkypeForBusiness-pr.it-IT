---
title: 'Lync Server 2013: configurazione di collegamenti ai siti di rete'
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
ms.openlocfilehash: e379a8195dd0a50d97a514307ac594908be4736c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>Configurazione di collegamenti ai siti di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

All'interno di una configurazione di controllo di ammissione chiamata (CAC), è possibile creare criteri intersito di rete che definiscono le limitazioni della larghezza di banda tra i siti direttamente collegati. Quando i siti di rete condividono un collegamento diretto, è possibile definire limitazioni della larghezza di banda per le connessioni audio e video tra questi due siti. Non è possibile usare il pannello di controllo di Lync Server per configurare i criteri del sito di rete, questo può essere eseguito solo usando i cmdlet di Lync Server Management Shell. È possibile creare, modificare e rimuovere un collegamento al sito di rete (noto anche come criterio intersito di rete) da Lync Server Management Shell.

<div>

## <a name="to-create-a-network-site-link"></a>Per creare un collegamento al sito di rete

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Dal prompt dei comandi digitare il comando seguente, sostituendo i valori validi per la configurazione:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Questo esempio crea un nuovo collegamento di sito di rete\_denominato Reno Portland che imposta le limitazioni della larghezza di banda tra i siti di rete Reno e Portland. I siti di rete e il profilo dei criteri di larghezza di banda devono già esistere prima di eseguire questo comando.

Per una descrizione dettagliata dei parametri, vedere [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) nella documentazione di Lync Server Management Shell. Per recuperare un elenco di profili dei criteri di larghezza di banda che possono essere applicati al collegamento al sito di rete, chiama il cmdlet **Get-CsNetworkBandwidthPolicyProfile** . Per informazioni dettagliate, vedere [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) nella documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>Per modificare un collegamento al sito di rete

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Utilizzare il cmdlet **set-CsNetworkInterSitePolicy** per modificare le proprietà di un collegamento al sito di rete specifico. È possibile modificare uno o entrambi i siti connessi e modificare il profilo dei criteri di larghezza di banda associato al collegamento. Ecco un esempio di modifica del profilo dei criteri di larghezza di banda di un collegamento\_di sito denominato Reno Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Per una descrizione dettagliata dei parametri, vedere [set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) nella documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>Per eliminare un collegamento al sito di rete

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Utilizzare il cmdlet **Remove-CsNetworkInterSitePolicy** per rimuovere un collegamento al sito di rete. L'esempio seguente elimina il collegamento\_al sito network di Reno Portland:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Per una descrizione dettagliata dei parametri, vedere [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) nella documentazione di Lync Server Management Shell.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Cmdlet di controllo dell'ammissione alle chiamate in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)  


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

