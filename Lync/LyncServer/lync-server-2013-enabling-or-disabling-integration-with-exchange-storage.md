---
title: "Lync Server 2013: attivazione o disattivazione dell'integrazione con l'archiviazione di Exchange"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d11e8bff053e483080e4725f2357c3434d9f08f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a>Abilitazione o disabilitazione dell'integrazione di Lync Server 2013 con l'archiviazione di Exchange

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-09_

Nel pannello di controllo di Lync Server 2013, è possibile utilizzare le configurazioni di archiviazione per abilitare e disabilitare l'integrazione con l'archivio di Exchange. Sono incluse le configurazioni di archiviazione seguenti:

  - Una configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.

  - Configurazioni facoltative a livello di sito e di pool che possono essere create e utilizzate per specificare come deve essere implementata l'archiviazione per siti o pool specifici.

Per informazioni dettagliate sulla modalità di implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a>Per abilitare o disabilitare l'integrazione con l'archiviazione di Microsoft Exchange

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.

4.  Fare clic sul nome della configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su **Modifica**, su **Mostra dettagli** e quindi eseguire le operazioni seguenti:
    
      - Per abilitare l'integrazione con l'archiviazione di Exchange 2013, selezionare la casella di controllo **integrazione di Microsoft Exchange** .
    
      - Per disabilitare l'integrazione con l'archiviazione di Exchange 2013, deselezionare la casella di controllo **integrazione di Microsoft Exchange** .

5.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Funzionamento dell'archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

