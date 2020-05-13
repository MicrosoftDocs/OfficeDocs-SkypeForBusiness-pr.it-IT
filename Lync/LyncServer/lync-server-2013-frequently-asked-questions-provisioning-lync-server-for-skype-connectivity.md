---
title: 'Domande frequenti: provisioning di Lync Server per la connettività Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Frequently Asked Questions: Provisioning Lync Server for Skype connectivity'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440172(v=OCS.15)
ms:contentKeyID: 57793362
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45fb31e6f9319f0a1a7a7eadca8f11c1c3ad1a03
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>Domande frequenti: provisioning di Lync Server 2013 per la connettività Skype

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2019-03-22_

A partire da aprile 2019, si interromperà la raccolta e la conservazione delle informazioni di contatto per i clienti che sono stati provisionati per la Federazione Skype tramite il sito Web pic.lync.com. Questa modifica viene apportata per garantire che il sistema di provisioning di pic.lync.com sia conforme ai criteri di privacy di Microsoft. 
 
Una volta che questa modifica è attiva, non sarà più possibile fornire gli aggiornamenti della posta elettronica sulle modifiche di provisioning in sospeso. Le modifiche del provisioning delle PIC vengono in genere completate entro 24-48 ore dopo l'immissione. Se si verificano ancora problemi relativi alla Federazione di Skype 48 ore dopo l'invio di una richiesta di provisioning, contattare il supporto tecnico Microsoft per approfondire ulteriormente.

> [!IMPORTANT]
> Come parte di questa modifica, tutte le informazioni di contatto inserite in precedenza verranno eliminate dal sistema entro la fine di aprile 2019.


**D: quali funzionalità sono supportate tra Microsoft Lync e Skype?**

**A:** Con Skype Now facente parte della famiglia Microsoft, nuove possibilità si aprono per estendere gli scenari di comunicazione unificata alle centinaia di milioni di persone che usano Skype. Questa combinazione consentirà ai clienti di Lync di connettersi e collaborare con fornitori, clienti e partner, basandosi sulla ricchezza di Lync e sulla portata di Skype.

  - Chiamate istantanee e di audio e video: chiamata audio e video federata e messaggistica istantanea tra gli utenti di Lync e Skype

  - Condivisione presenza-informazioni sulla presenza di Exchange tra contatti federati

  - Amministrazione semplice: impostazioni e controlli che consentono di configurare le comunicazioni federate secondo i criteri e gli standard dell'organizzazione

**D: come si qualificano per connettere la distribuzione di Lync con Skype?**

**A:** Se si dispone di una licenza per la connettività Skype, è possibile eseguire le operazioni seguenti:

  - Lync Server (2010 o 2013) e le licenze di accesso client di Lync Server standard ("Cal"; 2010 o 2013) per gli utenti e/o i dispositivi dell'organizzazione che si connetteranno a Skype. 

  - Lync Online (come licenze autonome o come parte di una famiglia di prodotti di Office 365).Tuttavia, questo servizio (pic.lync.com) è solo per il provisioning di Lync Server e delle distribuzioni ibride di Lync Server e Lync Online.Il provisioning di Lync Online PIC viene eseguito in Lync Online Control Panel (LOCP).

**D: che cosa devono fare gli utenti finali di Lync per connettersi ai contatti Skype?**

**A:** Dopo che un dominio è stato attivato e le funzionalità sono state abilitate dall'amministratore di Lync di un'organizzazione, gli utenti di Lync possono aggiungere contatti Skype ai propri elenchi di contatti all'interno del client Lync.

**D: che cosa devono fare gli utenti finali Skype per la connessione a contatti di Lync?**

**A:** Tutti gli utenti Skype che desiderano connettersi a un utente di Lync devono disporre di un account Microsoft associato ai propri ID Skype e accedere utilizzando l'account Microsoft.Questo può essere abilitato all'interno del client Skype.

**D: la Federazione con Windows Live è ancora disponibile?**

**A:** A partire da ottobre 2012, Microsoft ha iniziato a aiutare gli utenti di Windows Live Messenger (WLM) a spostarsi su Skype, in rotta verso la fine del ritiro di WLM.Lync continuerà a supportare la Federazione con WLM fintanto che WLM è nel mercato, ma non verranno consentite altre attivazioni di Windows Live Domain.Il movimento degli utenti di WLM è abilitato dal Skype 6,0 per Mac e Windows (rilasciati il 25 ottobre 2012), che consente l'accesso con un account Microsoft (ad esempio, le stesse credenziali di WLM). Dopo aver eseguito l'accesso a Skype, gli elenchi di WLM Buddy vengono inseriti automaticamente in Skype e gli utenti possono usufruire delle funzionalità di comunicazione espanse di Skype, come la chiamata di telefoni fissi e mobili, la condivisione dello schermo, la videochiamata di gruppo e il supporto per un'ampia gamma di dispositivi.Inoltre, i contatti federati di Lync degli utenti di WLM seguono la transizione in Skype con il resto degli elenchi di contatti e i messaggi istantanei tra Skype e Lync per questi interlocutori saranno immediatamente disponibili. I clienti di Lync non devono eseguire alcuna operazione per abilitare questa continuità del servizio.

**D: la Federazione con Yahoo \! o AOL è ancora disponibile?**

**A:** No. Federazione con Yahoo\! e AOL sono stati contingenti al supporto di Yahoo\! e AOL.Sia per Yahoo\! e AOL, il servizio si è concluso il 30 giugno 2014. 

**D: è possibile provare la connettività Skype prima di acquistare Lync?**

**A:** La connettività Skype non è disponibile su base di prova. Al posto di una versione di valutazione, i clienti Lync con licenze idonee sono invitati a iscriversi semplicemente affinché il servizio venga testato.

**D: quali informazioni sono necessarie per il provisioning?**

**A:** Per inviare una richiesta di provisioning con una licenza qualificata, è necessario eseguire le operazioni seguenti:

  - Numero del contratto Microsoft:
    
      - Supporto per contratti multilicenza Microsoft: numero contratto contratti multilicenza Microsoft
    
      - Microsoft Partner Network: ID del partner della sede centrale
    
      - Contratto di licenza per il provider di servizi: numero di registrazione iniziale
    
      - Servizi ad alto volume: numero di registrazione prodotto

  - Nomi di dominio completi (FQDN) per il servizio Access Edge.
    
      - FQDN per almeno un servizio Access Edge è necessario.
    
      - Se nell'organizzazione sono presenti più server che eseguono il servizio Access Edge, specificare gli FQDN per ogni servizio di Access Edge aggiuntivo. Importante: se in precedenza è stato specificato un nome di dominio completo per il servizio Access Edge e si desidera modificarlo, il provisioning per la modifica può richiedere diversi giorni per il completamento e può provocare interruzioni del servizio. Per evitare interruzioni del servizio, è consigliabile mantenere il nome di dominio completo specificato in precedenza del servizio Access Edge.

  - Domini SIP (Session Initiation Protocol). Questo è il suffisso di dominio dell'URI SIP utilizzato attualmente dagli utenti per la messaggistica istantanea. Se l'organizzazione dispone di più di un dominio SIP, specificare il suffisso di dominio per ogni dominio utilizzato per la messaggistica istantanea. Ad esempio, per user1@contoso.com, specificare contoso.com per il dominio SIP. per user1@example.fabrikam.com, specificare example.fabrikam.com come dominio SIP.
    
    <div>
    

    > [!NOTE]
    > Specificare solo il suffisso di dominio per il dominio SIP. Non specificare FQDN, incluso il nome di dominio completo per il servizio Access Edge, per il dominio SIP.

    
    </div>

  - Informazioni di contatto. Specificare un indirizzo di posta elettronica per l'amministratore di ogni dominio SIP specificato.

**D: come si attiva la connettività Lync-Skype in uno scenario Split-Domain?**

**A:** Se si dispone di uno scenario split-domain locale di Lync Online 2013 e Lync Server (con gli utenti sia online che locali utilizzando lo stesso dominio SIP), abilitare la connettività Lync-Skype eseguendo questi due passaggi nell'ordine seguente:

1.  Configurare la connettività Lync-Skype locale come spiegato nella Guida al provisioning del PIC.

2.  Attendere fino a quando non viene visualizzata la conferma del provisioning del dominio da parte di Microsoft.

3.  Dopo aver visualizzato la conferma, utilizzare l'interfaccia di amministrazione di Lync per abilitare "comunicazioni esterne". Per ulteriori informazioni, vedere[https://office.microsoft.com/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](https://office.microsoft.com/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

Questo ordine è importante.Prima di abilitare le comunicazioni in Lync Online, è necessario configurare la connettività locale. Se l'ordine viene annullato, le informazioni immesse per il locale in non passeranno <https://pic.lync.com> . Se è già stata configurata Lync Online per le comunicazioni esterne con questo dominio, è necessario disattivarla, attendere 24 ore e ricominciare, per prima cosa, immettendo le informazioni locali <https://pic.lync.com> e quindi attivando le comunicazioni esterne per Lync Online.

**D: è possibile eseguire il provisioning di più FQDN del servizio Access Edge per la connettività Skype?**

**A:** È possibile eseguire il provisioning di un solo FQDN di Access Edge per uno o più domini. Se dispongono di domini distinti, è possibile eseguire il provisioning di più FQDN di Access Edge, fino a 10 per ogni richiesta.

**D: è possibile ottenere l'elenco degli indirizzi di posta elettronica dell'account Microsoft individuati per l'organizzazione che richiede il provisioning?**

**A:** No. Questi indirizzi sono considerati informazioni di identificazione personale e non sono condivisi.

**D: come si aggiunge un contatto di Windows Live Messenger con un ID contenente un dominio diverso da quello supportato da Windows Live?**

**A:** Se si sta aggiungendo un utente di Windows Live Messenger con un account o un ID con un dominio non Windows Live, immettere l'indirizzo nel formato seguente: \< nome utente \> ( \< nome di \> dominio) @msn. com, dove \< Domain Name \> è il nome di dominio nell'indirizzo di posta elettronica dell'utente. Ad esempio, se si desidera aggiungere ted@contoso.com, è necessario utilizzare il formato seguente: Ted (contoso. com) @msn. com. Per un elenco dei domini amministrati da Windows Live, vedere la sezione relativa ai domini supportati in "problemi noti che si verificano con la messaggistica istantanea pubblica dopo l'installazione di Live Communications Server Service Pack 1" all'indirizzo https://support.microsoft.com/?kbid=897567 .

**D: qual è il tempo necessario per il processo di provisioning?**

**A:** Il provisioning può richiedere fino a 30 giorni.

**D: in che modo è necessario sapere se il provisioning è completo?**

**A:** Microsoft invierà una notifica tramite posta elettronica al completamento del provisioning.

**D: come si aggiornano le informazioni di configurazione o i contatti inviati?**

**A:** È possibile aggiornare le informazioni nello stesso sito Web utilizzato per richiedere il provisioning, dopo il completamento del provisioning. Immettere il numero del contratto e quindi fare clic su Aggiorna servizio.

</div>

<span> </span>

</div>

</div>

</div>
