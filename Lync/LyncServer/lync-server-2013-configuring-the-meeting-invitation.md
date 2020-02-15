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
ms.openlocfilehash: 5697605b4560fc91a153869204756f0ddda356fc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a>Configurazione dell'invito alla riunione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-16_

È possibile personalizzare gli inviti alle riunioni inviati dal componente aggiuntivo per riunioni online per Lync 2013 includendo i seguenti elementi facoltativi nel corpo dell'invito alla riunione:

  - **Logo dell'organizzazione** Aggiungere il logo dell'organizzazione agli inviti alle riunioni utilizzando l'opzione URL logo. Se gli inviti alle riunioni vengono inviati a utenti esterni all'organizzazione, l'immagine deve trovarsi in un URL disponibile pubblicamente. I formati di immagine supportati sono GIF e JPG. Anche se Lync Server 2013 archivia l'URL senza restrizioni di dimensione per l'immagine, per ottenere risultati ottimali, le dimensioni massime dell'immagine devono essere alte 30 pixel di 188 pixel di larghezza.

  - **Un collegamento di supporto o assistenza personalizzato** Aggiungere un URL per la guida o il sito Web del team di supporto dell'organizzazione. Se gli inviti alle riunioni verranno inviati agli utenti esterni all'organizzazione, l'URL dovrebbe essere disponibile pubblicamente. La lunghezza massima dell'URL è pari a 1 KB.

  - **Testo della dichiarazione di non responsabilità legale** Aggiungere un URL per il testo legale o una dichiarazione di non responsabilità che verrà visualizzata in tutti gli inviti alle riunioni. Se gli inviti alle riunioni verranno inviati agli utenti esterni all'organizzazione, l'URL dovrebbe essere disponibile pubblicamente. La lunghezza massima dell'URL è pari a 1 KB.

  - **Testo del piè** di pagina personalizzato Aggiungere del testo di cui verrà eseguito il rendering come piè di pagina personalizzato nell'invito. La lunghezza massima del testo che è possibile aggiungere è 2 KB.

È possibile configurare queste opzioni utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell.

<div>


**Per personalizzare l'invito alla riunione utilizzando il pannello di controllo di Lync Server**

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Configurazione riunione**.

4.  Nella pagina **Configurazione riunione** fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti:
    
      - Per creare un criterio a livello di sito, fare clic su **Configurazione sito**. Nel campo di ricerca **Seleziona un sito** digitare il nome del sito per cui si desidera definire le impostazioni di partecipazione alle riunioni, per intero o in parte. Fare clic sul sito desiderato nell'elenco dei siti e quindi fare clic su **OK**.
    
      - Per creare un criterio a livello di pool, fare clic su **Configurazione pool**. Nel campo di ricerca **Seleziona un servizio** digitare il nome del pool per cui si desidera definire le impostazioni di partecipazione alle riunioni, per intero o in parte. Fare clic su un pool desiderato nell'elenco di servizi e quindi su **OK**.

5.  Eseguire una delle operazioni seguenti:
    
      - Nel campo **URL logo** Digitare l'URL dell'immagine del logo dell'organizzazione.
    
      - Nel campo **URL della Guida** Digitare l'URL del sito di supporto o della Guida dell'organizzazione.
    
      - Nel campo **testo legale** Digitare l'URL del testo legale o della dichiarazione di non responsabilità che si desidera includere negli inviti alle riunioni.
    
      - Nel campo di **testo del piè** di pagina personalizzato digitare il testo del piè di pagina, fino a 2 KB.

**Per personalizzare l'invito alla riunione mediante Lync Server Management Shell**

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet **New-CsMeetingConfiguration** o **Set-CsMeetingConfiguration** per creare o configurare le opzioni di invito alla riunione. Ad esempio, eseguire:
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

