---
title: Modificare la topologia in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Dopo aver completato le domande di colloquio iniziale, è possibile modificare il nome di dominio completo (FQDN) e gli indirizzi IP per il sito. A questo scopo, nella pagina topologia globale fare doppio clic sul sito che si vuole modificare.
ms.openlocfilehash: 91a7ad51c66d810255fcc3239d25298bd370501f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186719"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>Modificare la topologia in Skype for Business Server 2015

Dopo aver completato le domande di colloquio iniziale, è possibile modificare il nome di dominio completo (FQDN) e gli indirizzi IP per il sito. A questo scopo, nella pagina **topologia globale** fare doppio clic sul sito che si vuole modificare.

Lo strumento di pianificazione Visualizza la topologia di sito per il sito selezionato. Nella parte inferiore della pagina del sito sono presenti quattro schede:

![Topologia del sito dello strumento di pianificazione](../../media/Planning_Tool_Site_Topology.png)

- Topologia del sito-la pagina attualmente visualizzata con una panoramica visiva della topologia come consigliato.

- Diagramma reticolare Edge: la pagina del diagramma reticolare perimetrale è il punto in cui la finestra di progettazione esegue la maggior parte del lavoro nello strumento di pianificazione. Il diagramma Visualizza la configurazione di rete per una topologia di Skype for Business Server 2015 consigliata, con le voci modificabili per gli indirizzi IP e gli FQDN per server, pool e per i dispositivi di bilanciamento del carico DNS (hardware e Domain Name System).

- Report amministratore Edge-il report amministratore Edge contiene un totale di quattro report:

     ![Pagina del rapporto di amministrazione della rete perimetrale](../../media/Planning_Tool_Summary_Report.png)

  - Riepilogo-report generale delle impostazioni per la configurazione di rete perimetrale. Se si modificano i valori nella pagina del **diagramma reticolare** alla topologia TCP/IP e i valori FQDN di che verranno usati nella distribuzione effettiva, questi indirizzi e nomi verranno rappresentati qui. In caso contrario, verrà visualizzato il testo predefinito.

  - Report certificato: il report certificato elenca il nome dell'oggetto e i nomi alternativi oggetto per i certificati necessari per la topologia.

  - Report firewall: il report firewall elenca le informazioni necessarie per configurare i firewall perimetrali nell'infrastruttura. Sono inclusi gli indirizzi IP (valori predefiniti o modificati), il ruolo del server, l'IP di origine e la porta, la destinazione IP e la porta, il protocollo di trasporto, il protocollo dell'applicazione e le note rilevanti.

  - Report DNS: il report DNS elenca le informazioni rilevanti per le voci DNS che è necessario creare. Sono inclusi il tipo di record, il nome di dominio completo, l'indirizzo IP e i commenti necessari per l'operazione appropriata.

- Riepilogo sito-il riepilogo del sito presenta una panoramica delle selezioni effettuate rispondendo alle domande di colloquio iniziale o inserendo i valori nei **siti di progettazione**. Vengono presentate anche informazioni sulla capacità.

    > [!NOTE]
    > Le informazioni nella pagina di riepilogo del sito sono personalizzate per ogni progettazione e potrebbero non contenere tutte le sezioni o le informazioni dettagliate.

## <a name="edit-the-network-configuration-diagram"></a>Modificare il diagramma di configurazione della rete
<a name="Edit_Network_diagram"> </a>

La maggior parte del lavoro svolto da un progettista nello strumento di pianificazione di Skype for Business Server 2015 è costituito dalla definizione delle voci relative agli indirizzi IP e ai nomi di dominio completi per le voci del diagramma reticolare. Le informazioni immesse in questa pagina vengono riportate nei report e in altre informazioni contenute nello strumento di pianificazione.

![Diagramma di rete dello strumento di pianificazione](../../media/Planning_Tool_Network_Diagram.png)

Lo strumento di pianificazione crea un diagramma reticolare con testo predefinito per gli indirizzi IP e i nomi di dominio completi.

Per modificare il diagramma reticolare e i valori di input:

1. Scegliere una sezione della rete per iniziare a lavorare. Ad esempio, fare doppio clic sul testo, **Access1.contoso.com**. Nella finestra di dialogo visualizzata digitare il nome di dominio completo effettivo del server access1.contoso.com e l'indirizzo IP effettivo, sostituendo 131.107.155.3.

2. Fare clic su **OK** per salvare le voci.

3. Continuare a modificare gli indirizzi IP e gli FQDN, fornendo indirizzi IP virtuali per i servizi di bilanciamento del carico hardware o le voci del server per il bilanciamento del carico DNS (Domain Name System) per i server nei pool.

Una caratteristica utile dello strumento di pianificazione è la possibilità di assegnare in modo incrementale un intervallo di indirizzi IP e nomi host del server, anziché richiedere alla finestra di progettazione di modificare ogni server separato in un pool. Ad esempio:

1. Fare doppio clic sui server front-end in pool. Quando si apre la finestra di dialogo, selezionare **si vuole usare l'IPS e il nome di dominio completo come punti di partenza per tutti i server equivalenti di questo cluster?**.

2. Ad esempio, il valore iniziale per il primo server è fe0101.contoso.com e un indirizzo IP di 192.168.21.122.

3. Digitare fe0.contoso.com in **FQDN del server front-end**, digitare 192.168.21.131 nell' **indirizzo IP del server front-end**e quindi fare clic su **OK**.

4. La caratteristica di incremento automatico aggiorna tutti i server del pool in FE01 tramite fe06 e tutti gli indirizzi IP da 192.168.21.131 a 136.

Dopo aver completato tutte le modifiche, salvare la topologia completando la procedura seguente:

Per salvare la struttura dello strumento di pianificazione, fare clic su **file**e quindi su **Salva topologia** o **Salva topologia con nome**. Se viene visualizzata una finestra di dialogo **Salva strumento di pianificazione come** , digitare un nome per il file in **nome file**e quindi fare clic su **Salva**.

## <a name="see-also"></a>Vedere anche
<a name="Edit_Network_diagram"> </a>

[Modifica della struttura](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
