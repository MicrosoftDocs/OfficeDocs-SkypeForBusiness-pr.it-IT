---
title: "Lync Server 2013: configurazione dell'integrità in Lync Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14a4da3ec3f06dfb573ef7e9422bdd6b751db636
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a>Configurazione dell'integrità in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Tra i vari siti Web, gli articoli della Microsoft Knowledge base e gli strumenti di Lync Server Resource Kit, gli amministratori che incontrano problemi durante l'uso di Lync Server non sono mai lontani da un modo per risolvere questi problemi.

Ovviamente non è possibile garantire che non si verifichino problemi con Lync Server 2013 perché Lync Server può essere influenzato da molti aspetti, ad esempio gli arresti anomali della rete e gli errori hardware, che il prodotto stesso non può controllare. Implementando il monitoraggio dell'integrità, gli amministratori possono identificare potenziali problemi prima che vengano trasformati in problemi reali. Ad esempio, gli amministratori possono usare il monitoraggio di Lync Server per identificare tendenze e tendenze. Ad esempio, un aumento costante del numero di conferenze audio/video potrebbe suggerire la necessità di aggiungere capacità prima che il sistema diventi sovraccaricato.

In modo analogo, gli amministratori possono usare System Center Operations Manager per eseguire operazioni come l'emissione di avvisi in tempo reale quando si verificano eventi specificati e per l'esecuzione di transazioni sintetiche che verificano in modo proattivo il sistema. Le transazioni sintetiche vengono usate in Lync Server per verificare che gli utenti siano in grado di completare correttamente le attività comuni, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o l'esecuzione di chiamate a un telefono che si trova nella rete PSTN (Public Switched Telephone Network). Ad esempio, l'uso periodico di questi test può avvisare i potenziali problemi con gli utenti che accedono a Lync Server e consente di risolvere il problema prima che il team di supporto venga allagato con chiamate provenienti da utenti non in grado di creare una connessione. Usando System Center Operations Manager per eseguire queste transazioni sintetiche, gli amministratori possono monitorare abitualmente la distribuzione di Lync Server continuamente per 24 ore ogni giorno, senza dover rispondere a qualsiasi avviso che potrebbe essere emesse.

<div>


> [!NOTE]  
> Per Lync Server 2013, il Management Pack di System Center Operations Manager è anche in grado di rilevare i problemi "esterni" che possono influire negativamente su Lync Server. Ad esempio, gli amministratori possono ricevere una notifica se Internet Information Services (IIS) non è in linea, le risorse di sistema in un computer Lync Server scendono al di sotto di un importo specificato o un computer Lync Server sperimenta un errore hardware.



</div>

La configurazione dell'integrità in Lync Server 2013 è basata su System Center Operations Manager e sull'uso di Lync Server Management Pack. Questi Management Pack includono una serie di nuove funzionalità e miglioramenti, tra cui:

  - **Disponibilità dello scenario da qualsiasi posizione.** Il Management Pack di Lync Server 2010 ha introdotto il concetto di monitoraggio della disponibilità degli scenari per gli utenti finali con le transazioni sintetiche. In Lync Server 2013 questi agenti hanno più transazioni sintetiche e possono essere eseguiti da un'ampia gamma di posizioni all'interno dell'organizzazione, da postazioni geografiche remote all'esterno dell'organizzazione, dagli strumenti di filiale e da Lync Server 2010 distribuzioni per aggiungere una copertura alle distribuzioni di Edge legacy.

  - **Registri delle transazioni sintetici.** Quando una transazione sintetica non riesce, gli amministratori hanno accesso ai log HTML per determinare il risultato non riuscito. Ciò include la comprensione dell'azione non riuscita, la latenza di ogni azione, la riga di comando usata per eseguire il test e l'errore che si è verificato.

  - **Maggiore copertura dell'affidabilità delle chiamate.** Il Management Pack di Lync Server 2010 ha introdotto l'avviso di affidabilità delle chiamate per rilevare gravi problemi di connettività che influiscono sulle chiamate audio degli utenti finali. I Management Pack di Lync Server 2013 aggiungono una copertura per la messaggistica istantanea peer-to-peer e altre funzionalità di conferenza di base per massimizzare la copertura riducendo il rumore.

  - **Monitoraggio delle dipendenze.** Gli scenari di Lync Server possono avere esito negativo a causa di diversi fattori esterni, ad esempio IIS offline, limitate risorse di CPU e memoria e problemi relativi al disco. I nuovi Management Pack controllano diverse dipendenze critiche per assicurarsi che gli amministratori siano a conoscenza del loro impatto.

  - **Report avanzato.** Un set di report per aiutare gli amministratori a valutare la disponibilità dello scenario, pianificare la capacità e vedere quali componenti stanno vivendo la maggior parte dei problemi.

I Management Pack includono anche varie funzionalità che consentono di rilevare e diagnosticare una visibilità in tempo reale nell'integrità della distribuzione di Lync Server. Queste caratteristiche sono elencate nella tabella seguente.

### <a name="management-pack-features"></a>Caratteristiche del Management Pack

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Funzionalità</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Transazioni sintetiche</p></td>
<td><p>Cmdlet di Windows PowerShell che possono essere eseguiti da varie posizioni per garantire che gli scenari degli utenti finali, ad esempio accesso, presenza, messaggistica istantanea e conferenza siano prontamente disponibili per gli utenti finali.</p></td>
</tr>
<tr class="even">
<td><p>Avvisi di affidabilità delle chiamate</p></td>
<td><p>Query di database per i record dei dettagli delle chiamate (CDR). Questi record vengono scritti dai server front-end per indicare se gli utenti finali sono stati in grado di connettersi a una chiamata o perché una chiamata è stata terminata. Queste query generano avvisi che indicano quando una vasta gamma di utenti finali sta vivendo problemi di connettività per le chiamate peer-to-peer o per le funzionalità di conferenza di base.</p></td>
</tr>
<tr class="odd">
<td><p>Avvisi di qualità multimediale</p></td>
<td><p>Query di database che esaminano i report di qualità dell'esperienza (QoE) pubblicati dai client alla fine di ogni chiamata. Queste query generano avvisi che individuano scenari in cui gli utenti possono provare una qualità media scadente durante le chiamate e le conferenze. I dati sono basati su metriche chiave, ad esempio la latenza e la perdita di pacchetti, le metriche note per contribuire direttamente alla qualità delle chiamate.</p></td>
</tr>
<tr class="even">
<td><p>Integrità dei componenti</p></td>
<td><p>I singoli componenti del server generano avvisi usando i registri eventi e i contatori delle prestazioni. Questi avvisi indicano le condizioni di errore che possono influire gravemente su uno o più scenari degli utenti finali. Questi avvisi possono anche indicare una varietà di altre condizioni di errore, inclusi i servizi non in uso, le alte frequenze di errore, la latenza elevata dei messaggi o i problemi di connettività.</p></td>
</tr>
<tr class="odd">
<td><p>Integrità delle dipendenze</p></td>
<td><p>È possibile che si verifichino errori per diversi motivi esterni. I Management Pack ora controllano e raccolgono dati per alcune delle dipendenze esterne critiche che potrebbero indicare problemi gravi, tra cui disponibilità di IIS, utilizzo della CPU e della memoria di server e processi e metriche del disco.</p></td>
</tr>
</tbody>
</table>


Gli avvisi emessi dal sistema sono stati classificati in tre categorie generali:

  - **Avvisi ad alta priorità.** Questi avvisi indicano le condizioni che causano interruzioni dei servizi per gruppi di utenti di grandi dimensioni. Ad esempio, un errore del componente in un singolo computer non è un avviso ad alta priorità, perché Lync Server 2013 include caratteristiche di disponibilità elevata predefinite. Al contrario, gli avvisi ad alta priorità rappresentano problemi abbastanza seri "per riattivare gli amministratori durante la notte". Le interruzioni rilevate dalle transazioni sintetiche e dai servizi offline, ad esempio le conferenze audio/video, si qualificano come avvisi ad alta priorità.

  - **Avvisi con priorità media.**. Questi avvisi indicano le condizioni che influiscono su un sottoinsieme di utenti o indicano la degradazione della qualità delle chiamate. Che include problemi come gli errori dei componenti, la latenza nello stabilimento di chiamata o la qualità audio degradata nella chiamata. Gli avvisi in questa categoria sono con stato e indicano lo stato corrente del problema. Supponiamo ad esempio che i tempi di creazione delle chiamate superino la soglia di avviso. Se le chiamate allo stabilimento per il ritorno alla normalità, questi avvisi verranno risolti automaticamente in System Center Operations Manager. L'aspettativa per questi avvisi è che un amministratore li guarderà nello stesso giorno lavorativo.

  - **Altri avvisi.** Si tratta di avvisi provenienti da componenti che possono influire su un utente o un sottoinsieme specifico di utenti. Ad esempio, forse il servizio Rubrica non può analizzare l'immissione di Active Directory di un utente specifico. L'aspettativa per questi avvisi consiste nel fatto che gli amministratori possano accedervi quando hanno tempo disponibile.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Configurazione di Lync Server 2013 per l'utilizzo con System Center Operations Manager](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Uso della registrazione avanzata per le transazioni sintetiche in Lync Server 2013](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Uso di Microsoft SQL Server 2008 R2 come database di Operations Manager di System Center per Lync Server 2013](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

