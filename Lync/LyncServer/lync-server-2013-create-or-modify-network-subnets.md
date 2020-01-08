---
title: 'Lync Server 2013: creare o modificare subnet di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f27088b59745bac580990b3e898f485d34dcad57
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>Creare o modificare subnet di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Una subnet di rete deve essere associata a un sito di rete allo scopo di determinare la posizione geografica dell'host appartenente alla subnet. È possibile usare il pannello di controllo di Lync Server per configurare le subnet. Dal pannello di controllo di Lync Server è possibile creare, modificare o eliminare una subnet di rete. Per informazioni dettagliate sull'eliminazione delle subnet di rete, vedere [eliminazione delle subnet di rete in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).

Nella maggior parte delle distribuzioni di Microsoft Lync Server 2013 in cui viene implementato il controllo di ammissione di chiamata (CAC), in genere esiste un numero elevato di subnet. Per questo motivo, è spesso consigliabile configurare subnet da Lync Server Management Shell. Da lì è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet di Windows PowerShell **Import-CSV**. Usando questi cmdlet insieme, è possibile leggere le impostazioni della subnet da un file con valori delimitati da virgole (CSV) e creare più subnet contemporaneamente. Per esempi su come creare subnet da un file CSV, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-create-a-network-subnet"></a>Per creare una subnet di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **Subnet**.

4.  Nella pagina **subnet** fare clic su **nuovo**.

5.  Nella **nuova subnet**immettere un valore nel campo **ID Subnet** . Deve essere un indirizzo IP, ad esempio 174.11.12.0, e deve essere il primo indirizzo nell'intervallo di indirizzi IP definito dalla subnet.

6.  Nel campo **maschera** immettere un valore numerico compreso tra 1 e 32.
    
    <div>
    

    > [!NOTE]  
    > Questo valore è la maschera di maschere che deve essere applicata alla subnet da creare.

    
    </div>

7.  In **ID sito di rete**selezionare il sito a cui appartiene la subnet.

8.  Opzionale Digitare un valore nel campo **Description** per ottenere altre informazioni su questa subnet che non può essere espressa solo dal nome.

9.  Fare clic su **Commit**.

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>Per modificare una subnet di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **Subnet**.

4.  Nella pagina **subnet** fare clic sulla subnet che si vuole modificare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

6.  Nella pagina **modifica subnet** è possibile modificare la maschera di posizione, il sito di rete associato o la descrizione. Se modifichi la maschera di base, tieni presente che l'ID subnet deve essere il primo indirizzo nell'intervallo di indirizzi IP definito dalla subnet.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminazione delle subnet di rete in Lync Server 2013](lync-server-2013-deleting-network-subnets.md)  


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

