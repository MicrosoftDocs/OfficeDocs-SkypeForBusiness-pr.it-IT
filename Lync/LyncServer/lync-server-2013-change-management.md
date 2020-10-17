---
title: 'Lync Server 2013: gestione delle modifiche'
description: 'Lync Server 2013: Change Management.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change management
ms:assetid: 73c774f5-c12f-4c72-be73-e07dc745b994
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720336(v=OCS.15)
ms:contentKeyID: 63969618
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69ea019f6366528c40b60a39ca8b646b49b336b0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564462"
---
# <a name="change-management-in-lync-server-2013"></a>Gestione delle modifiche in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-08-18_

Le modifiche apportate all'ambiente IT sono inevitabili. Le modifiche includono nuove tecnologie, sistemi, applicazioni, hardware, strumenti, processi e modifiche dei ruoli e delle responsabilità. Un sistema di gestione delle modifiche efficace consente di introdurre modifiche all'ambiente IT in modo rapido e con interruzioni minime del servizio. Un sistema di gestione delle modifiche riunisce i team coinvolti nella modifica di un sistema. Ad esempio, decidere di usufruire di Office Web Apps. Si tratta di un'applicazione di servizio Lync integrata che consente agli utenti di leggere e modificare documenti in un browser. L'implementazione di questo servizio, dopo aver effettuato la produzione, richiede la partecipazione di più team:

  - Team di testing **Test Team**     Questo team carica i test di Office Web Apps in un server di testing, nel processo che fornisce informazioni sui modelli di utilizzo previsti e sulle prestazioni previste dei server di produzione.

  - **Amministratori**     di Lync Questo team determina la strategia di distribuzione e gli script dell'installazione in cui era possibile. Il team è responsabile del fatto che la modifica venga distribuita nell'ambiente di produzione ed è responsabile dell'amministrazione in seguito. Il team deve comprendere l'effetto delle modifiche e inserirle nelle procedure prima che le modifiche vengano inserite in produzione

  - **Team**     di rete Questo team è responsabile delle modifiche apportate alle regole del firewall che consentono l'accesso da Internet ai server del pool Lync interni. Il team è anche responsabile di collaborare con gli amministratori di Lync per garantire che la larghezza di banda disponibile sia in grado di supportare il carico aggiuntivo.

  - **Team**     di sicurezza Questo team valuta la sicurezza e riduce al minimo i rischi. Il team di sicurezza deve esaminare le vulnerabilità note e garantire che i rischi per la sicurezza vengano minimizzati.

  - Team di accettazione **dell'utente**     Questo team è composto da utenti che sono disposti a testare il sistema e a fornire commenti e suggerimenti per i miglioramenti.

Il processo di gestione delle modifiche definisce le responsabilità di ogni team e pianifica il lavoro da eseguire, includendo i controlli e i test in cui sono necessari. I controlli delle modifiche variano in base alla complessità e all'effetto atteso di una modifica. Possono variare dall'approvazione automatica delle modifiche di lieve entità, per modificare le riunioni di revisione, per visualizzare le recensioni complete a livello di progetto. Per spiegarlo meglio, i gruppi di modifiche sono descritti in questa sezione.

  - **Modifiche principali**     Le modifiche principali hanno un effetto globale sul sistema e possono richiedere input da vari team. Un esempio di questo è l'aggiornamento a Lync Server 2013. Le modifiche importanti riguardano molte squadre e sistemi diversi. Il processo di gestione delle modifiche probabilmente includerà una o più riunioni di revisione delle modifiche per informare i team che saranno coinvolti nella modifica o essere interessati dalla modifica.

  - **Modifiche**     significative Le modifiche significative richiedono risorse significative per la pianificazione, la creazione e l'implementazione. È opportuno introdurre controlli di modifica adeguati per garantire che l'effetto della modifica venga compreso, che vengano verificate le procedure di distribuzione e che i piani di ripristino e di emergenza siano pronti. Un esempio di modifica significativa consiste nella distribuzione di un nuovo aggiornamento cumulativo.

  - **Modifiche**     minime Le modifiche minime non influiscono in modo significativo sull'ambiente IT, ad esempio modificando alcuni criteri di Lync tramite il pannello di controllo di Microsoft Lync Server 2013.

  - **Modifiche standard**     Le modifiche standard vengono eseguite regolarmente e sono ben comprese e documentate. Il processo di gestione delle modifiche dovrebbe esaminare tutte le modifiche apportate alle procedure. Non dovrebbe essere necessario per le modifiche di routine come la creazione di un database del contenuto o l'aggiunta di un utente.

Nell'esempio seguente di gestione delle modifiche viene esaminato il modo in cui i diversi team interagiscono e le azioni eseguite quando si distribuisce un nuovo Service Pack. Queste azioni vengono organizzate e gestite dal processo di gestione delle modifiche.

  - **Generare una richiesta**     di modifica Il team di sicurezza ha valutato il Service Pack più recente e ha confermato che risolve una possibile vulnerabilità del sistema di produzione. Il team genera una richiesta di modifica per fare in modo che il nuovo aggiornamento cumulativo venga applicato a tutti i server che eseguono Lync Server.

  - Revisione delle note sulla **versione del Service Pack**     Il team di amministrazione di Lync esamina le note sulla versione del Service Pack per identificare l'effetto sul sistema.

  - **Viene eseguita**     una serie di test di laboratorio Il team di amministrazione di Lync deve eseguire gli aggiornamenti dei test su un server in un ambiente di testing per decidere se il Service Pack può essere applicato correttamente senza influire su nessuna delle applicazioni installate e sui sistemi server. Se sono presenti applicazioni di terze parti o create internamente che si interfacciano con Lync Server in un ambiente di produzione, queste devono essere testate anche. Questi test possono anche essere utilizzati per stimare il tempo necessario per l'esecuzione degli aggiornamenti.

  - **Gli utenti vengono informati dell'interruzione**     Il team di amministrazione di Lync, il team di comunicazione o l'help desk dell'utente informa tutti gli utenti coinvolti sul ciclo di manutenzione pianificato e sulla durata del servizio non disponibile.

  - **Prima dell'aggiornamento viene eseguito un backup completo di Lync**     . Il team di amministrazione di Lync deve verificare che esista un backup valido che può essere utilizzato per ripristinare lo stato del sistema originale se l'installazione del Service Pack ha esito negativo. È consigliabile ripristinare il backup su un server di standby in modo che il sistema sia prontamente disponibile in caso di problemi.

  - **L'aggiornamento cumulativo è distribuito**     Il team di amministrazione di Lync esegue l'installazione durante il ciclo di manutenzione pianificato.

<div>

## <a name="managing-the-timing-of-changes"></a>Gestione della tempistica delle modifiche

È consigliabile implementare una procedura per la pianificazione delle modifiche per evitare interruzioni nelle sezioni sovrapposte del lavoro. Ad esempio, due team possono entrambi pianificare una modifica di minore entità in un sistema. Un team potrebbe applicare un aggiornamento cumulativo in un pool mentre un altro team sta migrando gli utenti legacy in quel pool. Nessuna squadra è intaccata dalle modifiche che l'altro team sta pianificando e ogni team potrebbe non essere necessariamente a conoscenza delle modifiche che l'altro team sta pianificando. Se entrambe le modifiche sono state eseguite contemporaneamente, potrebbero verificarsi problemi nell'implementazione delle modifiche. Inoltre, se si verificano problemi dopo l'applicazione delle modifiche, ad esempio se la migrazione degli utenti ha esito negativo, potrebbe essere difficile decidere quale modifica deve essere ripristinata. I periodi di manutenzione devono essere configurati tra l'IT e la gestione per testare le modifiche e accettarle.

</div>

</div>

<span> </span>

</div>

</div>

</div>

