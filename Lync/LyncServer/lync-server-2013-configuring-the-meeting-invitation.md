---
title: "Lync Server 2013: configurazione dell'invito alla riunione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14e0614ecdaa73a886429e89618cac568d620938
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a>Configurazione dell'invito alla riunione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-16_

È possibile personalizzare gli inviti alle riunioni inviati dal componente aggiuntivo riunione online per Lync 2013 includendo gli elementi facoltativi seguenti nel corpo dell'invito alla riunione:

  - **Logo dell'organizzazione** Aggiungere il logo dell'organizzazione agli inviti alla riunione usando l'opzione URL logo. Se gli inviti alle riunioni verranno inviati a persone esterne all'organizzazione, l'immagine deve trovarsi in un URL disponibile pubblicamente. I formati di immagine supportati sono GIF e JPG. Sebbene Lync Server 2013 memorizzi l'URL senza restrizioni di dimensione per l'immagine, per ottenere risultati ottimali, le dimensioni massime dell'immagine devono essere alte 30 pixel per 188 pixel di larghezza.

  - **Collegamento Guida o supporto personalizzato** Aggiungere un URL per la guida o il sito Web del team di supporto dell'organizzazione. Se gli inviti alle riunioni verranno inviati a persone esterne all'organizzazione, l'URL dovrebbe essere disponibile pubblicamente. La lunghezza massima dell'URL è di 1 KB.

  - **Testo della dichiarazione di non responsabilità legale** Aggiungere un URL per il testo legale o una dichiarazione di non responsabilità che verrà visualizzata in tutti gli inviti alle riunioni. Se gli inviti alle riunioni verranno inviati a persone esterne all'organizzazione, l'URL dovrebbe essere disponibile pubblicamente. La lunghezza massima dell'URL è di 1 KB.

  - **Testo del piè** di pagina personalizzato Aggiungere il testo di cui verrà eseguito il rendering come piè di pagina personalizzato nell'invito. La lunghezza massima del testo che può essere aggiunta è 2 KB.

Le opzioni possono essere configurate tramite il pannello di controllo di Lync Server o Lync Server Management Shell.

<div>


**Per personalizzare l'invito alla riunione usando il pannello di controllo di Lync Server**

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **conferenza** e quindi su **Configurazione riunione**.

4.  Nella pagina **Configurazione riunione** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:
    
      - Per creare un criterio a livello di sito, fare clic su **configurazione sito**. Nel campo **Seleziona ricerca sito** digitare tutto o parte del nome del sito per il quale si desidera definire le impostazioni di partecipazione alle riunioni. Nell'elenco dei siti risultante fare clic sul sito desiderato e quindi fare clic su **OK**.
    
      - Per creare criteri a livello di pool, fare clic su **Configurazione pool**. Nel campo **selezionare un servizio** di ricerca digitare tutto o parte del nome del servizio pool per cui si desidera definire le impostazioni di partecipazione alle riunioni. Nell'elenco dei servizi risultante fare clic sul pool desiderato e quindi fare clic su **OK**.

5.  Eseguire una delle operazioni seguenti:
    
      - Nel campo **URL logo** Digitare l'URL per l'immagine del logo dell'organizzazione.
    
      - Nel campo **URL della Guida** Digitare l'URL del sito della guida o del supporto dell'organizzazione.
    
      - Nel campo **testo legale** Digitare l'URL del testo legale o della dichiarazione di non responsabilità che si desidera includere negli inviti alle riunioni.
    
      - Nel campo **testo piè** di pagina personalizzato digitare il testo del piè di pagina, fino a 2 KB.

**Per personalizzare l'invito alla riunione tramite Lync Server Management Shell**

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet **New-CsMeetingConfiguration** o **Set-CsMeetingConfiguration** per creare o configurare le opzioni dell'invito alla riunione. Ad esempio, eseguire:
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

