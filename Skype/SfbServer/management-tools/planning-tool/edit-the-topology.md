---
title: Modificare la topologia in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Dopo aver completato le domande iniziali, è possibile modificare il nome di dominio completo (FQDN) e gli indirizzi IP per il sito. A tale scopo, nella pagina Topologia globale fare doppio clic sul sito che si desidera modificare.
ms.openlocfilehash: 2276f2959329c77744054976e3a49f5ad72778ae
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776166"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>Modificare la topologia in Skype for Business Server 2015

Dopo aver completato le domande iniziali, è possibile modificare il nome di dominio completo (FQDN) e gli indirizzi IP per il sito. A tale scopo, nella **pagina Topologia globale** fare doppio clic sul sito che si desidera modificare.

Lo Strumento di pianificazione visualizza la topologia del sito per il sito selezionato. Nella parte inferiore della pagina del sito sono presenti quattro schede:

![Topologia del sito dello strumento di pianificazione.](../../media/Planning_Tool_Site_Topology.png)

- Topologia sito - La pagina attualmente visualizzata con una panoramica visiva della topologia come consigliato.

- Diagramma reticolare perimetrale - La pagina Diagramma reticolare perimetrale è la posizione in cui il progettista esegue la maggior parte delle operazioni nello strumento di pianificazione. Nel diagramma viene visualizzata la configurazione di rete per una topologia di Skype for Business Server 2015 consigliata, con voci modificabili per gli indirizzi IP e gli FQDN per server, pool ed hardware e servizi di bilanciamento del carico DNS (Domain Name System).

- Edge Admin Report - Il report dell'amministratore di Edge contiene un totale di quattro report:

     ![Pagina Report amministratore Edge.](../../media/Planning_Tool_Summary_Report.png)

  - Rapporto riepilogativo- Report generale delle impostazioni per la configurazione della rete perimetrale. Se si modificano i valori nella pagina **Diagramma** reti perimetrale con i valori TCP/IP e FQDN della topologia che verranno utilizzati nella distribuzione effettiva, tali indirizzi e nomi verranno rappresentati qui. In caso contrario, verrà visualizzato il testo predefinito.

  - Rapporto certificati - Nel rapporto del certificato verranno elencati il nome soggetto e i nomi alternativi del soggetto per i certificati necessari per la topologia.

  - Report firewall - Nel report del firewall sono elencate le informazioni necessarie per configurare i firewall perimetrali nell'infrastruttura. Sono inclusi gli indirizzi IP (valori predefiniti o modificati), il ruolo del server, l'IP e la porta di origine, l'IP e la porta di destinazione, il protocollo di trasporto, il protocollo dell'applicazione e le note rilevanti.

  - Rapporto DNS - Il rapporto DNS elenca le informazioni rilevanti per le voci DNS che è necessario creare. Sono inclusi il tipo di record, l'FQDN, l'indirizzo IP e i commenti necessari per l'operazione corretta.

- Riepilogo sito - Il riepilogo del sito presenta una panoramica delle selezioni effettuate rispondendo alle domande iniziali del colloquio o compilando i valori in **Siti di progettazione.** Vengono presentate anche le informazioni sulla capacità.

    > [!NOTE]
    > Le informazioni nella pagina Riepilogo sito sono personalizzate per ogni progettazione e potrebbero non contenere tutte le sezioni o le informazioni descritte qui.

## <a name="edit-the-network-configuration-diagram"></a>Modificare il diagramma di configurazione di rete
<a name="Edit_Network_diagram"> </a>

La maggior parte delle operazioni che un progettista esegue nello strumento di pianificazione di Skype for Business Server 2015 consiste nella definizione delle voci per gli indirizzi IP e i nomi di dominio completi (FQDN) per le voci nel diagramma di rete. Le informazioni immesse in questa pagina vengono riportate nei report e nelle altre informazioni contenute nello Strumento di pianificazione.

![Diagramma di rete dello strumento di pianificazione.](../../media/Planning_Tool_Network_Diagram.png)

Lo strumento di pianificazione crea un diagramma di rete con testo predefinito per gli indirizzi IP e gli FQDN.

Per modificare il diagramma di rete e i valori di input:

1. Scegliere una sezione della rete da cui iniziare. Ad esempio, fare doppio clic sul testo, **access1.contoso.com**. Nella finestra di dialogo visualizzata digitare l'FQDN effettivo del server access1.contoso.com e l'indirizzo IP effettivo, sostituendo 131.107.155.3.

2. Fare clic su **OK** per salvare le immissioni.

3. Continuare a modificare gli indirizzi IP e gli FQDN, fornendo indirizzi IP virtuali per i dispositivi di bilanciamento del carico hardware o le voci relative ai server per il bilanciamento del carico DNS (Domain Name System) per i server dei pool.

Nello Strumento di pianificazione è disponibile una funzionalità utile che consente di assegnare in modo incrementale un intervallo di indirizzi IP e nomi host di server anziché richiedere al progettista di modificare ogni server separato di un pool. Ad esempio:

1. Fare doppio clic sui Front End Server in pool. Quando viene visualizzata la finestra di dialogo, selezionare **Utilizzare questi IP e l'FQDN come punti di partenza per tutti i server equivalenti nel cluster?**.

2. Ad esempio, il valore iniziale per il primo server è fe0101.contoso.com e un indirizzo IP di 192.168.21.122.

3. Digitare fe0.contoso.com in **FQDN Front End Server,** digitare 192.168.21.131 in **Indirizzo IP Front End Server** e quindi fare clic su **OK**.

4. La funzionalità di incremento automatico aggiorna tutti i server del pool da fe01 a fe06 e tutti gli indirizzi IP da 192.168.21.131 a 136.

Dopo aver completato tutte le modifiche, salvare la topologia completando la procedura seguente:

Per salvare la struttura dello strumento di pianificazione, fare clic **su File** e quindi su **Salva** topologia o Salva topologia **con nome.** Se viene visualizzata una finestra di dialogo **Salva file dello Strumento di pianificazione con nome**, digitare un nome per il file in **Nome file** e quindi fare clic su **Salva**.

## <a name="see-also"></a>Vedere anche
<a name="Edit_Network_diagram"> </a>

[Modifica della struttura](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)