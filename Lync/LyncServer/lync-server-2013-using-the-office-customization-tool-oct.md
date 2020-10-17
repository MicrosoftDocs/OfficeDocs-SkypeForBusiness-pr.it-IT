---
title: 'Lync Server 2013: utilizzo dello strumento di personalizzazione di Office'
description: 'Lync Server 2013: utilizzo dello strumento di personalizzazione di Office.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 602502ba4579ed6c640eee909d4c6b056ce247d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547332"
---
# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a>Utilizzo dello strumento di personalizzazione di Office in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

Lo Strumento di personalizzazione di Office fa parte del programma di installazione ed è lo strumento consigliato per molte personalizzazioni. Tramite questo strumento, è possibile personalizzare Office e salvare le personalizzazioni in un file di configurazione dell'installazione con estensione msp. Il file viene inserito nella cartella Aggiornamenti nella posizione di installazione dalla rete. Quando si installa Office, il programma di installazione cerca un file di configurazione dell'installazione nella cartella Aggiornamenti e applica le personalizzazioni. La cartella Updates può essere utilizzata solo per distribuire gli aggiornamenti software durante un'installazione iniziale di Office 2013.

Lo Strumento di personalizzazione di Office fa parte dell'installazione ed è incluso nelle versioni multilicenza del prodotto. È possibile eseguire lo strumento di personalizzazione di Office digitando `setup.exe /admin` dalla riga di comando dalla radice del punto di installazione di rete che contiene i file di origine di 2013. Ad esempio, utilizzare quanto segue:

`\\server\share\Office15\setup.exe /admin`

Gli amministratori utilizzano questo strumento per creare un file di configurazione dell'installazione con estensione msp. Come in Microsoft Office 2010 OCT, gli amministratori possono personalizzare le aree seguenti:

  - **Programma di installazione** Utilizzato per specificare il percorso di installazione predefinito sul client e il nome dell'organizzazione predefinito, origini di installazione di rete aggiuntive, codice Product Key, contratto di licenza con l'utente finale, livello di visualizzazione, versioni precedenti di Office da rimuovere, programmi personalizzati da eseguire durante l'installazione, impostazioni di sicurezza e proprietà del programma di installazione.

  - **Caratteristiche** Utilizzato per configurare le impostazioni utente e per personalizzare la modalità di installazione delle caratteristiche di Office. Gli amministratori possono utilizzare lo Strumento di personalizzazione di Office per specificare valori predefiniti iniziali delle impostazioni delle applicazioni Office per gli utenti. Gli utenti possono modificare la maggior parte delle impostazioni dopo l'installazione.

  - **Contenuto aggiuntivo** Utilizzato per aggiungere o rimuovere file, aggiungere o rimuovere voci del registro di sistema e configurare i collegamenti.

  - **Outlook** Utilizzato per personalizzare il profilo Outlook predefinito di un utente, specificare le impostazioni di Exchange, aggiungere account, rimuovere account ed esportare le impostazioni e specificare i gruppi di invio/ \\ ricezione.

Per informazioni sullo strumento di personalizzazione di Office, vedere <https://go.microsoft.com/fwlink/p/?linkid=267516> .

</div>

<span> </span>

</div>

</div>

</div>

