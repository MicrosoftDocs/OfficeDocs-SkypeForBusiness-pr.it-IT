---
title: 'Lync Server 2013: installare i file per Mediation Server'
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
ms.openlocfilehash: c84d5fc2c863e0e56af275a4bee084652742eeac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a>Installare i file per Mediation Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-08-06_

Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server, almeno come amministratore locale e un utente di dominio con appartenenza almeno al gruppo RTCUniversalReadOnlyAdmins.

Seguire i passaggi descritti in questo argomento per eseguire la distribuzione guidata di Lync Server 2013 per installare i file per Mediation Server in un computer aggiunto a un pool di Mediation Server quando è stato usato generatore di topologie per definire e pubblicare il pool. Durante l'installazione di file Mediation Server è anche possibile installare e assegnare il certificato richiesto da ogni computer in un pool di Mediation Server.

In questo sito, se sono già stati distribuiti server di mediazione collocati nei pool Front-end o in un server Standard Edition, è possibile ignorare questo argomento e, invece, continuare a [configurare Trunks in Lync server 2013](lync-server-2013-configuring-trunks.md).

<div>


> [!NOTE]  
> Questo argomento presuppone che sia già stato definito e pubblicato un pool di Mediation Server autonomo come descritto in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">definire un Mediation Server in Generatore di topologia in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">pubblicare la topologia in Lync Server 2013</A> nella documentazione di distribuzione. e verificare che i computer nel pool di Mediation server soddisfino i prerequisiti descritti in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">prerequisiti software per enterprise Voice in Lync Server 2013</A> e <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">prerequisiti per la sicurezza e la configurazione per le aziende Voce in Lync Server 2013</A>.



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Per installare i file per un pool di Mediation Server autonomo

1.  Dal supporto di installazione fare clic con il \<pulsante destro\>del mouse su installazione media**\\Setup. exe\\amd64\\**e quindi scegliere **Esegui come amministratore**.

2.  Nella pagina **posizione di installazione** fare clic su **OK**.

3.  Nella pagina **contratto di licenza con l'utente finale** fare clic su **Accetto**e quindi fare clic su **OK**. (Obbligatorio per continuare).

4.  Nella pagina **distribuzione guidata di Lync server 2010** fare clic su **Installa o aggiorna Lync Server System**.

5.  Accanto al **passaggio 1: installare l'archivio configurazione locale**, fare clic su **Esegui**e quindi seguire le istruzioni visualizzate.

6.  Nella pagina **Configura replica locale della pagina Central Management store** accettare il recupero predefinito **direttamente dall'Central Management store**e quindi fare clic su **Avanti**.

7.  Nella pagina **esecuzione dei comandi** , quando lo stato dell'attività viene visualizzato come **completato**, fare clic su **fine**.

8.  Accanto al **passaggio 2: configurare o rimuovere i componenti di Lync Server**, fare clic su **Esegui**e quindi su **Avanti**.

9.  Nella pagina **esecuzione dei comandi** , quando lo stato dell'attività viene visualizzato come **completato**, fare clic su **fine**.

10. Accanto al **passaggio 3: richiedere, installare o assegnare certificati**, fare clic su **Esegui**. Seguire le istruzioni visualizzate per accettare le impostazioni predefinite. Il Mediation Server richiede un certificato e quindi verrà eseguito due volte il **passaggio 3** : una volta per emettere il certificato richiesto e ancora una volta per assegnarlo.

11. Quando il certificato è stato emesso e assegnato correttamente, accanto al **passaggio 4: avviare i servizi**, fare clic su **Esegui**e quindi seguire le istruzioni visualizzate.

12. Quando il **passaggio 4** è stato completato correttamente, riavviare il server e accedere al server come membro del gruppo DomainAdmins.

13. Nel computer in cui è in uso il pannello di controllo di Lync Server verificare nella pagina **topologia** del pannello di controllo di Lync Server che lo stato del servizio di Mediation Server viene visualizzato come segno di spunta verde. Se invece viene visualizzata una X rossa, selezionare il Mediation Server. Nel menu **azione** fare clic su **Avvia tutti i servizi**.

Se sono stati aggiunti più computer al pool di Mediation Server, eseguire i passaggi descritti in questa procedura in tutti gli altri computer del pool di Mediation Server. Se non è necessario installare file per Mediation Server per altri computer, seguire le procedure descritte in configurazione di [Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) per configurare le impostazioni per la connessione trunk tra questo pool di Mediation Server (o tutti i Mediation Server di un sito) e il relativo peer.

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

