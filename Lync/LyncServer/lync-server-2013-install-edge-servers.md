---
title: 'Lync Server 2013: Installare server perimetrali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22d1961a158ead735ae63d20bb2bd233d6ed5958
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a>Installare server perimetrali per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

Si installa Lync Server 2013 in Edge Server tramite la distribuzione guidata di Lync Server. Eseguendo la distribuzione guidata in ogni Edge Server, è possibile completare la maggior parte delle attività necessarie per configurare il server perimetrale. Per distribuire Lync Server 2013 in un server perimetrale, è necessario avere già eseguito Generatore di topologia per definire e pubblicare la topologia di Edge Server ed esportarla in elementi multimediali disponibili nel server perimetrale. Per informazioni dettagliate, vedere [scenari per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md) ed [esportare la topologia di Lync Server 2013 e copiarla in elementi multimediali esterni per l'installazione di Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

Dopo aver usato la distribuzione guidata per installare ogni Edge Server, installare e assegnare i certificati necessari e avviare i servizi necessari, è possibile completare la configurazione usando le informazioni in [configurazione del supporto per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-configuring-support-for-external-user-access.md) per abilitare e configurare l'accesso degli utenti esterni e le informazioni per [verificare la distribuzione di Edge in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) per convalidare la configurazione, inclusa la connettività del server

<div>

## <a name="to-install-an-edge-server"></a>Per installare un server perimetrale

1.  Accedere al computer in cui si vuole installare l'Edge Server come membro del gruppo Administrators locale o un account con autorizzazioni e diritti utente equivalenti.

2.  Verificare che il file di configurazione della topologia creato con generatore di topologie e quindi esportato e copiato in elementi multimediali esterni sia disponibile nell'Edge Server, ad esempio accesso all'unità USB in cui è stato copiato il file di configurazione della topologia o verifica accesso alla condivisione di rete in cui è stato copiato il file.

3.  Avviare la distribuzione guidata.
    
    <div>
    

    > [!NOTE]  
    > Se viene visualizzato un messaggio che informa che è necessario installare Microsoft Visual C++ ridistribuibile, fare clic su <STRONG>Sì</STRONG>. Nella finestra di dialogo successiva è possibile accettare il percorso di <STRONG>installazione</STRONG> predefinito oppure fare clic sul pulsante <STRONG>Sfoglia</STRONG> per selezionare un percorso alternativo e quindi fare clic su <STRONG>Installa</STRONG>. Nella finestra di dialogo successiva selezionare la casella <STRONG>di controllo Accetto i termini del contratto di licenza</STRONG> e quindi fare clic su <STRONG>OK</STRONG>.

    
    </div>

4.  Nella distribuzione guidata fare clic su **Installa o aggiorna Lync Server System**.

5.  Dopo che la procedura guidata determina lo stato di distribuzione, al **passaggio 1. Installare l'archivio di configurazione locale**, fare clic su **Esegui** e quindi eseguire le operazioni seguenti:
    
      - Nella finestra di dialogo **Configura replica locale di Central Management store** fare clic su **Importa da un file (consigliato per Edge Server)**, spostarsi nel percorso del file di configurazione della topologia esportata, selezionare il file con estensione zip, fare clic su **Apri**e quindi fare clic su **Avanti**.
    
      - La distribuzione guidata legge le informazioni di configurazione dal file di configurazione e scrive il file di configurazione XML nel computer locale.
    
      - Dopo aver completato il processo di **esecuzione dei comandi** , fare clic su **fine**.

6.  Nella distribuzione guidata fare clic su **passaggio 2: configurare o rimuovere i componenti di Lync Server** per installare i componenti Edge di lync Server 2013 specificati nel file di configurazione XML archiviato nel computer locale.

7.  Dopo aver completato l'installazione, usare le informazioni in [configurare i certificati di Edge per Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) per installare e assegnare i certificati necessari prima di avviare i servizi.

</div>

</div>

<span> </span>

</div>

</div>

</div>

