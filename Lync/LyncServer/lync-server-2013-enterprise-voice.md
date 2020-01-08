---
title: 'Lync Server 2013: VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7c8131c2f52dfc7ab061d8dec46ee34b62f89e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a>VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-04-08_

Con Enterprise Voice, Lync Server offre una funzionalità VoIP (Voice over Internet Protocol) autonoma che consente di migliorare o sostituire sistemi PBX (Private Branch Exchange) tradizionali. Gli utenti di Enterprise Voice possono chiamare i colleghi della rete VoIP o del PBX dell'organizzazione e possono chiamare i numeri di telefono tradizionali all'esterno dell'organizzazione. La soluzione VoIP aziendale include funzionalità di chiamata comuni, ad esempio risposta, inoltrare, trasferire, tenere, deviare, rilasciare e parcheggiare e la chiamata di 9-1-1 (E9-1-1) avanzata (E9-1-1 è disponibile solo negli Stati Uniti). Enterprise Voice supporta inoltre una vasta gamma di dispositivi IP e USB correnti e meno recenti.

<div>

## <a name="placing-and-receiving-calls"></a>Immissione e ricezione di chiamate

L'uso di Lync consente agli utenti di effettuare chiamate digitando un nome o un numero di telefono sulla tastiera oppure usando una tastierina telefonica visualizzata sullo schermo. Gli utenti possono anche avviare chiamate direttamente dall'elenco contatti. È anche possibile distribuire i dispositivi Lync Phone Edition, che sono dispositivi IP autonomi forniti da Microsoft partner.

Gli utenti possono avere più dispositivi telefonici registrati con Lync Server e possono passare facilmente tra di essi.

Gli utenti vengono avvisati delle chiamate in arrivo su tutti i loro dispositivi contemporaneamente, con suonerie personalizzabili su dispositivi telefonici IP e una notifica simile a un messaggio istantaneo nel PC.

Gli utenti possono anche impostare un singolo numero di telefono che si connette al telefono da tavolo, al PC e al cellulare, in modo che possano essere raggiunti ovunque si trovino.

</div>

<div>

## <a name="basic-call-features"></a>Funzionalità di base delle chiamate

Durante una chiamata, un utente può rispondere alle chiamate in arrivo aggiuntive o avviare le chiamate in uscita e la chiamata attiva esistente viene inserita automaticamente in attesa. Le chiamate possono essere trasferite da un utente a un altro, direttamente o dopo che il primo utente parla in privato con il secondo utente. Gli utenti possono anche trasferire le chiamate a un altro dispositivo; ad esempio, potrebbero trasferire una chiamata attiva al proprio telefono cellulare mentre camminano fuori dalla porta del loro ufficio.

</div>

<div>

## <a name="richer-communications"></a>Comunicazioni più avanzate

Quando si parla a un altro utente con Lync, gli utenti possono aggiungere facilmente testo, video o condivisione desktop alla chiamata. La caratteristica do-not-disturb è integrata con le impostazioni di presenza in Lync.

Con la messaggistica UNIFICAta di Exchange, Lync e Lync Server si integrano con Microsoft Exchange Server 2013 e Microsoft Outlook 2013. Gli utenti possono vedere se sono presenti nuovi messaggi vocali nella finestra di Lync e nella posta elettronica. Durante la posta elettronica, è possibile fare clic per riprodurre l'audio della segreteria telefonica in un messaggio di posta elettronica o visualizzare una trascrizione del messaggio della segreteria telefonica.

</div>

<div>

## <a name="advanced-calling-features"></a>Funzionalità per le chiamate avanzate

Enterprise Voice include diverse funzionalità di chiamata avanzate, ad esempio la delega delle chiamate di Lync, le chiamate di Team, il pick-up delle chiamate di gruppo e i gruppi di risposta.

La delega delle chiamate di Lync consente agli utenti di delegare la gestione delle chiamate a uno o più assistenti, passando alle **impostazioni di inoltro delle chiamate delle** **Opzioni** \> **degli strumenti** \> . Il delegato può eseguire più attività di chiamata per conto dell'utente, incluse le chiamate di selezione, l'immissione di chiamate e l'avvio di conferenze.

<div>


> [!IMPORTANT]  
> Potrebbe essere alla ricerca di un'altra caratteristica denominata in modo simile, delegazione del calendario Lync. Non richiede la funzionalità VoIP aziendale e consente agli utenti di pianificare riunioni di Lync Online da Outlook. Se sei qui per cercare queste informazioni, ti consigliamo di verificare <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> per informazioni su come abilitare la sincronizzazione dei delegati di Exchange.



</div>

La chiamata in team consente a un utente di avere chiamate in arrivo squillare simultaneamente i telefoni dei membri del team in modo che tutti gli utenti possano rispondere alla chiamata.

Raccolta di chiamate di gruppo, una nuova funzionalità degli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013, consente agli utenti di rispondere alle chiamate in arrivo ai propri colleghi dal proprio telefono. Il ritiro delle chiamate di gruppo è diverso da quello delle chiamate in team principalmente in quanto una chiamata in arrivo squilla solo presso il telefono del destinatario previsto, ma qualsiasi altro utente può scegliere di rispondere chiamando un numero del gruppo di selezione chiamata.

I gruppi di risposta possono essere configurati per l'accodamento e il routing intelligente delle chiamate agli agenti designati. Gli usi comuni includono helpdesk IT, hotline risorse umane e altri centri di contatto interni.

</div>

<div>

## <a name="enterprise-voice-administration"></a>Amministrazione di VoIP aziendale

Lync Server usa standard e interfacce pubblicate per interagire con l'infrastruttura esistente. Supporta sia le opzioni di gateway che SIP, ad esempio il trunking SIP, per l'interconnessione ai sistemi IP PBX e le reti PSTN, in modo da poter eseguire la migrazione degli utenti a Enterprise Voice nel tempo, riducendo al minimo le interruzioni. Lync Server supporta codec tradizionali come G. 711, G. 722 e G. 723.1 per l'interoperabilità con le tradizionali soluzioni VoIP.

Con il controllo di ammissione alle chiamate (CAC), gli amministratori possono impostare limiti per la quantità di traffico vocale e video di Lync Server eseguito sui collegamenti di rete vincolati e specificare l'azione da eseguire se una nuova chiamata supera il limite. Le azioni possono includere il routing in base a un percorso alternativo o rifiutare la chiamata.

Lync Server funziona con gli elettrodomestici Survivable di terze parti per ottenere servizi di chiamata locali e la connessione a PSTN presso le filiali, in caso di errore WAN nel sito centrale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

