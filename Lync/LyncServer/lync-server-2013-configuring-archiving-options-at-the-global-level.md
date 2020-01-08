---
title: 'Lync Server 2013: configurazione delle opzioni di archiviazione a livello globale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21653d38c7b56fa93395422a2e20906afd0cc3e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a>Configurazione delle opzioni di archiviazione a livello globale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-10_

Quando si aggiunge l'archiviazione alla topologia e si pubblica la topologia, Lync Server crea una configurazione globale per l'archiviazione. Per impostazione predefinita, le opzioni di archiviazione non sono abilitate nella configurazione globale. La configurazione globale Controlla quali opzioni sono abilitate per l'intera distribuzione, a meno che non vengano configurate configurazioni del sito o del pool, che eseguono l'override della configurazione globale.

Per informazioni dettagliate sul funzionamento delle configurazioni di archiviazione, ad esempio la gerarchia per le configurazioni globali, del sito e del pool, vedere funzionamento dell' [archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, nella documentazione di distribuzione o nelle operazioni.

<div>


> [!NOTE]  
> Devi specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a>Per configurare le opzioni di archiviazione a livello globale

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server 2013. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server 2013, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.

4.  Nella pagina **Configurazione archiviazione** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **Modifica impostazioni di archiviazione-globale**, nell'elenco a discesa **Impostazioni archiviazione** Selezionare una delle opzioni di archiviazione seguenti:
    
      - **Disabilita archiviazione**
    
      - **Archivia sessioni di messaggistica istantanea**
    
      - **Archivia sessioni di messaggistica istantanea e Web Conferencing**

6.  Anche nell' **impostazione modifica archiviazione-pagina globale** eseguire le operazioni seguenti:
    
      - Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca messaggistica istantanea o servizi di conferenza Web se l'archiviazione non riesce** .
    
      - Per usare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .
    
      - Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita l'eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:
        
          - Per specificare l'eliminazione dopo un determinato numero di giorni, fare clic su **Elimina dati di archiviazione esportati e archivia dati archiviati dopo la durata massima (giorni)** e quindi specificare il numero di giorni.
        
          - Per limitare l'eliminazione all'archiviazione dei dati esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.

7.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

