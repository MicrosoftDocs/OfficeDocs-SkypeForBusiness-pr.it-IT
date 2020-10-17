---
title: 'Lync Server 2013: tecnologie di virtualizzazione supportate e limitazioni note'
description: 'Lync Server 2013: tecnologie di virtualizzazione supportate e limitazioni note.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 745fa535462d29342f4c0a58674ee6487db42a6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544612"
---
# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Tecnologie di virtualizzazione supportate e limitazioni note in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2017-02-06_

Il plug-in VDI di Lync consente la chiamata audio e video per le tecnologie di virtualizzazione supportate. In questo articolo viene estesa la funzionalità delineata per Microsoft Lync Server 2010 nella [virtualizzazione client in Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper. In conformità con le normative telefoniche standard, è incluso anche il supporto per E911. Nelle sezioni seguenti vengono descritte le tecnologie di virtualizzazione supportate dal plug-in VDI di Lync e le limitazioni note delle funzionalità.

<div>

## <a name="support-for-virtualization-technologies"></a>Supporto per le tecnologie di virtualizzazione

Il plug-in VDI di Lync supporta le funzionalità remote desktop complete nello scenario di desktop virtuale personale, ma non nello scenario di sessione Desktop remoto. Questi scenari possono essere descritti nel modo seguente:

  - **Supportato: desktop virtuali personalizzati o VDI (Virtual Desktop Infrastructure).**     In questo scenario, ogni utente esegue l'accesso a un desktop virtuale personalizzabile ed è in grado di salvare i file sul desktop che persistono tra le sessioni. Servizi Desktop remoto Microsoft, VMware Horizon View e Citrix XenDesktop sono implementazioni che sono state testate per l'utilizzo con Lync. Per informazioni sugli ambienti VDI specifici del fornitore e sull'hardware client che sono stati testati da Microsoft, vedere [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).

  - **Non supportata: sessioni di desktop remoto.**     In questo scenario, ogni utente esegue l'accesso a una sessione desktop virtuale generica che non può essere personalizzata. Le implementazioni di esempio includono Microsoft Remote Desktop Sessions (RDSH) e Citrix XenApp in combinazione con Citrix Receiver.

Il plug-in VDI di Lync non supporta altre tecnologie di virtualizzazione, ad esempio la virtualizzazione dell'applicazione, che consente l'utilizzo di un'applicazione senza richiedere l'installazione dell'applicazione completa localmente. Le implementazioni di esempio includono Citrix XenApp e Microsoft Application Virtualization (App-V). Le modalità di flusso applicazioni, comunicazione remota applicazioni e virtualizzazione mista, ad esempio la comunicazione remota applicazioni in Desktop remoto completo, non sono supportate.

Per consentire l'estensibilità, il plug-in VDI di Lync è stato creato per l'utilizzo di API indipendenti dalla piattaforma denominate Dynamic Virtual Channels (dinamici). Per gli scenari non supportati in modo esplicito da Lync, fare riferimento alle istruzioni di supporto del provider di soluzioni VDI.

</div>

<div>

## <a name="known-feature-limitations"></a>Limitazioni note delle funzionalità

Quando si utilizza Lync 2013 in un ambiente VDI, sono note le limitazioni seguenti:

  - È disponibile un supporto limitato per le funzionalità di delega chiamata e agente di Response Group Anonymization.

  - Non è previsto supporto per le seguenti caratteristiche:
    
      - Pagine di regolazione dispositivi audio e video integrati.
    
      - Video con più visualizzazioni.
    
      - Registrazione delle conversazioni.
    
      - Servizi Desktop remoto (RDS).
    
      - Partecipare a riunioni in forma anonima, ovvero partecipare a riunioni di Lync ospitate da un'organizzazione non federata con la propria organizzazione.
    
      - Utilizzo del plug-in VDI di Lync insieme a un dispositivo Lync Phone Edition.
    
      - Continuità di chiamata in caso di problemi di rete.
    
      - Suonerie personalizzate e funzionalità di musica in attesa.

  - Il plug-in VDI di Lync non è supportato in un ambiente Microsoft 365 o Office 365.

</div>

</div>

<span> </span>

</div>

</div>

</div>

