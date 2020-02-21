---
title: 'Lync Server 2013: modifica del diagramma di configurazione di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 225702f30aa19bf53c8b3f65c9731ea29b16a686
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a>Modifica del diagramma di configurazione di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

La maggior parte del lavoro svolto da un progettista in Lync Server 2013 è costituito dalla definizione delle voci relative agli indirizzi IP e ai nomi di dominio completi (FQDN) per le voci del diagramma reticolare. Le informazioni immesse in questa pagina vengono riportate nei report e nelle altre informazioni contenute nello strumento di pianificazione.

![Diagramma di rete dello strumento di pianificazione](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Diagramma di rete dello strumento di pianificazione")

Lo strumento di pianificazione crea un diagramma reticolare con testo predefinito per gli indirizzi IP e gli FQDN.

Per modificare il diagramma di rete e i valori di input:

1.  Scegliere una sezione della rete da cui iniziare. Ad esempio, fare doppio clic sul testo **Access1.contoso.com**. Nella finestra di dialogo che si apre, digitare il nome di dominio completo effettivo del server access1.contoso.com e l'indirizzo IP effettivo, sostituendo 131.107.155.3.

2.  Fare clic su **OK** per salvare le immissioni.

3.  Continuare a modificare gli indirizzi IP e gli FQDN, fornendo indirizzi IP virtuali per i dispositivi di bilanciamento del carico hardware o le voci relative ai server per il bilanciamento del carico DNS (Domain Name System) per i server dei pool.

Nello Strumento di pianificazione è disponibile una funzionalità utile che consente di assegnare in modo incrementale un intervallo di indirizzi IP e nomi host di server anziché richiedere al progettista di modificare ogni server separato di un pool. Ad esempio:

1.  Fare doppio clic sui Front End Server in pool. Quando viene visualizzata la finestra di dialogo, selezionare **Utilizzare questi IP e l'FQDN come punti di partenza per tutti i server equivalenti nel cluster?**.

2.  Ad esempio, il valore iniziale del primo server è fe0101.contoso.com e un indirizzo IP di 192.168.21.122.

3.  Digitare **fe0.contoso.com** nell' **FQDN front end server**, digitare **192.168.21.131** nell' **indirizzo IP front end server**e quindi fare clic su **OK**.

4.  La funzionalità di incremento automatico consente di aggiornare tutti i server del pool a FE01 tramite fe06 e tutti gli indirizzi IP da 192.168.21.131 a 136.

Dopo aver completato tutte le modifiche, salvare la topologia completando i passaggi seguenti:

Per salvare la progettazione dello strumento di pianificazione, fare clic su **file**e quindi su **Salva topologia** o **Salva topologia con nome**. Se viene visualizzata una finestra di dialogo **Salva file dello Strumento di pianificazione con nome**, digitare un nome per il file in **Nome file** e quindi fare clic su **Salva**.

<div>

## <a name="see-also"></a>Vedere anche


[Modifica della progettazione in Lync Server 2013](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

