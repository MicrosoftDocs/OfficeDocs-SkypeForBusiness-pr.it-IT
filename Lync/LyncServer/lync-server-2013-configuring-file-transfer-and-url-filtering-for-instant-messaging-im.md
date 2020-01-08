---
title: Configurazione del filtro del trasferimento di file e degli URL per la messaggistica istantanea
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a9e39799815a86bc255b9aa58627df94eb3f81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a>Configurazione del filtro del trasferimento di file e degli URL per la messaggistica istantanea in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Lo strumento di filtro ISTANTANEo intelligente consente di proteggere la distribuzione di Lync Server 2013 con la diffusione delle forme più comuni di virus con una degradazione minima dell'esperienza utente. Usare il filtro istantaneo intelligente per configurare i filtri per bloccare i messaggi istantanei non richiesti o potenzialmente nocivi da endpoint sconosciuti esterni al firewall aziendale. I filtri vengono configurati specificando i criteri da usare per determinare gli elementi da bloccare, ad esempio i messaggi istantanei contenenti collegamenti ipertestuali con prefissi e file specifici con specifiche estensioni.

Il filtro ISTANTANEo intelligente offre gli elementi seguenti:

  - Filtro di URL avanzato.

  - Filtro di trasferimento file avanzato.

La configurazione di un filtro ISTANTANEo intelligente include le seguenti:

  - Configurazione del filtro URL.

  - Configurazione del filtro trasferimento file.

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a>Come vengono applicate le opzioni di filtro ai messaggi istantanei

Prima di distribuire lo strumento di filtro messaggi ISTANTANEi intelligente, è necessario capire in che modo le opzioni di filtro vengono applicate quando i messaggi vengono instradati da un server di Lync Server 2013 a un altro. Il modo in cui queste opzioni di filtro vengono applicate è coerente, indipendentemente dal fatto che i server si trovino in un'unica organizzazione o in tutti i confini aziendali. Questa coerenza si applica al modo in cui i testi personalizzati di avviso e di avviso vengono inseriti nei messaggi e inviati attraverso i server.

<div>


> [!NOTE]
> Il filtro dei messaggi istantanei aumenta la quantità di risorse della CPU necessarie per elaborare gli URL in un messaggio. Questo aumento della richiesta di CPU influenza anche le prestazioni di Lync Server.



</div>

Usando la pagina **filtro URL** nel gruppo **messaggistica istantanea e presenza** del pannello di controllo di Lync Server, è possibile bloccare alcuni o tutti i collegamenti ipertestuali o configurare un avviso. L'avviso viene inserito all'inizio di un messaggio istantaneo che contiene un collegamento ipertestuale quando si sceglie l'opzione **Invia messaggio di avviso**per il **prefisso del collegamento ipertestuale** .

Quando un messaggio istantaneo viaggia da un server a un altro, si applicano le linee guida generali seguenti:

  - Se un server blocca un messaggio istantaneo, perché è stata selezionata la casella di controllo **Blocca URL con estensione file** nella pagina **filtro URL** o perché si è scelto l'opzione **prefisso collegamento ipertestuale** per **bloccare i collegamenti ipertestuali**, viene restituito un messaggio di errore al client. I server successivi non ricevono questo messaggio istantaneo.

  - Se un server (Server1) aggiunge un avviso a un messaggio istantaneo che contiene un collegamento ipertestuale attivo, un server successivo (Server2) che riceve questo messaggio istantaneo può comunque eseguire un'azione diversa in base a questo collegamento ipertestuale attivo presente nel messaggio istantaneo e bloccare l' messaggio istantaneo o aggiunta di un avviso. Se Server2 è configurato solo per aggiungere un avviso per questo URL, l'avviso precedente aggiunto da Server1 viene rimosso e l'avviso configurato su Server2 viene aggiunto all'inizio del messaggio istantaneo.

<div>


> [!NOTE]
> Se si esegue Lync Server 2013 in un ambiente misto, Live Communications Server 2005 con SP1 è la versione minima necessaria per usare l'applicazione di filtro messaggi istantanei intelligente. Il filtro di messaggistica istantanea intelligente non è supportato in Live Communications Server 2005 senza SP1.



</div>

<div>

## <a name="url-filtering"></a>Filtro URL

Gli URL vengono filtrati in base al prefisso del collegamento ipertestuale. Gli esempi seguenti sono prefissi validi:

  - www\*.

  - FTP.

  - http

Se non si configura il filtro per i messaggi istantanei per eseguire il filtro degli URL, tutti gli URL contenuti nei messaggi istantanei vengono passati non modificati tramite il server. Se si configura il filtro dei messaggi istantanei per eseguire il filtro URL, gli URL nei messaggi istantanei vengono filtrati in base alle opzioni selezionate nella finestra di dialogo **Modifica filtro URL** o **nuovo filtro URL** .

  - **Abilita filtro**   URL questa opzione consente di filtrare gli URL per la distribuzione globale o per il sito selezionato.

  - **Bloccare gli URL con estensione**   di file il filtro messaggi istantanei blocca qualsiasi URL Intranet o Internet attivo che contiene un file con un'estensione elencata in **estensioni di file da bloccare** nella finestra di dialogo **Modifica filtro file** . Quando un URL è bloccato, al mittente viene visualizzato un messaggio di errore. Se selezionata, questa opzione ha la precedenza su tutte le altre opzioni di filtro per tutte le estensioni di file definite in **estensioni di file da bloccare**.
    
    <div>
    

    > [!IMPORTANT]
    > Il filtro delle estensioni di file è limitato ai nomi di file standard. Il filtro potrebbe non funzionare con le estensioni di file incorporate in altri nomi.

    
    </div>

Per configurare la modalità di gestione dei collegamenti ipertestuali nelle conversazioni di messaggistica istantanea, selezionare una delle opzioni seguenti in **prefisso collegamento ipertestuale**:

  - **Non filtrare**   gli URL nei messaggi inviati tramite il server. Quando si sceglie questa opzione, viene visualizzata la casella **Consenti messaggio** . Nella casella **Consenti messaggio** specificare l'avviso che si vuole inserire all'inizio di ogni messaggio istantaneo contenente collegamenti ipertestuali. Questo avviso può essere costituito da non più di 65535 caratteri.

  - **Blocca collegamenti ipertestuali**   il recapito dei messaggi istantanei contenenti collegamenti ipertestuali attivi viene bloccato da Lync Server e viene visualizzato un messaggio di errore al mittente.

  - **Invia messaggio**   di avviso Lync Server consente collegamenti ipertestuali attivi nei messaggi istantanei, ma include un avviso. Quando si sceglie questa opzione, viene visualizzata la finestra di **messaggio di avviso** . Nella casella **messaggio di avviso** è necessario digitare l'avviso che si desidera includere nei messaggi istantanei contenenti collegamenti ipertestuali validi. Ad esempio, questo avviso potrebbe indicare i potenziali pericoli di fare clic su un collegamento sconosciuto oppure può fare riferimento ai criteri e ai requisiti pertinenti dell'organizzazione. L'avviso non può essere maggiore di 65535 caratteri.

Se si seleziona **Blocca collegamenti ipertestuali** o **Invia messaggio di avviso**, sono disponibili le opzioni seguenti:

  - **Escludi collegamenti ipertestuali Intranet locali**   il filtro per i messaggi istantanei blocca solo gli URL Internet. Gli URL per le posizioni all'interno della Intranet vengono passati non modificati tramite il server. Tuttavia, gli URL Intranet che i singoli server che esegue Lync Server passano dipendono dai tipi di siti Web locali considerati parte dell'area Intranet. Per controllare le impostazioni dell'area Intranet del server, vedere la procedura "per configurare le impostazioni della Intranet in Internet Explorer" in [modificare il filtro URL predefinito in Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).

  - **Filtrare questi prefissi dei collegamenti ipertestuali**   per scegliere i prefissi da bloccare, fare clic su **Seleziona**e quindi, in **Seleziona prefisso collegamento**ipertestuale, aggiungere i prefissi all'elenco **prefissi collegamento ipertestuale** .
    
    Tutti i prefissi eccetto **href** devono terminare con un punto o due punti oppure un asterisco seguito da un punto. I prefissi validi possono contenere qualsiasi carattere nel set di caratteri URL validi eccetto l'asterisco (\*). Il set di caratteri validi per gli URL \# \*è: +/0123456789 =\_ \` @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ abcdefghijklmnopqrstuvwxyz | ~

</div>

<div>

## <a name="file-transfer-filtering"></a>Filtro trasferimento file

Filtro trasferimento filtri influisce su messaggi istantanei e conferenze. Per le conferenze, queste impostazioni influiscono sulla caratteristica stampati nel client di Office Live Meeting 2007 e nelle funzionalità di riproduzione multimediale.

<div>


> [!NOTE]
> Lync Server offre anche opzioni per l'impostazione del trasferimento di file. Questa opzione lato server è disponibile oltre ai controlli lato client disponibili in Lync Server.



</div>

È possibile filtrare i trasferimenti di file durante le conversazioni istantanee, quando si usa la caratteristica stampati nel client Office Live Meeting 2007 e per le funzionalità di riproduzione multimediale per tutti i tipi di file. È possibile impostare le opzioni seguenti per controllare i trasferimenti di file:

  - **Abilita filtro**   file questa opzione consente di filtrare i file per la distribuzione globale o per il sito selezionato.
    
    Quando si Abilita il filtro file, è possibile scegliere una delle opzioni seguenti in **trasferimento file**:
    
      - **Blocca tipi**   di file specifici per specificare quali richieste di trasferimento di file vengono filtrate dal server specificando un elenco di estensioni di file da bloccare. Le voci nell'elenco possono contenere tutti i caratteri standard, ma non il carattere jolly\*(). Nel client Office Live Meeting 2007 è abilitata la caratteristica stampati, ma non è possibile caricare o scaricare qualsiasi file con questa estensione. Se si seleziona la casella di controllo **Blocca URL con estensione di file** nelle impostazioni per un filtro URL elencato nella scheda **filtro URL** , il filtro URL usa lo stesso elenco per bloccare i collegamenti ipertestuali attivi che contengono una di queste estensioni di file. Per scegliere i tipi di file da bloccare, fare clic su **Seleziona**e quindi, in **Seleziona tipo di file**, aggiungere le estensioni del tipo di file all'elenco delle estensioni del **tipo di file selezionato** .
    
      - **Blocca tutto**   il server rilascia tutti i messaggi istantanei che contengono richieste di trasferimento di file e restituisce un messaggio di errore al mittente della richiesta. La caratteristica stampati nel client Office Live Meeting 2007 è disabilitata.

<div>


> [!IMPORTANT]
> Il filtro delle estensioni di file è limitato ai nomi di file standard. Il filtro potrebbe non funzionare con le estensioni di file incorporate in altri nomi.



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Modificare il filtro di trasferimento file predefinito in Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [Creare un nuovo filtro per il trasferimento di file in Lync Server 2013 per un sito specifico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [Modificare il filtro URL predefinito in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)

  - [Creare un nuovo filtro URL in Lync Server 2013 per gestire i collegamenti ipertestuali nelle conversazioni ISTANTANEe](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Gestione delle impostazioni di messaggistica istantanea e presenza in Lync Server 2013](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

