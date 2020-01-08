---
title: 'Lync Server 2013: visualizzare un elenco di applicazioni attendibili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23866bfbc437d87911a84d065ae7f501c7d80466
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a>Visualizzare un elenco di applicazioni attendibili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

È possibile usare il pannello di controllo di Lync Server 2013 per visualizzare un elenco delle applicazioni attendibili distribuite nell'ambiente Lync Server 2013. Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK attendibile per Lync Server 2013. Questa relazione di trust viene riepilogata nell'elenco seguente:

  - Le applicazioni attendibili non vengono contestate per l'autenticazione da Lync Server.

  - Le applicazioni attendibili non vengono limitate da Lync Server per le transazioni SIP, le connessioni o le chiamate VoIP (Voice over Internet Protocol) in uscita.

  - Le applicazioni attendibili possono rappresentare qualsiasi utente e possono partecipare a conferenze senza comparire in roster.

  - Le applicazioni attendibili sono altamente disponibili e resilienti.

Nel pannello di controllo di Lync Server è possibile visualizzare il nome delle applicazioni, il pool in cui vengono eseguiti e la porta che usano.

<div>

## <a name="to-view-a-list-of-trusted-applications"></a>Per visualizzare un elenco di applicazioni attendibili

1.  Da un account utente assegnato al ruolo CsServerAdministrator, CsAdministrator, CsHelpDesk o CsViewOnlyAdministrator, accedere a qualsiasi computer della distribuzione interna. Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Lync Server 2013, vedere [pianificazione per il controllo dell'accesso basato sui ruoli in Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **topologia** e fare clic su **applicazione attendibile**.

4.  Nella pagina dell' **applicazione attendibile** fare clic su un'intestazione di colonna per ordinare le applicazioni, se necessario.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Gestione della topologia di Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

