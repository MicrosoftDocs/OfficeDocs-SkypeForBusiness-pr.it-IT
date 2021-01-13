---
title: Modificare la topologia in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Dopo aver completato le domande relative all'intervista iniziale, è possibile modificare il nome di dominio completo (FQDN) e gli indirizzi IP per il sito. A tale scopo, nella pagina topologia globale fare doppio clic sul sito che si desidera modificare.
ms.openlocfilehash: ba18070b21494028d31b4167ab92a622794c5e51
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834886"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>Modificare la topologia in Skype for Business Server 2015

Dopo aver completato le domande relative all'intervista iniziale, è possibile modificare il nome di dominio completo (FQDN) e gli indirizzi IP per il sito. A tale scopo, nella pagina **topologia globale** fare doppio clic sul sito che si desidera modificare.

Lo strumento di pianificazione Visualizza la topologia di sito per il sito selezionato. Nella parte inferiore della pagina del sito sono disponibili quattro schede:

![Topologia del sito dello strumento di pianificazione](../../media/Planning_Tool_Site_Topology.png)

- Topologia del sito: la pagina attualmente visualizzata con una panoramica visiva della topologia come consigliato.

- Diagramma di rete perimetrale-la pagina del diagramma reticolare è il punto in cui la finestra di progettazione esegue la maggior parte del lavoro nello strumento di pianificazione. Nel diagramma viene visualizzata la configurazione di rete per una topologia di Skype for Business Server 2015 consigliata, con voci modificabili per gli indirizzi IP e FQDN per i server, il pool e i dispositivi di bilanciamento del carico DNS (Domain Name System).

- Report amministratore Edge-il report amministratore Edge contiene un totale di quattro rapporti:

     ![Pagina del rapporto di amministrazione Edge](../../media/Planning_Tool_Summary_Report.png)

  - Report riepilogativo-un rapporto generale delle impostazioni per la configurazione della rete perimetrale. Se si modificano i valori della pagina del **diagramma di rete perimetrale** nella topologia TCP/IP e i valori FQDN di che verranno utilizzati nella distribuzione effettiva, tali indirizzi e nomi verranno rappresentati in questo articolo. In caso contrario, verrà visualizzato il testo predefinito.

  - Report dei certificati-il rapporto sui certificati elenca i nomi soggetto e gli oggetti alternativi del soggetto per il certificato richiesto per la topologia.

  - Report firewall-il report del firewall elenca le informazioni necessarie per configurare i firewall perimetrali nell'infrastruttura. Sono inclusi gli indirizzi IP (valori predefiniti o modificati), il ruolo del server, l'IP di origine e la porta, l'IP di destinazione e la porta, il protocollo di trasporto, il protocollo dell'applicazione e le note rilevanti.

  - Report DNS-il report DNS elenca le informazioni rilevanti per le voci DNS che è necessario creare. Sono inclusi il tipo di record, il nome di dominio completo, l'indirizzo IP e i commenti necessari per il corretto funzionamento.

- Riepilogo sito-il riepilogo del sito presenta una panoramica delle selezioni effettuate rispondendo alle domande relative all'intervista iniziale o compilando i valori nei siti di **progettazione**. Vengono inoltre presentate informazioni sulla capacità.

    > [!NOTE]
    > Le informazioni nella pagina di riepilogo del sito sono personalizzate per ogni progettazione e potrebbero non contenere tutte le sezioni o informazioni dettagliate in questo articolo.

## <a name="edit-the-network-configuration-diagram"></a>Modificare il diagramma di configurazione di rete
<a name="Edit_Network_diagram"> </a>

La maggior parte del lavoro svolto da un progettista nello strumento di pianificazione di Skype for Business Server 2015 è costituito dalla definizione delle voci relative agli indirizzi IP e ai nomi di dominio completi (FQDN) per le voci nel diagramma reticolare. Le informazioni immesse in questa pagina vengono riportate nei report e nelle altre informazioni contenute nello strumento di pianificazione.

![Diagramma di rete dello strumento di pianificazione](../../media/Planning_Tool_Network_Diagram.png)

Lo strumento di pianificazione crea un diagramma reticolare con testo predefinito per gli indirizzi IP e gli FQDN.

Per modificare il diagramma di rete e i valori di input:

1. Scegliere una sezione della rete da cui iniziare. Ad esempio, fare doppio clic sul testo **Access1.contoso.com**. Nella finestra di dialogo che si apre, digitare il nome di dominio completo effettivo del server access1.contoso.com e l'indirizzo IP effettivo, sostituendo 131.107.155.3.

2. Fare clic su **OK** per salvare le immissioni.

3. Continuare a modificare gli indirizzi IP e gli FQDN, fornendo indirizzi IP virtuali per i dispositivi di bilanciamento del carico hardware o le voci relative ai server per il bilanciamento del carico DNS (Domain Name System) per i server dei pool.

Nello Strumento di pianificazione è disponibile una funzionalità utile che consente di assegnare in modo incrementale un intervallo di indirizzi IP e nomi host di server anziché richiedere al progettista di modificare ogni server separato di un pool. Ad esempio:

1. Fare doppio clic sui Front End Server in pool. Quando viene visualizzata la finestra di dialogo, selezionare **Utilizzare questi IP e l'FQDN come punti di partenza per tutti i server equivalenti nel cluster?**.

2. Ad esempio, il valore iniziale del primo server è fe0101.contoso.com e un indirizzo IP di 192.168.21.122.

3. Digitare fe0.contoso.com nell' **FQDN front end server**, digitare 192.168.21.131 nell' **indirizzo IP front end server** e quindi fare clic su **OK**.

4. La funzionalità di incremento automatico consente di aggiornare tutti i server del pool a FE01 tramite fe06 e tutti gli indirizzi IP da 192.168.21.131 a 136.

Dopo aver completato tutte le modifiche, salvare la topologia completando i passaggi seguenti:

Per salvare la progettazione dello strumento di pianificazione, fare clic su **file** e quindi su **Salva topologia** o **Salva topologia con nome**. Se viene visualizzata una finestra di dialogo **Salva file dello Strumento di pianificazione con nome**, digitare un nome per il file in **Nome file** e quindi fare clic su **Salva**.

## <a name="see-also"></a>Vedere anche
<a name="Edit_Network_diagram"> </a>

[Modifica della progettazione](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
