---
title: 'Lync Server 2013: eliminazione delle subnet di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93806d3e9d5f0cb7f004a90d6f461b363aff65f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a>Eliminazione delle subnet di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Per eliminare una subnet, è possibile usare la procedura seguente. Dal pannello di controllo di Lync Server è possibile creare, modificare o eliminare una subnet di rete. Per informazioni dettagliate sulla creazione o la modifica delle subnet di rete, vedere [creare o modificare subnet di rete in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).

Nella maggior parte delle distribuzioni di Microsoft Lync Server 2013 in cui viene implementato il controllo di ammissione di chiamata (CAC), in genere esiste un numero elevato di subnet. Per questo motivo, è spesso consigliabile configurare subnet da Lync Server Management Shell. Da lì è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet di Windows PowerShell **Import-CSV**. Usando questi cmdlet insieme, è possibile leggere le impostazioni della subnet da un file con valori delimitati da virgole (CSV) e creare più subnet contemporaneamente. Per esempi su come creare subnet da un file CSV, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-delete-a-network-subnet"></a>Per eliminare una subnet di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **Subnet**.

4.  Nella pagina **subnet** fare clic sulla subnet che si desidera eliminare.
    
    <div>
    

    > [!NOTE]  
    > Puoi eliminare più di una subnet alla volta. A questo scopo, premere CTRL e selezionare più subnet tenendo premuto CTRL. In alternativa, per selezionare tutte le subnet, fare clic su <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>modifica</STRONG> .

    
    </div>

5.  Scegliere **Elimina**dal menu **modifica** .

6.  Fare clic su **OK**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare o modificare subnet di rete in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

