---
title: "Lync Server 2013: creare collegamenti all'area di rete"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c0f21f599b8afa4f9f31ec16aad82e305c8a08e
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40979839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a>Creare collegamenti all'area di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Le aree all'interno di una rete sono collegate tramite connettività WAN fisica. Un *collegamento all'area di rete* crea un collegamento tra due aree geografiche configurate per il controllo di ammissione alle chiamate (CAC) e imposta le limitazioni della larghezza di banda per il traffico audio e video tra queste aree.

Per informazioni dettagliate sull'uso dei collegamenti all'area di rete, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:

  - [New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

La topologia di esempio include un collegamento tra le aree Nord America e APAC e un collegamento tra le aree EMEA e APAC. Ognuno di questi collegamenti di area geografica è vincolato dalla larghezza di banda WAN, come descritto nella tabella informazioni sulla larghezza di banda del collegamento di area nell' [esempio: raccogliere i requisiti per il controllo di ammissione delle chiamate nella sezione Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) della documentazione relativa alla pianificazione.

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a>Per creare collegamenti all'area geografica di rete tramite Lync Server Management Shell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet New-CsNetworkRegionLink per creare i collegamenti all'area geografica e applicare i profili dei criteri di larghezza di banda appropriati. Ad esempio, eseguire:
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a>Per creare collegamenti all'area geografica di rete tramite il pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.

3.  Fare clic sul pulsante di spostamento **collegamento area geografica** .

4.  Fare clic su **nuovo**.

5.  Nella pagina **New Region link** fare clic su **nome** e quindi digitare un nome per il collegamento all'area di rete.

6.  Fare clic su **area \#di rete 1**e quindi sull'area di rete nell'elenco che si vuole collegare all'area \#di rete 2.

7.  Fare clic su **area geografica \#di rete 2**e quindi fare clic su un'area di rete nell'elenco che si \#vuole collegare all'area geografica di rete 1.

8.  Facoltativamente, fare clic su **criteri di larghezza di banda**e quindi selezionare il profilo dei criteri di larghezza di banda che si vuole applicare al collegamento all'area di rete.
    
    <div class=" ">
    

    > [!NOTE]  
    > Applicare un criterio di larghezza di banda solo se il collegamento all'area di rete è vincolato dalla larghezza di banda e si vuole usare CAC per controllare il traffico multimediale sul collegamento.

    
    </div>

9.  Fare clic su **Commit**.

10. Per completare la creazione di collegamenti di area di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per altre aree geografiche.

</div>

</div>

<span> </span>

</div>

</div>

</div>
