---
title: 'Lync Server 2013: rapporto riepilogativo conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4390c2f3aa18820668415543496dfdcfd5aa79e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502353"
---
# <a name="conference-summary-report-in-lync-server-2013"></a>Report riepilogativo conferenze in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-09-03_

Il Rapporto riepilogativo conferenze offre una visuale generale delle sessioni di conferenza online. Una conferenza in genere coinvolge più di 2 utenti e richiede l'utilizzo di Microsoft Lync Server 2013 Servizi di conferenza. Una sessione peer-to-peer, invece, coinvolge in genere solo 2 utenti e non richiede l'utilizzo dei servizi di conferenza di Lync Server. Le attività peer-to-peer sono segnalate nel [rapporto riepilogativo attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).

Il rapporto riepilogativo conferenze non solo indica quante conferenze sono state tenute durante un determinato periodo di tempo (ogni ora, giornaliero, settimanale, mensile) ma indica anche il numero totale di persone che hanno partecipato a tali conferenze e il numero totale di organizzatori di conferenze univoci.

Con organizzatore "univoco” si intende qualsiasi utente che pianifica almeno una conferenza. Se Luisa Cazzaniga pianifica una conferenza, ad esempio, sarà conteggiata come organizzatore univoco. Se Davide Garghentini pianifica 148 conferenze, anche lui sarà conteggiato come singolo organizzatore univoco. La tabella seguente, ad esempio, indica 8 conferenze pianificate ma solo tre organizzatori univoci, ovvero Davide Garghentini, Luisa Cazzaniga e Luca Argentiero.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Organizzatore conferenza</th>
<th>Data conferenza</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Davide Garghentini</p></td>
<td><p>07/07/2012 10.00</p></td>
</tr>
<tr class="even">
<td><p>Luca Argentiero</p></td>
<td><p>07/07/2012 10.00</p></td>
</tr>
<tr class="odd">
<td><p>Davide Garghentini</p></td>
<td><p>07/07/2012 11.00</p></td>
</tr>
<tr class="even">
<td><p>Daniela Cazzaniga</p></td>
<td><p>07/07/2012 11.00</p></td>
</tr>
<tr class="odd">
<td><p>Davide Garghentini</p></td>
<td><p>07/07/2012 13.00</p></td>
</tr>
<tr class="even">
<td><p>Daniela Cazzaniga</p></td>
<td><p>07/07/2012 14.00</p></td>
</tr>
<tr class="odd">
<td><p>Davide Garghentini</p></td>
<td><p>02/07/2012 10.00</p></td>
</tr>
<tr class="even">
<td><p>Daniela Cazzaniga</p></td>
<td><p>02/07/2012 10.00</p></td>
</tr>
</tbody>
</table>


Il Rapporto riepilogativo conferenze indica inoltre il numero di conferenze con audio e video.

<div>

## <a name="accessing-the-conference-summary-report"></a>Accesso al rapporto riepilogativo conferenze

È possibile accedere al rapporto riepilogativo conferenze dalla home page Relazioni monitoraggio. È possibile eseguire il drill-down al Rapporto attività conferenza facendo clic su una delle metriche seguenti:

  - Totale conferenze

  - Totale partecipanti

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a>Utilizzo ottimale del rapporto riepilogativo conferenze

I valori totali per la maggior parte delle metriche utilizzate nel Rapporto riepilogativo conferenze sono disponibili nella parte inferiore del rapporto. Scorrere verso il basso per visualizzare valori come il numero totale di conferenze tenutesi durante il periodo di tempo specificato e il numero totale di persone che hanno partecipato a tali conferenze. Una metrica per la quale non è disponibile il totale nella parte inferiore del rapporto è Totale organizzatori conferenza univoci. Uno dei motivi è questo: si supponga di voler esaminare i dati mensili. Nel giorno 1 sono stati rilevati 34 organizzatori di conferenza univoci, nel giorno 2 gli organizzatori univoci sono 27. Ciò non significa tuttavia che per i due giorni il totale degli organizzatori univoci sia 61. Tutte le 27 persone che hanno organizzato conferenze nel giorno 2 potrebbero essere infatti incluse nei 34 organizzatori univoci del giorno 1. In questo semplice rapporto, ad esempio, notare che Davide Garghentini e Daniela Cazzaniga hanno pianificato conferenze sia in data 07/07/2012 che in data 02/07/2012:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Organizzatore conferenza</th>
<th>Data conferenza</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Davide Garghentini</p></td>
<td><p>07/07/2012 10.00</p></td>
</tr>
<tr class="even">
<td><p>Luca Argentiero</p></td>
<td><p>07/07/2012 10.00</p></td>
</tr>
<tr class="odd">
<td><p>Davide Garghentini</p></td>
<td><p>07/07/2012 11.00</p></td>
</tr>
<tr class="even">
<td><p>Daniela Cazzaniga</p></td>
<td><p>07/07/2012 11.00</p></td>
</tr>
<tr class="odd">
<td><p>Davide Garghentini</p></td>
<td><p>07/07/2012 13.00</p></td>
</tr>
<tr class="even">
<td><p>Daniela Cazzaniga</p></td>
<td><p>07/07/2012 14.00</p></td>
</tr>
<tr class="odd">
<td><p>Davide Garghentini</p></td>
<td><p>02/07/2012 10.00</p></td>
</tr>
<tr class="even">
<td><p>Daniela Cazzaniga</p></td>
<td><p>02/07/2012 10.00</p></td>
</tr>
</tbody>
</table>


Per ottenere un'indicazione più precisa del numero totale di utenti univoci che hanno organizzato conferenze, modificare l'intervallo di tempo, ad esempio esaminare i dati su base mensile anziché giornaliera.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il rapporto riepilogativo conferenze consente di scegliere la modalità di raggruppamento dei dati. In questo caso le conferenze sono raggruppabili per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri applicabili al rapporto riepilogativo conferenze.

### <a name="conference-summary-report-filters"></a>Filtri del rapporto riepilogativo conferenze

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</p>
<p>07/07/2012 13.00</p>
<p>Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane vanno sempre dal lunedì alla domenica.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</p>
<p>07/07/2012 13.00</p>
<p>Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane vanno sempre dal lunedì alla domenica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervallo</strong></p></td>
<td><p>Selezionare uno dei seguenti:</p>
<ul>
<li><p>Orario (è possibile visualizzare un massimo di 25 ore)</p></li>
<li><p>Giornaliero (è possibile visualizzare un massimo di 31 giorni)</p></li>
<li><p>Settimanale (è possibile visualizzare un massimo di 12 settimane)</p></li>
<li><p>Mensile (è possibile visualizzare un massimo di 12 mesi)</p></li>
</ul>
<p>Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo giornaliero con data di inizio 07/07/2012 e data di fine 28/02/2012, verranno visualizzati i dati per i giorni da 07/08/2012 ore 12.00 a 07/09/2012 ore 12.00 (per un totale di 31 giorni).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

La tabella seguente elenca le informazioni disponibili nel rapporto riepilogativo conferenze.

### <a name="conference-summary-report-metrics"></a>Metriche del rapporto riepilogativo conferenze

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Elemento utilizzabile per eseguire l'ordinamento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Orario</strong></p>
<p><strong>Giornaliero</strong></p>
<p><strong>Settimanale</strong></p>
<p><strong>Mensile</strong></p></td>
<td><p>No</p></td>
<td><p>Indica l'intervallo di tempo selezionato sulla barra degli strumenti dei filtri. Ove applicabile, è possibile fare clic su un determinato intervallo di tempo per visualizzare informazioni dettagliate relative a tale intervallo. Se ad esempio si sta utilizzando l'intervallo giornaliero e si fa clic su 07/07/2012, verranno visualizzate le attività di registrazione degli utenti per tale data, suddivise per ore.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale conferenze</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze eseguite, indipendentemente dal tipo di conferenza. Facendo clic su questo elemento viene visualizzato il rapporto attività conferenza per il periodo di tempo selezionato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale partecipanti</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di persone che hanno partecipato alle conferenze. Facendo clic su questo elemento viene visualizzato il rapporto attività conferenza per il periodo di tempo selezionato.</p></td>
</tr>
<tr class="even">
<td><p><strong>Numero medio di partecipanti per conferenza</strong></p></td>
<td><p>No</p></td>
<td><p>Numero medio di persone che hanno preso parte a una specifica conferenza, determinato dividendo il numero totale di conferenze per il numero totale di partecipanti.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale conferenze audio/video</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze con audio o video.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale minuti di conferenza audio/video</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di minuti dedicati alle conferenze audio/video.</p>
<p>La metrica Total A/V Conference minutes riepiloga tutti i tipi di conferenze audio/video, tra cui: conferenze A/V. Conferenze di messaggistica istantanea; Conferenze di condivisione app; Conferenze dati; e conferenze PSTN.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale minuti partecipante di conferenza audio/video</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di minuti partecipante dedicati alle conferenze audio/video. Si supponga, ad esempio, che un utente dedichi 5 minuti a una conferenza audio/video e che un secondo utente ne dedichi 3 nella stessa conferenza. Si ottiene così un totale di 8 minuti partecipante (5+3).</p></td>
</tr>
<tr class="even">
<td><p><strong>Media minuti di conferenza audio/video	</strong></p></td>
<td><p>No</p></td>
<td><p>Numero medio di minuti per conferenza audio/video.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale organizzatori conferenza univoci</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di utenti che hanno organizzato almeno una conferenza. Gli utenti che hanno organizzato più conferenze vengono considerati come un organizzatore unico, come gli utenti che hanno organizzato una sola conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale messaggi conferenza</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di messaggi istantanei inviati durante le conferenze.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

