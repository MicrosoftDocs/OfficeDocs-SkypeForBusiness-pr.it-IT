---
title: 'Lync Server 2013: configurazione delle opzioni di archiviazione per un sito'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14b0e29a2796c23c13a16bfb3e8a202a0a535aaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a>Configurazione delle opzioni di archiviazione per un sito in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-09_

È possibile specificare le opzioni di archiviazione da applicare a siti specifici creando e configurando le opzioni in una configurazione di archiviazione per ognuno di questi siti. Una configurazione del sito sostituisce la configurazione globale, ma solo per il sito specificato nella configurazione del sito. Le configurazioni del pool eseguono l'override delle configurazioni sito

Per informazioni dettagliate sul funzionamento delle configurazioni di archiviazione, ad esempio la gerarchia per le configurazioni globali, del sito e del pool, vedere funzionamento dell' [archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, nella documentazione di distribuzione o nelle operazioni.

<div>


> [!NOTE]  
> Devi specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione.



</div>

<div>


> [!IMPORTANT]  
> Per abilitare l'archiviazione, è necessario specificare i criteri di archiviazione per controllare l'archiviazione delle comunicazioni interne ed esterne a livello globale e, se necessario, ai livelli di sito e utente. Se si configurano i criteri a livello di utente, è necessario assegnare i criteri utente anche a utenti specifici. Per informazioni dettagliate sulla creazione e la configurazione dei criteri di archiviazione, vedere <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013</A> nella documentazione delle operazioni.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a>Per configurare le opzioni di archiviazione a livello di sito

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server 2013. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server 2013, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.

4.  Nella pagina **Configurazione archiviazione** fare clic su **nuovo**e quindi su **configurazione sito**.

5.  In **Seleziona un sito**selezionare il sito da configurare per l'archiviazione.

6.  In **nuova impostazione archiviazione**, nella casella di riepilogo a discesa **Impostazioni archiviazione** eseguire una delle operazioni seguenti:
    
      - Per abilitare l'archiviazione solo per le sessioni di messaggistica istantanea (IM), fare clic su **Archivia sessioni**istantanee.
    
      - Per abilitare l'archiviazione sia per le sessioni di messaggistica istantanea che per le conferenze, fare clic su **Archivia messaggistica istantanea e sessioni di conferenza Web**.
    
      - Per disabilitare l'archiviazione per il criterio, fare clic su **Disattiva archiviazione**.

7.  Anche in **nuove impostazioni di archiviazione**eseguire le operazioni seguenti:
    
      - Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca messaggistica istantanea o servizi di conferenza Web se l'archiviazione non riesce** .
    
      - Per usare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .
    
      - Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita l'eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:
        
          - Per specificare l'eliminazione dopo un determinato numero di giorni, fare clic su **Elimina dati di archiviazione esportati e archivia dati archiviati dopo la durata massima (giorni)** e quindi specificare il numero di giorni.
        
          - Per limitare l'eliminazione all'archiviazione dei dati esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.

8.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

