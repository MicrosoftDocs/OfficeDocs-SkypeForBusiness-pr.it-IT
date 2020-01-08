---
title: 'Lync Server 2013: Modifica della progettazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 601c313231a26341c3c4cf8a4897d11872dec9a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a>Modifica della progettazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Dopo aver completato le domande di colloquio iniziale, è possibile modificare il nome di dominio completo (FQDN) e gli indirizzi IP per il sito. A questo scopo, nella pagina **topologia globale** fare doppio clic sul sito che si vuole modificare.

Lo strumento di pianificazione Visualizza la topologia di sito per il sito selezionato. Nella parte inferiore della pagina del sito sono presenti quattro schede:

(images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Topologia sito") strumento pianificazione ![topologia sito]strumento

  - Topologia sito: la pagina attualmente visualizzata con una panoramica visiva della topologia, come consigliato.

  - Diagramma reticolare Edge: la pagina del diagramma reticolare perimetrale è la posizione in cui la finestra di progettazione esegue la maggior parte del lavoro nello strumento di pianificazione. Nel diagramma viene visualizzata la configurazione di rete per una topologia di Lync Server 2013 consigliata, con le voci modificabili per gli indirizzi IP e gli FQDN per server, pool e per i dispositivi di bilanciamento del carico DNS (hardware e Domain Name System).

  - Report amministratore Edge-il report amministratore Edge contiene un totale di quattro report:
    
    ![](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Pagina") rapporto amministratore bordo pagina report amministratore  
    
      - Report di riepilogo: un report generale delle impostazioni per la configurazione di rete perimetrale. Se si modificano i valori nella pagina del **diagramma reticolare** alla topologia TCP/IP e i valori FQDN di che verranno usati nella distribuzione effettiva, questi indirizzi e nomi verranno rappresentati qui. In caso contrario, verrà visualizzato il testo predefinito.
    
      - Report certificato: il report certificato elenca il nome dell'oggetto e i nomi alternativi oggetto per i certificati necessari per la topologia.
    
      - Report firewall: il report firewall elenca le informazioni necessarie per configurare i firewall perimetrali nell'infrastruttura. Sono inclusi gli indirizzi IP (valori predefiniti o modificati), il ruolo del server, l'IP di origine e la porta, la destinazione IP e la porta, il protocollo di trasporto, il protocollo dell'applicazione e le note rilevanti.
    
      - Report DNS: il report DNS elenca le informazioni rilevanti per le voci DNS che è necessario creare. Sono inclusi il tipo di record, il nome di dominio completo, l'indirizzo IP e i commenti necessari per l'operazione appropriata.

  - Riepilogo sito: il riepilogo del sito presenta una panoramica delle selezioni effettuate rispondendo alle domande di colloquio iniziale o inserendo i valori nei **siti di progettazione**. Vengono presentate anche informazioni sulla capacità.
    
    <div>
    

    > [!NOTE]  
    > Le informazioni nella pagina di riepilogo del sito sono personalizzate per ogni progettazione e potrebbero non contenere tutte le sezioni o le informazioni dettagliate.

    
    </div>

<div>

## <a name="see-also"></a>Vedere anche


[Modifica del diagramma di configurazione della rete in Lync Server 2013](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

