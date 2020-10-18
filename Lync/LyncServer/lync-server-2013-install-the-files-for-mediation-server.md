---
title: 'Lync Server 2013: installare i file per Mediation Server'
description: 'Lync Server 2013: installare i file per Mediation Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea1fc20fb91328d116a4aee62b96b95aa3e270eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574072"
---
# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a>Installare i file per Mediation Server in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-08-06_

Per eseguire questa procedura, è necessario accedere al server almeno come amministratore locale e come utente di dominio appartenente almeno al gruppo RTCUniversalReadOnlyAdmin.

Utilizzare la procedura descritta in questo argomento per eseguire la distribuzione guidata di Lync Server 2013 per installare i file per Mediation Server in un computer aggiunto a un pool di Mediation Server quando è stato utilizzato il generatore di topologie per definire e pubblicare il pool. Quando si installano i file Mediation Server, è inoltre necessario installare e assegnare il certificato richiesto da ogni computer in un pool di Mediation Server.

In questo sito, se sono già stati distribuiti i Mediation Server collocati nei pool Front end o nel server Standard Edition, è possibile ignorare questo argomento e, invece, continuare con la [configurazione dei trunk in Lync server 2013](lync-server-2013-configuring-trunks.md).

<div>


> [!NOTE]  
> In questo argomento si presuppone che sia già stato definito e pubblicato un pool di Mediation Server autonomo, come descritto in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">define a Mediation Server in Generatore di topologie in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">pubblicare la topologia in Lync Server 2013</A> nella documentazione relativa alla distribuzione. e verificare che i computer nel pool di Mediation server soddisfino i prerequisiti descritti in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software Prerequisites for voip aziendale in Lync Server 2013</A> e <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">prerequisiti di configurazione e sicurezza per VoIP aziendale in Lync Server 2013</A>.



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Per installare i file per un pool Mediation Server autonomo

1.  Dal supporto di installazione fare clic con il pulsante destro del mouse su \<installation media\> ** \\ Setup \\ amd64 \\Setup.exe**e quindi scegliere **Esegui come amministratore**.

2.  Nella pagina **Percorso di installazione** fare clic su **OK**.

3.  Nella pagina **Contratto di licenza con l'utente finale** fare clic su **Accetto** e quindi su **OK**. Questa operazione è obbligatoria per proseguire.

4.  Nella pagina **Distribuzione guidata di Lync Server 2010** fare clic su **Installa o aggiorna il sistema Lync Server**.

5.  Accanto a **Passaggio 1: Installazione dell'archivio di configurazione locale** fare clic su **Esegui** e quindi seguire le istruzioni visualizzate sullo schermo.

6.  Nella pagina **Configura la replica locale dell'archivio di gestione centrale** accettare l'impostazione predefinita **Recupera direttamente dall'archivio di gestione centrale** e quindi fare clic su **Avanti**.

7.  Nella pagina **Esecuzione comandi in corso**, quando lo stato dell'attività risulta completato,**** fare clic su **Fine**.

8.  Accanto a **Passaggio 2: Installazione o rimozione componenti di Lync Server** fare clic su **Esegui** e quindi su **Avanti**.

9.  Nella pagina **Esecuzione comandi in corso**, quando lo stato dell'attività risulta completato,**** fare clic su **Fine**.

10. Accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati** fare clic su **Esegui**. Seguire le istruzioni visualizzate sullo schermo, accettando le impostazioni predefinite. Il Mediation Server richiede un certificato, quindi il **Passaggio 3** verrà eseguito due volte, una per emettere il certificato necessario e l'altra per assegnarlo.

11. Dopo che il certificato è stato emesso e assegnato correttamente, accanto **Passaggio 4: Avvia servizi** fare clic su **Esegui** e quindi seguire le istruzioni visualizzate sullo schermo.

12. Al termine del **Passaggio 4**, riavviare il server e accedere come membro del gruppo DomainAdmins.

13. Nel computer in cui è in esecuzione il pannello di controllo di Lync Server, verificare nella pagina **topologia** del pannello di controllo di Lync Server che lo stato del servizio del Mediation Server sia visualizzato come segno di spunta verde. Se invece appare una X rossa, selezionare il Mediation Server. Scegliere **Avvia tutti i servizi** dal menu **Azione**.

Se è stato aggiunto più di un computer al pool di Mediation Server, eseguire i passaggi descritti in questa procedura in tutti gli altri computer del pool di Mediation Server. Se non è necessario installare i file per Mediation Server per altri computer, seguire le procedure illustrate in [Configuring Trunks in Lync server 2013](lync-server-2013-configuring-trunks.md) per configurare le impostazioni per la connessione trunk tra il pool di Mediation Server (o tutti i Mediation Server in un sito) e il relativo peer.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti dei certificati per i server interni in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

