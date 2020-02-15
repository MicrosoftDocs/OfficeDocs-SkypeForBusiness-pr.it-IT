---
title: Configurazione del filtro per il trasferimento di file e degli URL per la messaggistica istantanea
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b741418790c5faf11c566afb27a477a67beb71ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a>Configurazione del filtro per il trasferimento di file e degli URL per la messaggistica istantanea in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Lo strumento di filtro di messaggistica istantanea intelligente consente di proteggere la distribuzione di Lync Server 2013 in base alla diffusione delle forme più comuni di virus con riduzione minima dell'esperienza utente. Utilizzare il filtro di protezione per messaggi istantanei per configurare filtri per bloccare i messaggi istantanei indesiderati o potenzialmente pericolosi provenienti da endpoint sconosciuti esterni al firewall aziendale. È possibile configurare i filtri specificando i criteri da utilizzare per determinare gli elementi da bloccare, ad esempio i messaggi istantanei contenenti collegamenti ipertestuali con prefissi specifici e file con estensioni specifiche.

Il filtro di protezione per messaggi istantanei offre le funzionalità seguenti:

  - Filtro avanzato per gli URL

  - Filtro avanzato per il trasferimento di file

La configurazione del filtro di protezione per messaggi istantanei prevede quanto segue:

  - Configurazione del filtro per gli URL

  - Configurazione del filtro per il trasferimento di file

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a>Modalità di applicazione delle opzioni di filtro ai messaggi istantanei

Prima di distribuire lo strumento di filtro dei messaggi di messaggistica istantanea intelligente, è necessario comprendere il modo in cui vengono applicate le opzioni di filtro quando i messaggi vengono instradati da un server Lync Server 2013 a un altro. Il modo in cui queste opzioni di filtro vengono applicate è coerente, indipendentemente dal fatto che i server si trovino in una singola organizzazione oppure oltre i limiti dell'organizzazione. Tale coerenza si applica al modo in cui i testi delle note e degli avvisi personalizzati vengono inseriti nei messaggi e inviati tra server.

<div>


> [!NOTE]
> Il filtro di protezione per messaggi istantanei comporta un aumento della quantità di risorse CPU necessarie per elaborare gli URL in un messaggio. Questo aumento della richiesta di CPU influisce anche sulle prestazioni di Lync Server.



</div>

Utilizzando la pagina **filtro URL** nel gruppo di **messaggistica istantanea e presenza** nel pannello di controllo di Lync Server, è possibile bloccare alcuni o tutti i collegamenti ipertestuali o configurare un avviso. L'avviso viene inserito all'inizio di un messaggio istantaneo contenente un collegamento ipertestuale quando per **Prefisso di collegamento ipertestuale** si seleziona l'opzione **Invia messaggio di avviso**.

Quando un messaggio istantaneo passa da un server a un altro, si applicano le linee guida generali seguenti:

  - Se un server blocca un messaggio istantaneo (perché è stata selezionata la casella di controllo **Blocca URL con estensione di file** nella pagina **Filtro URL** o perché per **Prefisso di collegamento ipertestuale** è stata selezionata l'opzione **Blocca collegamenti ipertestuali**), al client viene restituito un messaggio di errore. I server successivi non ricevono il messaggio istantaneo.

  - Se un server (Server1) aggiunge un avviso a un messaggio istantaneo contenente un collegamento ipertestuale attivo, un server successivo (Server2) che riceve il messaggio istantaneo può comunque eseguire un'azione diversa in base a tale collegamento ipertestuale attivo presente nel messaggio istantaneo e bloccare il messaggio o aggiungere un avviso. Se Server2 è configurato solo per aggiungere un avviso per l'URL, il precedente avviso aggiunto da Server1 viene rimosso e quello configurato in Server2 viene aggiunto all'inizio del messaggio istantaneo.

<div>


> [!NOTE]
> Se Lync Server 2013 è in esecuzione in un ambiente misto, Live Communications Server 2005 con SP1 è la versione minima necessaria per utilizzare l'applicazione filtro di messaggistica istantanea intelligente. Il filtro di protezione per messaggi istantanei non è supportato su Live Communications Server 2005 senza SP1.



</div>

<div>

## <a name="url-filtering"></a>Filtro per gli URL

Gli URL vengono filtrati in base al relativo prefisso di collegamento ipertestuale. Gli esempi seguenti sono prefissi validi:

  - www\*.

  - FTP.

  - http

Se non si configura il filtro per messaggi istantanei in modo da filtrare gli URL, tutti gli URL presenti nei messaggi istantanei verranno passati attraverso il server senza essere modificati. Se si configura il filtro per messaggi istantanei in modo da filtrare gli URL, gli URL presenti nei messaggi istantanei verranno filtrati in base alle opzioni selezionate nella finestra di dialogo **Modifica filtro URL** o **Crea nuovo filtro URL**.

  - **Abilita filtro**   URL questa opzione consente di abilitare il filtro URL per la distribuzione globale o per il sito selezionato.

  - **Blocca URL con estensione**   file il filtro messaggi istantanei blocca qualsiasi URL Internet o Intranet attivo contenente un file con un'estensione elencata in **estensioni di file da bloccare** nella finestra di dialogo **Modifica filtro file** . Quando un URL viene bloccato, al mittente viene visualizzato un messaggio di errore. Se viene selezionata, questa opzione ha la precedenza su tutte le altre opzioni di filtro per le estensioni di file definite in **Estensioni di file da bloccare**.
    
    <div>
    

    > [!IMPORTANT]
    > Il filtro delle estensioni di file è limitato ai nomi file standard. Il filtro potrebbe non funzionare con estensioni di file incorporate in altri nomi.

    
    </div>

Per configurare la modalità con cui vengono gestiti i collegamenti ipertestuali nelle conversazioni istantanee, selezionare una delle opzioni seguenti in **Prefisso di collegamento ipertestuale**:

  - **Non filtrare**   gli URL nei messaggi inviati tramite il server. Quando si seleziona questa opzione, viene visualizzata la casella **Consenti messaggio**. In tale** **casella specificare la nota che si desidera inserire all'inizio di ogni messaggio istantaneo contenente collegamenti ipertestuali. Questa nota può essere costituita al massimo da 65535 caratteri.

  - **Blocca collegamenti ipertestuali**   il recapito dei messaggi istantanei contenenti collegamenti ipertestuali attivi è bloccato da Lync Server e viene visualizzato un messaggio di errore al mittente.

  - **Invia messaggio**   di avviso Lync Server consente collegamenti ipertestuali attivi nei messaggi istantanei, ma include un avviso. Quando si seleziona questa opzione, viene visualizzata la casella **Messaggio di avviso**. In tale** **casella è necessario digitare l'avviso che si desidera inserire nei messaggi istantanei contenenti collegamenti ipertestuali validi. L'avviso ad esempio potrebbe segnalare i pericoli che si possono correre facendo clic su un collegamento sconosciuto o fare riferimento ai requisiti e ai criteri pertinenti dell'organizzazione. Questo avviso può essere costituito al massimo da 65535 caratteri.

Se si seleziona **Blocca collegamenti ipertestuali** o **Invia messaggio di avviso**, saranno disponibili le opzioni seguenti:

  - **Escludi collegamenti ipertestuali Intranet locali**   il filtro dei messaggi istantanei blocca solo gli URL Internet. Gli URL relativi ai percorsi all'interno della rete Intranet vengono passati attraverso il server senza essere modificati. Tuttavia, gli URL Intranet che i singoli server che eseguono Lync Server pass dipendono da quali tipi di siti Web locali sono considerati parte dell'area Intranet. Per verificare le impostazioni dell'area Intranet del server, vedere la procedura "per configurare le impostazioni della rete Intranet in Internet Explorer" in [Modify the default URL Filter in Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).

  - **Filtrare questi**   prefissi di collegamento ipertestuale per scegliere quali prefissi si desidera bloccare, fare clic su **Seleziona**e quindi in **Seleziona prefisso collegamento**ipertestuale aggiungere i prefissi all'elenco **prefissi di collegamento ipertestuale** .
    
    Tutti i prefissi, ad eccezione di **href**, devono terminare con un punto o i due punti oppure con un asterisco seguito da un punto. I prefissi validi possono contenere tutti i caratteri del set di caratteri URL validi, ad eccezione\*dell'asterisco (). Il set di caratteri URL validi è: \# \*+/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^\_ \` abcdefghijklmnopqrstuvwxyz | ~

</div>

<div>

## <a name="file-transfer-filtering"></a>Filtro per il trasferimento di file

Il filtro per il trasferimento di file riguarda sia i messaggi istantanei che le conferenze. Per le conferenze, queste impostazioni influiscono sia sulla funzionalità relativa agli stampati del client Office Live Meeting 2007 che sulle funzionalità di riproduzione multimediale.

<div>


> [!NOTE]
> Lync Server offre anche opzioni di impostazione del trasferimento di file. Questa opzione sul server viene offerta oltre ai controlli sul retro disponibili in Lync Server.



</div>

È possibile filtrare i trasferimenti di file durante le conversazioni istantanee, quando si utilizza la funzionalità relativa agli stampati del client Office Live Meeting 2007 e per le funzionalità di riproduzione multimediale per tutti i tipi di file. Per controllare i trasferimenti di file, è possibile impostare le opzioni seguenti:

  - **Attiva filtro**   file questa opzione consente di abilitare il filtro dei file per la distribuzione globale o per il sito selezionato.
    
    Quando si abilita il filtro per i file, è possibile selezionare una delle opzioni seguenti in **Trasferimento file**:
    
      - **Blocca tipi**   di file specifici specificare le richieste di trasferimento dei file filtrate dal server specificando un elenco di estensioni di file da bloccare. Le voci nell'elenco possono contenere tutti i caratteri standard, ma non il carattere jolly\*(). Nel client Office Live Meeting 2007 la funzionalità relativa agli stampati sarà abilitata, ma i file con le estensioni specificate non potranno essere caricati o scaricati. Se si seleziona la casella di controllo **Blocca URL con estensione di file** nelle impostazioni di un filtro per gli URL nella scheda **Filtro URL**, tale filtro utilizzerà questo stesso elenco per bloccare i collegamenti ipertestuali attivi contenenti una qualsiasi di queste estensioni di file. Per specificare quali tipi di file bloccare, fare clic su **Seleziona** e quindi in **Seleziona estensioni di file** aggiungere le estensioni di file desiderate all'elenco **Estensioni di file selezionate**.
    
      - **Blocca tutto**   il server rilascia tutti i messaggi istantanei che contengono richieste di trasferimento di file e restituisce un messaggio di errore al mittente della richiesta. La funzionalità relativa agli stampati del client Office Live Meeting 2007 sarà disabilitata.

<div>


> [!IMPORTANT]
> Il filtro delle estensioni di file è limitato ai nomi file standard. Il filtro potrebbe non funzionare con estensioni di file incorporate in altri nomi.



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Modificare il filtro di trasferimento file predefinito in Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [Creare un nuovo filtro trasferimento file in Lync Server 2013 per un sito specifico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [Modificare il filtro URL predefinito in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)

  - [Creare un nuovo filtro URL in Lync Server 2013 per gestire i collegamenti ipertestuali nelle conversazioni di messaggistica istantanea](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

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

