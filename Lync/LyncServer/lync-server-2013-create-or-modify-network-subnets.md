---
title: 'Lync Server 2013: creare o modificare le subnet di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47075e96171bbeef5c2709e3eb38a480d08938f0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>Creare o modificare le subnet di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Una subnet di rete deve essere associata a un sito di rete per la determinazione della posizione geografica dell'host appartenente alla subnet. È possibile utilizzare il pannello di controllo di Lync Server per configurare le subnet. Dal pannello di controllo di Lync Server, è possibile creare, modificare o eliminare una subnet di rete. Per informazioni dettagliate sull'eliminazione delle subnet di rete, vedere [eliminazione di subnet di rete in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).

Nella maggior parte delle distribuzioni di Microsoft Lync Server 2013 in cui è implementato il controllo di ammissione di chiamata (CAC), in genere vi sarà un numero elevato di subnet. Per questo motivo, è spesso preferibile configurare le subnet da Lync Server Management Shell. Da questa pagina è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet **Import-CSV**di Windows PowerShell. Se si utilizzano questi cmdlet insieme, è possibile leggere le impostazioni della subnet da un file con valori delimitati da virgole (con estensione CSV) e creare più subnet contemporaneamente. Per esempi su come creare subnet da un file CSV, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-create-a-network-subnet"></a>Per creare una subnet di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Subnet**.

4.  Nella pagina **Subnet** fare clic su **Nuovo**.

5.  In **Nuova subnet** immettere un valore nel campo **ID subnet**. Questo valore deve essere il primo indirizzo IP (ad esempio, 174.11.12.0) dell'intervallo di indirizzi IP definito dalla subnet.

6.  Nel campo **Maschera** immettere un valore numerico compreso tra 1 e 32.
    
    <div>
    

    > [!NOTE]  
    > Questo valore corrisponde alla maschera di bit da applicare alla subnet da creare.

    
    </div>

7.  In **ID sito di rete** selezionare il sito a cui appartiene la subnet.

8.  (Facoltativo) Digitare un valore nel campo **Descrizione** per fornire ulteriori informazioni sulla subnet che non possono essere espresse dal solo nome.

9.  Fare clic su **Commit**.

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>Per modificare una subnet di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Subnet**.

4.  Nella pagina **Subnet** fare clic sulla subnet che si desidera modificare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  Nella pagina **Modifica Subnet** è possibile modificare la maschera di bit, il sito di rete associato o la descrizione. Se si modifica la maschera di bit, tenere presente che l'ID subnet deve essere comunque il primo indirizzo IP dell'intervallo di indirizzi IP definito dalla subnet.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminazione di subnet di rete in Lync Server 2013](lync-server-2013-deleting-network-subnets.md)  


[Informazioni su aree di rete, siti e subnet in Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

