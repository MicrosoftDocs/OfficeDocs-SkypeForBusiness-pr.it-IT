---
title: 'Domande frequenti: provisioning della connettività Lync Server per Skype'
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
ms.openlocfilehash: 7204119aca18bfeb2539b0ee5eae5bb53f38efd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>Domande frequenti: provisioning della connettività Lync Server 2013 per Skype

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2019-03-22_

A partire da aprile 2019, si fermerà la raccolta e la conservazione delle informazioni di contatto per i clienti che hanno effettuato il provisioning per la Federazione Skype tramite il sito Web pic.lync.com. Questa modifica viene eseguita per garantire che il sistema di provisioning di pic.lync.com aderisca ai criteri di privacy Microsoft. 
 
Al termine della modifica, non sarà più possibile inviare aggiornamenti tramite posta elettronica in sospeso. Le modifiche al provisioning di PIC vengono in genere completate entro 24-48 ore dopo l'immissione. Se si verificano ancora problemi con la Federazione di Skype 48 ore dopo l'invio di una richiesta di provisioning, contattare il supporto tecnico Microsoft per approfondire ulteriormente.

> [!IMPORTANT]
> Come parte di questa modifica, tutte le informazioni di contatto inserite in precedenza verranno eliminate dal sistema entro la fine di aprile 2019.


**D: quali funzionalità sono supportate tra Microsoft Lync e Skype?**

**A:** Con Skype ora parte della famiglia Microsoft, le nuove possibilità si aprono per estendere gli scenari di comunicazioni unificate alle centinaia di milioni di persone che usano Skype. Questa combinazione consentirà ai clienti di Lync di connettersi e collaborare con fornitori, clienti e partner, basandosi sulla ricchezza di Lync e sulla portata di Skype.

  - Messaggi istantanei e chiamate audio e videochiamate-audio e videochiamate federate e messaggistica istantanea tra utenti di Lync e Skype

  - Condivisione presenza: informazioni sulla presenza di Exchange tra contatti federati

  - Amministrazione semplice: impostazioni e controlli per configurare le comunicazioni federate in conformità con i criteri e gli standard dell'organizzazione

**D: come si qualificano per connettere la distribuzione di Lync con Skype?**

**A:** Se si dispone di una licenza per la connettività Skype, è possibile:

  - Lync Server (2010 o 2013) più le licenze di accesso client standard di Lync Server ("Cal"; 2010 o 2013) per gli utenti e/o i dispositivi dell'organizzazione che si connetteranno a Skype. 

  - Lync Online (come licenze autonome o come parte di una famiglia di prodotti Office 365).Tuttavia, questo servizio (pic.lync.com) è solo per il provisioning di Lync Server e le distribuzioni Lync Server e Lync Online ibride.Il provisioning di Lync Online PIC viene eseguito nel pannello di controllo di Lync Online (LOCP).

**D: cosa devono fare gli utenti finali di Lync per connettersi ai contatti Skype?**

**A:** Dopo che un dominio è stato attivato e le funzionalità sono abilitate dall'amministratore di Lync di un'organizzazione, gli utenti di Lync possono aggiungere contatti Skype agli elenchi di contatti all'interno del client Lync.

**D: cosa devono fare gli utenti finali Skype per connettersi ai contatti di Lync?**

**A:** Tutti gli utenti Skype che desiderano connettersi a un utente di Lync devono avere un account Microsoft associato ai loro ID Skype ed eseguire l'accesso con l'account Microsoft.Questa funzionalità può essere abilitata nel client Skype.

**D: la Federazione con Windows Live è ancora disponibile?**

**A:** A partire da ottobre 2012, Microsoft ha iniziato ad aiutare gli utenti di Windows Live Messenger (WLM) a passare a Skype, in viaggio per poi ritirarsi da WLM.Lync continuerà a supportare la Federazione con WLM fintanto che WLM si trova nel mercato, ma non saranno consentite altre attivazioni di dominio Windows Live.Il movimento degli utenti di WLM è abilitato da Skype 6,0 per Mac e Windows (rilasciati il 25 ottobre 2012) che consente l'accesso con un account Microsoft (ad esempio, le stesse credenziali di WLM). Dopo aver effettuato l'accesso a Skype, WLM Buddy elenca automaticamente i contatti in Skype e gli utenti possono sfruttare le funzionalità di comunicazione espansa di Skype, ad esempio chiamare fissi e dispositivi mobili, condivisione dello schermo, videochiamate di gruppo e supporto per un'ampia varietà di dispositivi.Inoltre, i contatti di Lync federati degli utenti di WLM seguono la transizione in Skype con il resto dei loro elenchi di contatti e i messaggi istantanei tra Skype e Lync per queste persone saranno immediatamente disponibili. I clienti di Lync non devono eseguire alcuna operazione per consentire questa continuità di servizio.

**D: la Federazione con Yahoo\! o AOL è ancora disponibile?**

**A:** Non. Federazione con Yahoo\! e AOL erano contingenti al supporto di Yahoo\! e AOL.Sia per Yahoo\! e AOL, il servizio si è concluso il 30 giugno 2014. 

**D: è possibile provare la connettività Skype prima di acquistare Lync?**

**A:** La connettività Skype non è disponibile in base a una versione di valutazione. Al posto di una versione di valutazione, i clienti Lync con licenze idonee sono invitati a iscriversi semplicemente per il servizio da testare.

**D: quali informazioni sono necessarie per il provisioning?**

**A:** Per inviare una richiesta di provisioning in una licenza qualificata, è necessario eseguire le operazioni seguenti:

  - Numero di contratto Microsoft:
    
      - Supporto per contratti multilicenza Microsoft: numero di contratto multilicenza Microsoft
    
      - Microsoft Partner Network: ID partner della sede centrale
    
      - Contratto di licenza per il provider di servizi: numero di registrazione iniziale
    
      - Servizi ad alto volume: numero di registrazione prodotto

  - Nomi di dominio completi (FQDN) per il servizio Access Edge.
    
      - Il nome FQDN per almeno un servizio di Access Edge è obbligatorio.
    
      - Se l'organizzazione ha più di un server che usa il servizio Access Edge, specificare gli FQDN per ogni ulteriore servizio di Access Edge. Importante: se in precedenza è stato specificato un nome di dominio completo per il servizio Access Edge e si vuole modificarlo, il provisioning per la modifica può richiedere diversi giorni per il completamento e può causare interruzioni di servizio. Per evitare interruzioni del servizio, è consigliabile mantenere il nome di dominio completo specificato in precedenza del servizio Access Edge.

  - Domini SIP (Session Initiation Protocol). Questo è il suffisso di dominio dell'URI SIP usato attualmente dagli utenti per la messaggistica istantanea. Se l'organizzazione ha più di un dominio SIP, specificare il suffisso di dominio per ogni dominio usato per la messaggistica istantanea. Ad esempio, per user1@contoso.com, specifica contoso.com per il dominio SIP; per user1@example.fabrikam.com, specifica example.fabrikam.com come dominio SIP.
    
    <div>
    

    > [!NOTE]
    > Specifica solo il suffisso di dominio per il dominio SIP. Non specificare nomi di dominio completi, incluso il nome di dominio completo per il servizio Access Edge, per il dominio SIP.

    
    </div>

  - Informazioni di contatto. Specificare un indirizzo di posta elettronica per l'amministratore di ogni dominio SIP specificato.

**D: come si Abilita la connettività di Lync-Skype in uno scenario con domini separati?**

**A:** Se si ha uno scenario di dominio diviso Lync Online 2013 e Lync Server (con gli utenti sia online che in locale con lo stesso dominio SIP), abilitare la connettività Lync-Skype eseguendo questi due passaggi nell'ordine seguente

1.  Configurare la connettività Lync-Skype locale come spiegato nella Guida al provisioning di PIC.

2.  Attendere fino a quando non viene visualizzata la conferma che il dominio è stato eseguito il provisioning da Microsoft.

3.  Dopo aver visualizzato la conferma, usare l'interfaccia di amministrazione di Lync per attivare "comunicazioni esterne". Per altre informazioni, vedere[http://office.microsoft.com/en-us/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/en-us/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

Questo ordine è importante.È necessario configurare la connettività locale prima di abilitare le comunicazioni in Lync Online. Se l'ordine viene invertito, le informazioni immesse per il locale in <https://pic.lync.com> non verranno superate. Se è già stato configurato Lync Online per le comunicazioni esterne con questo dominio, è necessario disattivarlo, attendere 24 ore e ricominciare, prima di tutto immettendo le informazioni locali <https://pic.lync.com> e quindi attivando le comunicazioni esterne per Lync Online.

**D: è possibile eseguire il provisioning di più FQDN dei servizi di Access Edge per la connettività Skype?**

**A:** È possibile eseguire il provisioning di un solo FQDN di Access Edge per uno o più domini. È possibile eseguire il provisioning di più nomi di dominio completi di Access Edge, fino a 10 per ogni richiesta, se hanno domini distinti.

**D: è possibile ottenere l'elenco degli indirizzi di posta elettronica dell'account Microsoft trovati per l'organizzazione che richiede il provisioning?**

**A:** Non. Questi indirizzi sono considerati informazioni personali e non sono condivisi.

**D: come si aggiunge un contatto di Windows Live Messenger che contiene un ID contenente un dominio diverso da quello supportato da Windows Live?**

**A:** Se si aggiunge un utente di Windows Live Messenger con un account o un ID con un dominio non Windows Live, immettere l'indirizzo con il formato seguente: \<nome\>utente (\<nome\>di dominio) @msn. com, \<dove domain\> Name è il nome di dominio nell'indirizzo di posta elettronica dell'utente. Ad esempio, se si vuole aggiungere ted@contoso.com, è necessario usare il formato seguente: Ted (contoso. com) @msn. com. Per un elenco dei domini gestiti da Windows Live, vedere la sezione domini supportati in "problemi noti che si verificano con la messaggistica istantanea pubblica dopo l'installazione di Live Communications Server Service Pack 1 http://support.microsoft.com/?kbid=897567" at.

**D: quanto tempo è necessario per il processo di provisioning?**

**A:** Il provisioning può richiedere fino a 30 giorni.

**D: come si può sapere quando viene completato il provisioning?**

**A:** Microsoft invierà una notifica tramite posta elettronica durante il completamento del provisioning.

**D: come si aggiorna la configurazione o i dettagli di contatto inviati?**

**A:** Dopo aver completato il provisioning, è possibile aggiornare le informazioni nello stesso sito Web usato per richiedere il provisioning. Immettere il numero del contratto e quindi fare clic su Aggiorna servizio.

</div>

<span> </span>

</div>

</div>

</div>

