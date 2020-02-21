---
title: 'Lync Server 2013: eliminazione di subnet di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05e47875007bd9fb7893ad952bea6772d2d9df9b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a>Eliminazione di subnet di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

È possibile utilizzare la procedura seguente per eliminare una subnet. Dal pannello di controllo di Lync Server, è possibile creare, modificare o eliminare una subnet di rete. Per informazioni dettagliate sulla creazione o la modifica di subnet di rete, vedere [creare o modificare le subnet di rete in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).

Nella maggior parte delle distribuzioni di Microsoft Lync Server 2013 in cui è implementato il controllo di ammissione di chiamata (CAC), in genere vi sarà un numero elevato di subnet. Per questo motivo, è spesso preferibile configurare le subnet da Lync Server Management Shell. Da questa pagina è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet **Import-CSV**di Windows PowerShell. Se si utilizzano questi cmdlet insieme, è possibile leggere le impostazioni della subnet da un file con valori delimitati da virgole (con estensione CSV) e creare più subnet contemporaneamente. Per esempi su come creare subnet da un file CSV, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-delete-a-network-subnet"></a>Per eliminare una subnet di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Subnet**.

4.  Nella pagina **Subnet** fare clic sulla subnet che si desidera eliminare.
    
    <div>
    

    > [!NOTE]  
    > È possibile eliminare più subnet contemporaneamente. A tale scopo, tenere premuto CTRL e selezionare le diverse subnet. In alternativa, per selezionare tutte le subnet, scegliere <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>Modifica</STRONG>.

    
    </div>

5.  Scegliere **Elimina** dal menu **Modifica**.

6.  Fare clic su **OK**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare o modificare le subnet di rete in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

