---
title: 'Lync Server 2013: visualizzazione di un elenco di applicazioni attendibili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 866286215389b0e446392bffe3e33f56a767f2e6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a>Visualizzare un elenco di applicazioni attendibili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

È possibile utilizzare il pannello di controllo di Lync Server 2013 per visualizzare un elenco delle applicazioni attendibili distribuite nell'ambiente Lync Server 2013. Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK che è considerato attendibile da Lync Server 2013. Questa relazione di trust è riepilogata nell'elenco seguente:

  - Le applicazioni attendibili non sono contestate per l'autenticazione da parte di Lync Server.

  - Le applicazioni attendibili non vengono limitate da Lync Server per le transazioni SIP, le connessioni o le chiamate VoIP (Voice over Internet Protocol) in uscita.

  - Le applicazioni attendibili possono rappresentare qualsiasi utente e possono partecipare a conferenze senza essere inserite negli elenchi dei partecipanti.

  - Le applicazioni attendibili sono resilienti e a disponibilità elevata.

Nel pannello di controllo di Lync Server, è possibile visualizzare il nome delle applicazioni, il pool in cui vengono eseguite e la porta utilizzata.

<div>

## <a name="to-view-a-list-of-trusted-applications"></a>Per visualizzare un elenco di applicazioni attendibili

1.  Da un account utente assegnato al ruolo CsServerAdministrator, CsAdministrator, CsHelpDesk o CsViewOnlyAdministrator, accedere a un computer nella distribuzione interna. Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Lync Server 2013, vedere [pianificazione del controllo di accesso basato sui ruoli in Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Applicazioni attendibili**.

4.  Nella pagina **Applicazione attendibile** fare clic sull'intestazione di una colonna per ordinare le applicazioni, se necessario.

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

