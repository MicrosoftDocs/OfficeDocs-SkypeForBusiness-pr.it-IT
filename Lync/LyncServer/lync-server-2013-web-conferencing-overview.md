---
title: Panoramica di Lync Server 2013 Web Conferencing
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing overview
ms:assetid: 40616dc4-f705-4890-85bf-79f76a033a9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425913(v=OCS.15)
ms:contentKeyID: 48183949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de63cb5bf2578359d012cda72b07b8fc7f62880d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-web-conferencing-in-lync-server-2013"></a>Panoramica delle conferenze Web in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-30_

Con i servizi di conferenza Web, gli utenti possono condividere e collaborare ai documenti, ad esempio presentazioni di PowerPoint, durante le conferenze. Inoltre, gli utenti possono condividere tutti o parte dei loro desktop tra loro in tempo reale, in modo da sembrare come se le persone della conferenza fossero riunite attorno alla stessa tabella della riunione.

<div>

## <a name="whiteboard-and-annotations"></a>Lavagna e annotazioni

Una lavagna è un'area di disegno vuota che può essere usata per la collaborazione, con testo, input penna, disegni e immagini. Le annotazioni effettuate sulle lavagne possono essere visualizzate da tutti i partecipanti alla riunione. La funzionalità Lavagna migliora la collaborazione consentendo ai partecipanti alla riunione di discutere idee, brainstorming, appunti e così via.

</div>

<div>

## <a name="polling"></a>Polling

La funzionalità di polling migliora la collaborazione consentendo ai relatori di determinare rapidamente le preferenze dei partecipanti. Durante le riunioni e le conversazioni online, i relatori possono usare il polling per raccogliere risposte anonime dai partecipanti. Tutti i relatori possono visualizzare i risultati e possono nascondere i risultati o visualizzarli in tutti i partecipanti.

</div>

<div>

## <a name="application-sharing-and-desktop-sharing"></a>Condivisione di applicazioni e condivisione desktop

Durante una conferenza è possibile condividere l'intero desktop, una singola applicazione o singoli monitor in un ambiente con più monitor. Oltre a visualizzare solo il contenuto, gli altri partecipanti alla conferenza possono anche richiedere il controllo dello schermo e, con l'autorizzazione, interagire con il contenuto (incluso lo scorrimento e la modifica).

<div>


> [!NOTE]  
> I partecipanti che stanno visualizzando la conferenza possono anche prendere il sopravvento e iniziare a condividere il contenuto durante la riunione



</div>

</div>

<div>

## <a name="powerpoint-sharing"></a>Condivisione di PowerPoint

In Lync 2010 le presentazioni di PowerPoint sono state visualizzate in uno dei due modi. Per gli utenti che usano Lync 2010, le presentazioni di PowerPoint venivano visualizzate usando il formato di PowerPoint 97-2003 e venivano visualizzate usando una copia incorporata del Visualizzatore di PowerPoint. Per gli utenti che usano Lync Web App, le presentazioni di PowerPoint sono state convertite in file HTML dinamici e quindi visualizzate usando una combinazione di questi file DHTML personalizzati e Silverlight. Anche se in genere efficace, questo approccio ha alcune limitazioni:

  - Il Visualizzatore di PowerPoint incorporato (che ha fornito l'esperienza di visualizzazione ottimale) è disponibile solo nella piattaforma Windows.

  - Molti dispositivi mobili (inclusi alcuni dei telefoni cellulari più diffusi) non supportano Silverlight.

  - Il Visualizzatore di PowerPoint e l'approccio DHTML/Silverlight non supportano tutte le funzionalità, ad esempio le transizioni delle diapositive e il video incorporato, che si trovano nelle edizioni più recenti di PowerPoint.

Per risolvere questi problemi e per migliorare l'esperienza complessiva degli utenti che presentano o visualizzano presentazioni di PowerPoint, Lync Server 2013 impiega Office Web Apps e il server Office Web Apps per gestire le presentazioni di PowerPoint. Tra gli altri vantaggi, questo nuovo approccio consente di:

  - Display con risoluzione superiore e supporto migliore per le funzionalità di PowerPoint, ad esempio animazioni, transizioni diapositiva e video incorporato.

  - Altri dispositivi mobili per accedere a queste presentazioni. Questo perché Lync Server 2013 USA standard DHTML e JavaScript per trasmettere presentazioni di PowerPoint invece di DHTML e Silverlight personalizzati.

  - Gli utenti con i privilegi appropriati per scorrere una presentazione di PowerPoint indipendentemente dalla presentazione stessa. Ad esempio, mentre Ken relatore sta presentando la sua presentazione, Pilar Ackerman può esaminare le diapositive desiderate e senza influire sulle presentazioni di Ken.

</div>

</div>

<span> </span>

</div>

</div>

</div>

