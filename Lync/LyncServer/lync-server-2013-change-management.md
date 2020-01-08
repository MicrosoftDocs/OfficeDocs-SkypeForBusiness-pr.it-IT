---
title: 'Lync Server 2013: gestione delle modifiche'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change management
ms:assetid: 73c774f5-c12f-4c72-be73-e07dc745b994
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720336(v=OCS.15)
ms:contentKeyID: 63969618
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13eb521ea6b4be5f8d701885df65a3e1672b2eaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-management-in-lync-server-2013"></a>Gestione delle modifiche in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-08-18_

Le modifiche apportate all'ambiente IT sono inevitabili. Le modifiche includono nuove tecnologie, sistemi, applicazioni, hardware, strumenti, processi e modifiche dei ruoli e delle responsabilità. Un sistema di gestione delle modifiche efficace consente di apportare modifiche all'ambiente IT in modo rapido e con interruzioni minime del servizio. Un sistema di gestione delle modifiche riunisce i team coinvolti nella modifica di un sistema. Ad esempio, decidendo di sfruttare le app di Office Web Apps. Si tratta di un'applicazione di servizio Lync integrata che consente agli utenti di leggere e modificare documenti in un browser. L'implementazione di questo servizio, dopo aver effettuato la produzione, richiede il coinvolgimento di più team:

  - **Test team**   questo team carica il test di Office Web Apps in un server di test, nel processo che fornisce informazioni sui modelli di utilizzo previsti e sulle prestazioni previste dei server di produzione.

  - **Amministratori di Lync**   questo team determina la strategia di distribuzione e gli script per l'installazione in cui è stato possibile. Il team è responsabile per assicurarsi che la modifica venga distribuita nell'ambiente di produzione ed è responsabile dell'amministrazione in seguito. Il team deve comprendere l'effetto delle modifiche e incorporarle nelle procedure prima che le modifiche vengano inserite in produzione

  - **Team di rete**   questo team è responsabile delle modifiche apportate alle regole del firewall che consentono l'accesso da Internet ai server di pool Lync interni. Il team è inoltre responsabile dell'uso degli amministratori di Lync per verificare che la larghezza di banda disponibile possa supportare il caricamento aggiuntivo.

  - **Team di sicurezza**   questo team valuta la sicurezza e minimizza i rischi. Il team di sicurezza deve rivedere le vulnerabilità note e garantire che i rischi per la sicurezza vengano minimizzati.

  - **Team di accettazione utente**   questo team è composto da utenti che vogliono testare il sistema e offrire feedback per migliorare.

Il processo di gestione delle modifiche definisce le responsabilità di ogni team e pianifica il lavoro da eseguire, incorporando i controlli e i test in cui sono necessari. I controlli di modifica variano a seconda della complessità e dell'effetto previsto di una modifica. Possono variare da approvazione automatica delle modifiche secondarie, per modificare le riunioni di revisione, a tutte le revisioni a livello di progetto. Per spiegarlo meglio, i gruppi di modifiche vengono discussi in questa sezione.

  - **Modifiche**   principali le modifiche principali hanno un effetto globale sul sistema e potrebbero richiedere l'input di vari team. Un esempio di questa operazione è l'aggiornamento a Lync Server 2013. Le modifiche principali riguardano molti team e forse sistemi diversi. Il processo di gestione delle modifiche includerà probabilmente una o più riunioni di revisione delle modifiche per informare i team che saranno coinvolti nella modifica o essere interessati dalla modifica.

  - **Modifiche**   significative le modifiche significative richiedono risorse significative per pianificare, creare e implementare. I controlli di modifica appropriati devono essere introdotti per garantire che l'effetto della modifica venga compreso, che le procedure di distribuzione vengano testate e che i piani di rollback e di emergenza siano pronti. Un esempio di modifica significativa consiste nel distribuire un nuovo aggiornamento cumulativo.

  - **Modifiche**   minori le modifiche minime non influiscono in modo significativo sull'ambiente IT, ad esempio modificando determinati criteri di Lync tramite il pannello di controllo di Microsoft Lync Server 2013.

  - **Modifiche standard le**   modifiche standard vengono eseguite regolarmente e sono ben comprese e documentate. Il processo di gestione delle modifiche dovrebbe rivedere tutte le modifiche apportate alle procedure. Non dovrebbe essere necessario per le modifiche di routine come la creazione di un database del contenuto o l'aggiunta di un utente.

Il seguente esempio di gestione delle modifiche esamina il modo in cui i diversi team interagiscono e le azioni che vengono eseguite quando viene distribuito un nuovo Service Pack. Queste azioni vengono organizzate e gestite dal processo di gestione delle modifiche.

  - **Sollevare una richiesta**   di modifica il team di sicurezza ha valutato il Service Pack più recente e ha confermato che risolve una possibile vulnerabilità nel sistema di produzione. Il team genera una richiesta di modifica per applicare il nuovo aggiornamento cumulativo a tutti i server che esegue Lync Server.

  - **Note sulla versione del Service Pack rivedere**   il team di amministrazione di Lync esamina le note sulla versione del Service Pack per identificare l'effetto sul sistema.

  - **Viene eseguita**   una serie di test di laboratorio il team di amministrazione di Lync deve eseguire gli aggiornamenti di test in un server in un ambiente di test per decidere se il Service Pack può essere applicato correttamente senza influire su nessuna delle applicazioni e dei sistemi server installati. Se sono presenti applicazioni di terze parti o create internamente che si interfacciano con Lync Server in un ambiente di produzione, queste devono essere anche testate. Questi test possono essere usati anche per stimare il tempo necessario per eseguire gli aggiornamenti.

  - **Gli utenti vengono informati dell'interruzione**   del team di amministrazione di Lync, del team di comunicazioni o dell'help desk dell'utente informa tutti gli utenti interessati sul ciclo di manutenzione pianificato e per quanto tempo il servizio non sarà disponibile.

  - **Per eseguire il backup completo di Lync prima dell'aggiornamento**   , il team di amministrazione di Lync deve verificare che sia presente un backup valido che può essere usato per ripristinare lo stato del sistema originale se l'installazione del Service Pack non riesce. È consigliabile che il backup venga ripristinato in un server di standby per avere questo sistema prontamente disponibile in caso di problemi.

  - **L'aggiornamento cumulativo viene distribuito**   il team di amministrazione di Lync esegue l'installazione durante il ciclo di manutenzione pianificato.

<div>

## <a name="managing-the-timing-of-changes"></a>Gestione dell'intervallo delle modifiche

È consigliabile implementare una procedura per la pianificazione delle modifiche per evitare interruzioni nelle sezioni sovrapposte del lavoro. Ad esempio, due team possono pianificare una modifica minore di un sistema. Un team può applicare un aggiornamento cumulativo in un pool mentre un altro team sta migrando gli utenti legacy in tale pool. Nessuno dei due team è influenzato dalle modifiche che l'altro team sta pianificando e ogni team potrebbe non conoscere necessariamente le modifiche che l'altro team sta pianificando. Se entrambe le modifiche si verificano contemporaneamente, potrebbero verificarsi problemi di implementazione delle modifiche. Inoltre, in caso di problemi dopo l'applicazione delle modifiche, ad esempio se la migrazione degli utenti non riesce, potrebbe essere difficile decidere quale modifica deve essere ripristinata. Devono essere configurati periodi di manutenzione regolari tra l'IT e la gestione per testare le modifiche e accettarle.

</div>

</div>

<span> </span>

</div>

</div>

</div>

