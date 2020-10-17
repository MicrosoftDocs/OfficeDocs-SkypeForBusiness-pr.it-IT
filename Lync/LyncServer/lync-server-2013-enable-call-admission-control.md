---
title: 'Lync Server 2013: abilitare il controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e129e109a62006d72b8b1db44c28effa8911e6c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528763"
---
# <a name="enable-call-admission-control-in-lync-server-2013"></a>Abilitare il controllo di ammissione di chiamata in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Dopo aver configurato le impostazioni di rete per la distribuzione del servizio Controllo di ammissione di chiamata, è necessario abilitare il servizio per rendere effettivi i criteri relativi alla larghezza di banda.

Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:

  - [Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a>Per abilitare il servizio Controllo di ammissione di chiamata tramite Management Shell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet Set-CsNetworkConfiguration per abilitare il servizio Controllo di ammissione di chiamata nella rete. Ad esempio, eseguire:
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    Se si desidera disabilitare il servizio Controllo di ammissione di chiamata nella rete, eseguire quanto segue:
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a>Per abilitare il servizio Controllo di ammissione di chiamata tramite il Pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.

3.  Fare clic sul pulsante di spostamento **Globale**.

4.  Fare clic su **Globale** nell'elenco e quindi scegliere **Mostra dettagli** dal menu **Modifica**.

5.  Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita il controllo di ammissione di chiamata**.
    
    <div>
    

    > [!NOTE]  
    > Se si desidera disabilitare il servizio Controllo di ammissione di chiamata in tutta la distribuzione, deselezionare questa casella di controllo.

    
    </div>

6.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

