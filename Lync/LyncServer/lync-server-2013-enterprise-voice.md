---
title: Lync Server 2013 VoIP aziendale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39179f1db1c547081e059d9b3ee275c924621cab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533173"
---
# <a name="enterprise-voice-in-lync-server-2013"></a>VoIP aziendale in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-04-08_

Con VoIP aziendale, Lync Server offre una voce autonoma che offre un protocollo Voice over Internet Protocol per migliorare o sostituire i sistemi PBX (Private Branch Exchange) tradizionali. Gli utenti di VoIP aziendale possono chiamare i colleghi sulla rete VoIP o sul sistema PBX dell'organizzazione, nonché numeri di telefono tradizionali all'esterno dell'organizzazione. La soluzione VoIP aziendale include funzionalità di chiamata comuni quali la risposta, l'inoltro, il trasferimento, la conservazione, la deviazione, la liberazione e il parco e la chiamata avanzata 9-1-1 (E9-1-1) (il servizio E9-1-1 è disponibile solo negli Stati Uniti). VoIP aziendale supporta anche una vasta gamma di dispositivi IP e USB correnti e meno recenti.

<div>

## <a name="placing-and-receiving-calls"></a>Effettuare e ricevere chiamate

Utilizzando Lync, gli utenti possono effettuare chiamate digitando un nome o un numero di telefono sulla propria tastiera oppure utilizzando un tastierino numerico visualizzato sullo schermo. Gli utenti possono anche avviare le chiamate direttamente dall'elenco dei contatti. È inoltre possibile distribuire i dispositivi Lync Phone Edition, che sono dispositivi telefonici IP autonomi forniti da Microsoft Partners.

Gli utenti possono disporre di più dispositivi telefonici registrati con Lync Server e possono passare facilmente tra di essi.

Vengono avvisati in caso di chiamate in arrivo su tutti i dispositivi contemporaneamente, mediante suonerie personalizzabili sui dispositivi telefonici IP e una notifica simile a un messaggio istantaneo sul PC.

Gli utenti possono inoltre impostare un singolo numero di telefono che si connette al telefono da tavolo, al PC e al cellulare, in modo da essere raggiungibili in qualsiasi luogo.

</div>

<div>

## <a name="basic-call-features"></a>Funzionalità di chiamata di base

Durante una chiamata, un utente può rispondere ad altre chiamate in arrivo o avviare chiamate in uscita mentre la chiamata attiva esistente viene automaticamente messa in attesa. Le chiamate possono essere trasferite da un utente all'altro, direttamente o dopo che il primo utente ha parlato in privato con il secondo. Gli utenti possono inoltre trasferire le chiamate a un altro dispositivo, ad esempio possono trasferire una chiamata attiva al loro cellulare mentre varcano la porta del proprio ufficio.

</div>

<div>

## <a name="richer-communications"></a>Comunicazioni più complete

Quando si parla a un altro utente con Lync, gli utenti possono aggiungere facilmente testo, video o condivisione del desktop alla chiamata. La funzionalità do-not-disturb è integrata con le impostazioni di presenza in Lync.

Con la messaggistica unificata di Exchange (UM), Lync e Lync Server si integrano con Microsoft Exchange Server 2013 e Microsoft Outlook 2013. Gli utenti possono vedere se dispongono di una nuova segreteria telefonica sia nella finestra di Lync sia nella posta elettronica. Mentre è aperto il programma di posta elettronica, possono fare clic per riprodurre l'audio della segreteria telefonica in un messaggio di posta elettronica o visualizzare una trascrizione del messaggio della segreteria telefonica.

</div>

<div>

## <a name="advanced-calling-features"></a>Funzionalità di chiamata avanzate

VoIP aziendale include anche diverse funzionalità di chiamata avanzate, ad esempio la delega delle chiamate di Lync, la chiamata di Team, il prelievo di chiamate di gruppo e i Response Group.

La delega delle chiamate di Lync consente agli utenti di delegare la gestione delle chiamate a uno **Tools** o più assistenti, accedendo alle \> **Options** \> **impostazioni delle opzioni di inoltro delle chiamate**degli strumenti. Consente inoltre di eseguire più attività di chiamata per conto dell'utente, ad esempio la selezione delle chiamate, l'esecuzione di chiamate e l'avvio delle conferenze.

<div>


> [!IMPORTANT]  
> È possibile cercare un'altra caratteristica denominata in modo simile, la delega del calendario di Lync. Non richiede la funzionalità VoIP aziendale e consente agli utenti di pianificare riunioni di Lync Online da Outlook. Se si è venuti a trovare le informazioni, è consigliabile consultare <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> per informazioni sull'abilitazione della sincronizzazione dei delegati di Exchange.



</div>

Il team Calling consente a un utente di effettuare chiamate in entrata contemporaneamente squillare i telefoni dei compagni di squadra in modo che tutti i membri del team possano rispondere alla chiamata.

Prelievo delle chiamate di gruppo, una nuova caratteristica negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013, consente agli utenti di rispondere alle chiamate in arrivo ai propri colleghi tramite i propri telefoni. Il prelievo delle chiamate di gruppo è diverso dalla chiamata del team principalmente in quanto una chiamata in arrivo squilla solo nel telefono del destinatario previsto, ma qualsiasi altro utente può scegliere di rispondere componendo un numero di gruppo di prelievo di chiamata.

I Response Group possono essere impostati per l'accodamento e il routing intelligente delle chiamate agli agenti designati. Gli usi comuni includono l'helpdesk IT, le hotline delle risorse umane e altri centri di contatto interni.

</div>

<div>

## <a name="enterprise-voice-administration"></a>Amministrazione VoIP aziendale

Lync Server utilizza gli standard e le interfacce pubblicate per interagire con l'infrastruttura esistente. Supporta sia le opzioni gateway che SIP, ad esempio il trunking SIP, per l'interconnessione con i sistemi IP PBX e le reti PSTN, in modo da consentire la migrazione graduale degli utenti a VoIP aziendale, riducendo al tempo stesso le interruzioni. Lync Server supporta codec tradizionali quali G. 711, G. 722 e G. 723.1 per l'interoperabilità con le soluzioni VoIP tradizionali.

Con il controllo di ammissione di chiamata (CAC), gli amministratori possono impostare limiti per la quantità di traffico vocale e video di Lync Server eseguito sui collegamenti di rete vincolati e specificare l'azione da eseguire se una nuova chiamata supera il limite. Le azioni possono includere il routing con un percorso alternativo o il rifiuto della chiamata.

Lync Server è compatibile con Survivable Branch Appliance di terze parti per fornire servizi di chiamata locali e la connessione alla rete PSTN nelle succursali, in caso di errore WAN nel sito centrale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

