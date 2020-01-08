---
title: "Lync Server 2013: abilitare o disabilitare l'integrazione con l'archiviazione di Exchange"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d2ded7e4cf586faf1f15ea6205aa23802413dc9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a>Abilitazione o disabilitazione dell'integrazione di Lync Server 2013 con lo spazio di archiviazione di Exchange

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-09_

Nel pannello di controllo di Lync Server 2013 si usano le configurazioni di archiviazione per abilitare e disabilitare l'integrazione con lo spazio di archiviazione di Exchange. Sono incluse le configurazioni di archiviazione seguenti:

  - Configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.

  - Configurazioni facoltative a livello di sito e a livello di pool che è possibile creare e usare per specificare la modalità di implementazione dell'archiviazione per siti o pool specifici.

Per informazioni dettagliate sull'implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere funzionamento dell' [archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla documentazione di distribuzione o alla documentazione operativa.

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a>Per abilitare o disabilitare l'integrazione con lo spazio di archiviazione di Microsoft Exchange

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.

4.  Fare clic sul nome della configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su **modifica**, fare clic su **Mostra dettagli**e quindi eseguire le operazioni seguenti:
    
      - Per abilitare l'integrazione con lo spazio di archiviazione di Exchange 2013, selezionare la casella di controllo **integrazione di Microsoft Exchange** .
    
      - Per disabilitare l'integrazione con lo spazio di archiviazione di Exchange 2013, deselezionare la casella di controllo **integrazione di Microsoft Exchange** .

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

