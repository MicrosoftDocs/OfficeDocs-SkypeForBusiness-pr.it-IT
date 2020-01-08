---
title: 'Lync Server 2013: creare profili dei criteri di larghezza di banda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69aa99d94843c6daa1483911325d45ede0a39f4a
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40981127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a>Creare profili dei criteri di larghezza di banda in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

I *criteri di larghezza di banda* definiscono le limitazioni dell'utilizzo della larghezza di banda per le modalità audio e video in tempo reale. I criteri di larghezza di banda vengono applicati ai *profili dei criteri di larghezza di banda*, che possono essere applicati a più siti di rete per il controllo ammissione chiamata.

Per le linee guida sui limiti della larghezza di banda da impostare nella distribuzione di CAC, vedere [definizione dei requisiti per il controllo dell'ammissione delle chiamate in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) nella documentazione relativa alla pianificazione.

Per informazioni dettagliate su come usare i criteri di larghezza di banda e i profili dei criteri, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:

  - [New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

I criteri di esempio creati nella procedura seguente impostano i limiti per il traffico audio globale, le singole sessioni audio, il traffico video complessivo e le singole sessioni video. Ad esempio, il profilo\_dei criteri di larghezza di banda collegamento di MB imposta i limiti seguenti:

  - Limite audio: 2.000 Kbps

  - Limite della sessione audio: 200 Kbps

  - Limite video: 1.400 kbps

  - Limite sessione video: 700 Kbps

<div class=" ">


> [!NOTE]  
> Il valore limite minimo della sessione audio è 40 Kbps. Il valore limite minimo della sessione video è di 100 kbps.



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a>Per creare profili dei criteri di larghezza di banda tramite Management Shell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Per ogni profilo dei criteri di larghezza di banda che si vuole creare, eseguire il cmdlet New-CsNetworkBandwidthPolicyProfile. Ad esempio, eseguire:
    
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

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a>Per creare profili dei criteri di larghezza di banda tramite il pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.

3.  Fare clic sul pulsante di spostamento del **profilo dei criteri** .

4.  Fare clic su **nuovo**.

5.  Nella pagina **nuovo profilo dei criteri** fare clic su **nome** e quindi digitare un nome per il profilo dei criteri di larghezza di banda.

6.  Fare clic su **limite audio**e quindi digitare il numero massimo di kbps da consentire per tutte le sessioni audio combinate.

7.  Fare clic su **limite sessione audio**e quindi digitare il numero massimo di kbps da consentire per ogni singola sessione audio.

8.  Fare clic su **limite video**e quindi digitare il numero massimo di kbps da consentire per tutte le sessioni video combinate.

9.  Fare clic su **limite sessione video**e quindi digitare il numero massimo di kbps da consentire per ogni singola sessione video.

10. Facoltativamente, fare clic su **Descrizione**e quindi digitare altre informazioni per descrivere il profilo dei criteri di larghezza di banda.

11. Fare clic su **Commit**.

12. Per completare la creazione di profili dei criteri di larghezza di banda per la topologia, ripetere i passaggi da 4 a 11 con impostazioni per altri profili dei criteri di larghezza

</div>

</div>

<span> </span>

</div>

</div>

</div>

