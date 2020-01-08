---
title: 'Lync Server 2013: Tecnologie di virtualizzazione supportate e limitazioni note'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b5c99151be45f70d1d95fa0a89835ebb6f7d352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Tecnologie di virtualizzazione supportate e limitazioni note in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2017-02-06_

Il plug-in Lync VDI consente le chiamate audio e video per le tecnologie di virtualizzazione supportate. In questo modo si estende la funzionalità delineata per Microsoft Lync Server 2010 nella [virtualizzazione client in Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper. In conformità con le normative telefoniche standard, è incluso anche il supporto per E911. Le sezioni seguenti descrivono le tecnologie di virtualizzazione supportate dal plug-in di Lync VDI e dalle limitazioni note delle funzionalità.

<div>

## <a name="support-for-virtualization-technologies"></a>Supporto per le tecnologie di virtualizzazione

Il plug-in Lync VDI supporta i servizi remoti desktop completi nello scenario desktop virtuale personale, ma non nello scenario di sessione Desktop remoto. Questi scenari possono essere descritti come segue:

  - **Supportati: desktop virtuali personalizzati o VDI (Virtual Desktop Infrastructure).**    In questo scenario ogni utente accede a un desktop virtuale personalizzabile ed è in grado di salvare i file sul desktop che persistono in più sessioni. I Servizi Desktop remoto Microsoft, VMware Horizon View e Citrix XenDesktop sono implementazioni testate per l'uso con Lync. Per informazioni sugli ambienti VDI specifici del fornitore e sull'hardware client testati da Microsoft, vedere [infrastruttura qualificata per Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).

  - **Non supportata: sessioni desktop remoto.**    In questo scenario ogni utente accede a una sessione desktop virtuale generica che non può essere personalizzata. Le implementazioni di esempio includono sessione desktop remoto Microsoft e Citrix XenApp combinato con Citrix Receiver.

Il plug-in di Lync VDI non supporta altre tecnologie di virtualizzazione, come la virtualizzazione delle applicazioni, che consente l'uso di un'applicazione senza richiedere l'installazione dell'applicazione completa localmente. Le implementazioni di esempio includono Citrix XenApp e Microsoft Application Virtualization (App-V). Lo streaming di applicazioni, la comunicazione remota applicazioni e le modalità miste di virtualizzazione (ad esempio, la comunicazione remota applicazioni in una comunicazione remota desktop completa) non sono supportati.

Per consentire l'estensibilità, il plug-in di Lync VDI è stato progettato per usare API indipendenti dalla piattaforma, denominate Dynamic Virtual Channels (DVCs). Per gli scenari non esplicitamente supportati da Lync, fare riferimento alle istruzioni del supporto del provider di soluzioni VDI.

</div>

<div>

## <a name="known-feature-limitations"></a>Limitazioni note delle funzionalità

Di seguito sono riportate le limitazioni note quando si usa Lync 2013 in un ambiente VDI:

  - È disponibile un supporto limitato per le funzionalità di delega delle chiamate e dell'agente di Response Group anonimato dell'.

  - Non è previsto supporto per le seguenti caratteristiche:
    
      - Pagine di regolazione dispositivi audio e video integrati.
    
      - Video con visualizzazioni multiple.
    
      - Registrazione delle conversazioni.
    
      - Servizi Desktop remoto (RDS).
    
      - Partecipare a riunioni in forma anonima, ovvero partecipare a riunioni Lync ospitate da un'organizzazione che non è stata associata alla propria organizzazione.
    
      - Usare il plug-in di Lync VDI insieme a un dispositivo Lync Phone Edition.
    
      - Continuità di chiamata in caso di problemi di rete.
    
      - Suonerie personalizzate e musica di attesa.

  - Il plug-in Lync VDI non è supportato in un ambiente di Office 365.

</div>

</div>

<span> </span>

</div>

</div>

</div>

