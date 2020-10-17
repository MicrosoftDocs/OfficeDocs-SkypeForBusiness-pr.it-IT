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
ms.openlocfilehash: 6287b5edd711df845b862b49bc15adb8405e8587
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535363"
---
# <a name="overview-of-web-conferencing-in-lync-server-2013"></a>Panoramica delle conferenze Web in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-30_

Con le conferenze Web, gli utenti possono condividere documenti, quali presentazioni di PowerPoint, e collaborare a essi durante le conferenze. Possono inoltre condividere interamente o in parte il loro desktop con gli altri utenti in tempo reale, come se le persone che partecipano alla conferenza fossero sedute attorno allo stesso tavolo per la riunione.

<div>

## <a name="whiteboard-and-annotations"></a>Lavagna e annotazioni

La lavagna è una schermata vuota che può essere utilizzata per la collaborazione con l'aiuto di strumenti come testo, inchiostro, disegni e immagini. Le annotazioni effettuate sulle lavagne verranno visualizzate da tutti i partecipanti. Tale funzionalità facilita la collaborazione, consentendo ai partecipanti alle riunioni di discutere, mettere insieme idee, prendere appunti e così via.

</div>

<div>

## <a name="polling"></a>Polling

La funzionalità per sondaggi migliora la collaborazione consentendo ai relatori di determinare rapidamente le preferenze dei partecipanti. Durante le riunioni e le conversazioni online, i relatori possono utilizzare i sondaggi per raccogliere risposte anonime dai partecipanti. Tutti i relatori possono vedere i risultati e decidere se nasconderli o mostrarli a tutti i partecipanti.

</div>

<div>

## <a name="application-sharing-and-desktop-sharing"></a>Condivisione programmi e condivisione desktop

Durante una conferenza è possibile condividere l'intero desktop, un'applicazione individuale o singoli monitor in un ambiente con più monitor. Oltre a visualizzare il contenuto, gli altri partecipanti alla conferenza possono anche richiedere il controllo dello schermo e, con l'autorizzazione appropriata, possono interagire con il contenuto (anche con operazioni di scorrimento e modifica).

<div>


> [!NOTE]  
> I partecipanti che visualizzano la conferenza possono anche prendere il controllo e iniziare a condividere il contenuto durante la riunione



</div>

</div>

<div>

## <a name="powerpoint-sharing"></a>Condivisione con PowerPoint

In Lync 2010 le presentazioni di PowerPoint sono state visualizzate in uno dei due modi. Per gli utenti che eseguono Lync 2010, le presentazioni di PowerPoint sono state visualizzate utilizzando il formato PowerPoint 97-2003 e sono state visualizzate utilizzando una copia incorporata del Visualizzatore di PowerPoint. Per gli utenti che eseguono Lync Web App, le presentazioni di PowerPoint sono state convertite in file HTML dinamici e quindi visualizzate utilizzando una combinazione di questi file DHTML personalizzati e Silverlight. Anche se efficace in termini generali, questo approccio presentava alcune limitazioni:

  - Il Visualizzatore di PowerPoint incorporato (che ha fornito l'esperienza di visualizzazione ottimale) è disponibile solo nella piattaforma Windows.

  - Molti dispositivi mobili (compresi alcuni dei telefoni cellulari più diffusi) non supportano Silverlight.

  - Il Visualizzatore di PowerPoint e l'approccio DHTML/Silverlight non supportano tutte le funzionalità (tali transizioni di diapositive e video incorporati) presenti nelle edizioni più recenti di PowerPoint.

Per risolvere questi problemi e per migliorare l'esperienza complessiva degli utenti che presentano o visualizzano presentazioni di PowerPoint, Lync Server 2013 utilizza Office Web Apps e il server Office Web Apps per gestire le presentazioni di PowerPoint. Tra gli altri vantaggi, questo nuovo approccio offre:

  - Visualizzazioni di risoluzione superiore e supporto migliorato di funzionalità di PowerPoint, come le animazioni, le transizioni diapositive e i video incorporati.

  - Dispositivi mobili aggiuntivi per accedere a tali presentazioni. Ciò è dovuto al fatto che Lync Server 2013 utilizza standard DHTML e JavaScript per trasmettere le presentazioni di PowerPoint anziché DHTML e Silverlight personalizzati.

  - Utenti dotati dei privilegi appropriati per lo scorrimento di una presentazione di PowerPoint indipendentemente dalla presentazione stessa. Ad esempio, mentre Ken Myer introduce la sua presentazione, Pilar Ackerman può esaminare tutte le diapositive che vuole, senza interferire con la presentazione di Ken.

</div>

</div>

<span> </span>

</div>

</div>

</div>

