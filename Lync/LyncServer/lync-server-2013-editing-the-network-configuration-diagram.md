---
title: 'Lync Server 2013: modificare il diagramma di configurazione della rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2772cad1d1a16aa0363b1ab50d0bcaadacb91a08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a>Modifica del diagramma di configurazione della rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

La maggior parte del lavoro svolto da un progettista in Lync Server 2013 è costituito dalla definizione delle voci relative agli indirizzi IP e ai nomi di dominio completi (FQDN) per le voci del diagramma reticolare. Le informazioni immesse in questa pagina vengono riportate nei report e in altre informazioni contenute nello strumento di pianificazione.

![](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Diagramma reticolare") strumento pianificazione diagramma reticolare

Lo strumento di pianificazione crea un diagramma reticolare con testo predefinito per gli indirizzi IP e i nomi di dominio completi.

Per modificare il diagramma reticolare e i valori di input:

1.  Scegliere una sezione della rete per iniziare a lavorare. Ad esempio, fare doppio clic sul testo, **Access1.contoso.com**. Nella finestra di dialogo visualizzata digitare il nome di dominio completo effettivo del server access1.contoso.com e l'indirizzo IP effettivo, sostituendo 131.107.155.3.

2.  Fare clic su **OK** per salvare le voci.

3.  Continuare a modificare gli indirizzi IP e gli FQDN, fornendo indirizzi IP virtuali per i servizi di bilanciamento del carico hardware o le voci del server per il bilanciamento del carico DNS (Domain Name System) per i server nei pool.

Una caratteristica utile dello strumento di pianificazione è la possibilità di assegnare in modo incrementale un intervallo di indirizzi IP e nomi host del server, anziché richiedere alla finestra di progettazione di modificare ogni server separato in un pool. Ad esempio:

1.  Fare doppio clic sui server front-end in pool. Quando si apre la finestra di dialogo, selezionare **si vuole usare l'IPS e il nome di dominio completo come punti di partenza per tutti i server equivalenti di questo cluster?**.

2.  Ad esempio, il valore iniziale per il primo server è fe0101.contoso.com e un indirizzo IP di 192.168.21.122.

3.  Digitare **fe0.contoso.com** in **FQDN del server front-end**, digitare **192.168.21.131** nell' **indirizzo IP del server front-end**e quindi fare clic su **OK**.

4.  La caratteristica di incremento automatico aggiorna tutti i server del pool in FE01 tramite fe06 e tutti gli indirizzi IP da 192.168.21.131 a 136.

Dopo aver completato tutte le modifiche, salvare la topologia completando la procedura seguente:

Per salvare la struttura dello strumento di pianificazione, fare clic su **file**e quindi su **Salva topologia** o **Salva topologia con nome**. Se viene visualizzata una finestra di dialogo **Salva strumento di pianificazione come** , digitare un nome per il file in **nome file**e quindi fare clic su **Salva**.

<div>

## <a name="see-also"></a>Vedere anche


[Modifica della progettazione in Lync Server 2013](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

