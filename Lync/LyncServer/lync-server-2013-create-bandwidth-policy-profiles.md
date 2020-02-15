---
title: 'Lync Server 2013: creare profili di criteri di larghezza di banda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea1e44f7c8c0d81757d6d10a63194de7c0d12c08
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a>Creare profili di criteri di larghezza di banda in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

I *criteri di larghezza di banda* definiscono restrizioni per l'utilizzo della larghezza di banda per le modalità audio e video in tempo reale. I criteri di larghezza di banda vengono applicati a *profili di criteri di larghezza di banda*, che possono essere a loro volta applicati a più siti di rete per il controllo di ammissione di chiamata.

Per le linee guida relative ai limiti della larghezza di banda che è necessario impostare nella distribuzione di CAC, vedere [definizione dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) nella documentazione relativa alla pianificazione.

Per informazioni dettagliate sull'utilizzo di criteri di larghezza di banda e profili di criteri, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:

  - [New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

I criteri di esempio creati nella procedura seguente impostano limiti per il traffico audio e il traffico video complessivi e per le sessioni audio e le sessioni video individuali. Ad esempio, il profilo\_dei criteri di larghezza di banda del collegamento di 5 MB imposta i seguenti limiti:

  - Limite audio: 2.000 kbps

  - Limite sessione audio: 200 kbps

  - Limite video: 1.400 kbps

  - Limite sessione video: 700 kbps

<div class=" ">


> [!NOTE]  
> Il valore minimo per il limite di una sessione audio è 40 kbps. Il valore minimo per il limite di una sessione video è 100 kbps.



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a>Per creare profili di criteri di larghezza di banda mediante Management Shell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Per ogni profilo di criteri di larghezza di banda che si desidera creare eseguire il cmdlet New-CsNetworkBandwidthPolicyProfile. Ad esempio, eseguire:
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a>Per creare profili di criteri di larghezza di banda mediante il Pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **Configurazione rete**.

3.  Fare clic sul pulsante di spostamento **Profilo criteri**.

4.  Fare clic su **Nuovo**.

5.  Nella pagina **Nuovo profilo criteri** fare clic su **Nome** e quindi digitare un nome per il profilo di criteri di larghezza di banda.

6.  Fare clic su **Limite audio** e quindi digitare il numero massimo di kbps consentiti per tutte le sessioni audio nel loro insieme.

7.  Fare clic su **Limite sessione audio** e quindi digitare il numero massimo di kbps consentiti per ogni singola sessione audio.

8.  Fare clic su **Limite video** e quindi digitare il numero massimo di kbps consentiti per tutte le sessioni video nel loro insieme.

9.  Fare clic su **Limite sessione video** e quindi digitare il numero massimo di kbps consentiti per ogni singola sessione video.

10. Se si desidera, fare clic su **Descrizione** e quindi digitare ulteriori informazioni per descrivere il profilo di criteri di larghezza di banda.

11. Fare clic su **Commit**.

12. Per completare la creazione dei profili di criteri di larghezza di banda, ripetere i passaggi da 4 a 11 con le impostazioni per gli altri profili.

</div>

</div>

<span> </span>

</div>

</div>

</div>

