---
title: 'Lync Server 2013: modifica della progettazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7607fb2f31107e3368fa52167dc5015eb1b71f15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a>Modifica della progettazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Dopo aver completato le domande relative all'intervista iniziale, è possibile modificare il nome di dominio completo (FQDN) e gli indirizzi IP per il sito. A tale scopo, nella pagina **topologia globale** fare doppio clic sul sito che si desidera modificare.

Lo strumento di pianificazione Visualizza la topologia di sito per il sito selezionato. Nella parte inferiore della pagina del sito sono disponibili quattro schede:

![Topologia del sito dello strumento di pianificazione](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Topologia del sito dello strumento di pianificazione")

  - Topologia del sito – la pagina attualmente visualizzata con una panoramica visiva della topologia come consigliato.

  - Diagramma di rete perimetrale: la pagina del diagramma reticolare è la posizione in cui la finestra di progettazione esegue la maggior parte del lavoro nello strumento di pianificazione. Nel diagramma viene visualizzata la configurazione di rete per una topologia di Lync Server 2013 consigliata, con voci modificabili per gli indirizzi IP e FQDN per i server, il pool e i dispositivi di bilanciamento del carico DNS (Domain Name System).

  - Report amministratore Edge – il report amministratore Edge contiene un totale di quattro rapporti:
    
    ![Pagina del rapporto di amministrazione Edge](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Pagina del rapporto di amministrazione Edge")  
    
      - Report riepilogativo – un rapporto generale delle impostazioni per la configurazione della rete perimetrale. Se si modificano i valori della pagina del **diagramma di rete perimetrale** nella topologia TCP/IP e i valori FQDN di che verranno utilizzati nella distribuzione effettiva, tali indirizzi e nomi verranno rappresentati in questo articolo. In caso contrario, verrà visualizzato il testo predefinito.
    
      - Rapporto certificati: il report del certificato elenca i nomi soggetto e gli oggetti alternativi per i certificati necessari per la topologia.
    
      - Report firewall: il report del firewall elenca le informazioni necessarie per configurare i firewall perimetrali nell'infrastruttura. Sono inclusi gli indirizzi IP (valori predefiniti o modificati), il ruolo del server, l'IP di origine e la porta, l'IP di destinazione e la porta, il protocollo di trasporto, il protocollo dell'applicazione e le note rilevanti.
    
      - Report DNS: il report DNS elenca le informazioni rilevanti per le voci DNS che è necessario creare. Sono inclusi il tipo di record, il nome di dominio completo, l'indirizzo IP e i commenti necessari per il corretto funzionamento.

  - Riepilogo del sito: il riepilogo del sito presenta una panoramica delle selezioni effettuate rispondendo alle domande relative all'intervista iniziale o compilando i valori nei **siti di progettazione**. Vengono inoltre presentate informazioni sulla capacità.
    
    <div>
    

    > [!NOTE]  
    > Le informazioni nella pagina di riepilogo del sito sono personalizzate per ogni progettazione e potrebbero non contenere tutte le sezioni o informazioni dettagliate in questo articolo.

    
    </div>

<div>

## <a name="see-also"></a>Vedere anche


[Modifica del diagramma di configurazione di rete in Lync Server 2013](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

