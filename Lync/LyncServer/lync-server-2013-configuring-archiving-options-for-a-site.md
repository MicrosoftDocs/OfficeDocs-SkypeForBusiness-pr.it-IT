---
title: 'Lync Server 2013: configurazione delle opzioni di archiviazione per un sito'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9b679eabfc0538de5daf59ee1eb7742ade94228
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a>Configurazione delle opzioni di archiviazione per un sito in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-09_

È possibile specificare le opzioni di archiviazione da applicare a siti specifici tramite la creazione e configurazione delle opzioni in una configurazione di archiviazione per ognuno dei siti. Una configurazione di sito ha la priorità rispetto alla configurazione globale, ma solo per il sito specificato. Le configurazioni di pool sono prioritarie rispetto alle configurazioni di sito.

Per informazioni dettagliate sul funzionamento delle configurazioni di archiviazione, inclusa la gerarchia per le configurazioni globali, del sito e del pool, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.

<div>


> [!NOTE]  
> Specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione.



</div>

<div>


> [!IMPORTANT]  
> Per abilitare l'archiviazione, è necessario specificare i relativi criteri allo scopo di controllare l'archiviazione delle comunicazioni interne ed esterne a livello globale e, se appropriato, a livello di sito e utente. Se si configurano i criteri a livello utente, è necessario assegnare i criteri utente a utenti specifici. Per informazioni dettagliate sulla creazione e sulla configurazione dei criteri di archiviazione, vedere <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of Internal and External Communications in Lync Server 2013</A> nella documentazione relativa alle operazioni.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a>Per configurare le opzioni di archiviazione a livello del sito

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Lync Server 2013. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server 2013, vedere [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.

4.  Nella pagina **Configurazione archiviazione** fare clic su **Nuovo** e quindi su **Configurazione sito**.

5.  In **Seleziona un sito** selezionare il sito da configurare per l'archiviazione.

6.  In **Nuova impostazione di archiviazione** eseguire una delle operazioni seguenti nella casella di riepilogo a discesa **Impostazione di archiviazione**:
    
      - Per abilitare l'archiviazione solo per le sessioni di messaggistica istantanea, fare clic su **Archivia sessioni di messaggistica istantanea**.
    
      - Per abilitare l'archiviazione per le conferenze e le sessioni di messaggistica istantanea, fare clic su **Archivia sessioni di messaggistica istantanea e Web Conferencing**.
    
      - Per disabilitare l'archiviazione dei criteri, fare clic su **Disabilita archiviazione**.

7.  Sempre in **Nuova impostazione di archiviazione** eseguire le operazioni seguenti:
    
      - Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione non riesce**.
    
      - Per utilizzare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .
    
      - Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:
        
          - Per specificare l'eliminazione dopo un numero specifico di giorni, fare clic su **Elimina dati di archiviazione esportati e archiviati dopo durata massima (giorni)** e quindi specificare il numero di giorni.
        
          - Per limitare l'eliminazione ai dati di archiviazione esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.

8.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

