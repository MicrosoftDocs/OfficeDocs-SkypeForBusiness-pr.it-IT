---
title: 'Lync Server 2013: creare collegamenti area di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72e8c3d0fd254ba780b91d554402ca38d30f7073
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515563"
---
# <a name="create-network-region-links-in-lync-server-2013"></a>Creare collegamenti area di rete in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Le aree all'interno di una rete sono collegate tramite connettività fisica WAN. Un *collegamento di aree di rete* crea un collegamento tra due aree configurate per Controllo di ammissione di chiamata e imposta i limiti di larghezza di banda per il traffico audio e video tra tali aree.

Per informazioni dettagliate sull'utilizzo dei collegamenti tra aree di rete, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:

  - [New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

Nella topologia di esempio è presente un collegamento tra il Nord America e le aree APAC e un collegamento tra le aree EMEA e APAC. Ognuno di questi collegamenti tra aree geografiche è vincolato dalla larghezza di banda della WAN, come descritto nella tabella informazioni sulla larghezza di banda del collegamento area nell' [esempio seguente: raccolta dei requisiti per il controllo di ammissione di chiamata nella sezione Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) della documentazione relativa alla pianificazione.

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a>Per creare collegamenti area di rete utilizzando Lync Server Management Shell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet New-CsNetworkRegionLink per creare i collegamenti area di rete e applicare i profili di criteri di larghezza di banda appropriati. Ad esempio, eseguire:
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a>Per creare collegamenti area di rete utilizzando il pannello di controllo Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.

3.  Fare clic sul pulsante di spostamento **Collegamento area**.

4.  Fare clic su **Nuovo**.

5.  Nella pagina **Nuovo collegamento area di rete** fare clic su **Nome** e quindi digitare un nome per il collegamento area di rete.

6.  Fare clic su **area di rete \# 1**e quindi fare clic sull'area di rete nell'elenco che si desidera collegare all'area di rete \# 2.

7.  Fare clic su **area di rete \# 2**e quindi fare clic su un'area di rete nell'elenco che si desidera collegare all'area di rete \# 1.

8.  Facoltativamente, fare clic su **Criteri larghezza di banda** e selezionare il profilo di criteri di larghezza di banda che si desidera applicare al collegamento area di rete.
    
    <div class=" ">
    

    > [!NOTE]  
    > Applicare criteri di larghezza di banda solo se il collegamento area di rete è vincolato dalla larghezza di banda e si desidera utilizzare CAC per controllare il traffico multimediale su tale collegamento.

    
    </div>

9.  Fare clic su **Commit**.

10. Per completare la creazione dei collegamenti area di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per le altre aree.

</div>

</div>

<span> </span>

</div>

</div>

</div>
