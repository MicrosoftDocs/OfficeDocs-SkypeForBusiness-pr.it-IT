---
title: 'Lync Server 2013: uso dello strumento di personalizzazione di Office (ott)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd9c101b9098f9a5a6ac6088740c067039921b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a>Uso dello strumento di personalizzazione di Office (ott) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

Lo strumento di personalizzazione di Office (ott) fa parte del programma di installazione ed è lo strumento consigliato per molte personalizzazioni. Usando lo strumento di personalizzazione di Office, è possibile personalizzare l'ufficio e salvare le personalizzazioni in un file msp di personalizzazione della configurazione. Si inserisce il file nella cartella Updates nel punto di installazione della rete. Durante l'installazione di Office, la configurazione Cerca un file di personalizzazione della configurazione nella cartella Updates e applica le personalizzazioni. La cartella Updates può essere usata solo per distribuire gli aggiornamenti software durante un'installazione iniziale di Office 2013.

Lo strumento di personalizzazione di ottobre fa parte della configurazione ed è incluso nelle versioni con contratto multilicenza del prodotto. Per eseguire lo strumento di personalizzazione `setup.exe /admin` di Office, digitare alla riga di comando dalla radice del punto di installazione di rete che contiene i file di origine di 2013. Ad esempio, usare quanto segue:

`\\server\share\Office15\setup.exe /admin`

Gli amministratori usano lo strumento di personalizzazione di ottobre per creare un file msp di personalizzazione della configurazione. Come in Microsoft Office 2010 OCT, gli amministratori possono personalizzare le aree seguenti:

  - **Configurazione** Usato per specificare il percorso di installazione predefinito nel client e il nome dell'organizzazione predefinito, altre origini di installazione di rete, codice Product Key, contratto di licenza con l'utente finale, livello di visualizzazione, versioni precedenti di Office da rimuovere, programmi personalizzati da eseguire durante l'installazione, le impostazioni di sicurezza e le proprietà di configurazione.

  - **Caratteristiche** Consente di configurare le impostazioni utente e di personalizzare la modalità di installazione delle funzionalità di Office. Gli amministratori possono usare lo strumento di personalizzazione di Office per specificare i valori predefiniti iniziali delle impostazioni dell'applicazione per gli utenti. Gli utenti possono modificare la maggior parte delle impostazioni dopo l'installazione.

  - **Contenuto aggiuntivo** Consente di aggiungere o rimuovere file, aggiungere o rimuovere voci del registro di sistema e configurare i tasti di scelta rapida.

  - **Outlook** Usato per personalizzare il profilo di Outlook predefinito di un utente, specificare le impostazioni di Exchange, aggiungere account, rimuovere gli account ed esportare\\le impostazioni e specificare i gruppi di invio.

Per informazioni sullo strumento di personalizzazione di <http://go.microsoft.com/fwlink/p/?linkid=267516>ottobre, vedere.

</div>

<span> </span>

</div>

</div>

</div>

