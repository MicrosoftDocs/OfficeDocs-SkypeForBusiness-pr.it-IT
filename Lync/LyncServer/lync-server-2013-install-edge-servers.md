---
title: 'Lync Server 2013: installazione di server perimetrali'
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
ms.openlocfilehash: 8060d72c6a5c727f0171d3082e7c17d0ed4ac5ab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a>Installare server perimetrali per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

È possibile installare Lync Server 2013 nei server perimetrali utilizzando la distribuzione guidata di Lync Server. Eseguendo la distribuzione guidata in ogni server perimetrale, è possibile effettuare la maggior parte delle attività necessarie per installare il server perimetrale. Per distribuire Lync Server 2013 in un server perimetrale, è necessario che sia già stato eseguito Generatore di topologie per definire e pubblicare la topologia del server perimetrale ed esportarla in un supporto disponibile dal server perimetrale. Per ulteriori informazioni, vedere [scenari per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md) ed [esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

Dopo aver utilizzato la distribuzione guidata per installare ogni server perimetrale, installare e assegnare i certificati necessari e avviare i servizi necessari, è possibile completare il programma di installazione utilizzando le informazioni riportate in [configurazione del supporto per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-configuring-support-for-external-user-access.md) per abilitare e configurare l'accesso degli utenti esterni e le informazioni di [Verifica della distribuzione di Edge in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) per convalidare l'installazione

<div>

## <a name="to-install-an-edge-server"></a>Per installare un server perimetrale

1.  Eseguire l'accesso al computer in cui si desidera installare il server perimetrale come membri del gruppo Administrators locale o utilizzando un account con autorizzazioni e diritti utente equivalenti.

2.  Verificare che il file di configurazione della topologia creato utilizzando Generatore di topologie, quindi esportato e copiato su supporto esterno, sia disponibile nel server perimetrale, ad esempio accesso all'unità USB in cui è stato copiato il file di configurazione della topologia o verifica accesso alla condivisione di rete in cui è stato copiato il file.

3.  Avviare la Distribuzione guidata.
    
    <div>
    

    > [!NOTE]  
    > Se viene visualizzato un messaggio che indica la necessità di installare Microsoft Visual C++ Redistributable, fare clic su <STRONG>Sì</STRONG>. Nella finestra di dialogo successiva è possibile accettare il<STRONG> </STRONG>percorso di installazione predefinito oppure fare clic su <STRONG>Sfoglia</STRONG> per selezionare un percorso diverso e quindi fare clic su <STRONG>Installa</STRONG>. Nella finestra di dialogo successiva selezionare la casella di controllo <STRONG>Accetto i termini del Contratto di licenza</STRONG> e quindi fare clic su <STRONG>OK</STRONG>.

    
    </div>

4.  Nella Distribuzione guidata fare clic su **Installare o aggiornare il sistema Lync Server**.

5.  Dopo che viene determinato lo stato della distribuzione, per **Passaggio 1: Installazione dell'archivio di configurazione locale** fare clic su **Esegui** e quindi eseguire le operazioni seguenti:
    
      - Nella finestra di dialogo **Configura la replica locale dell'archivio di gestione centrale** fare clic su **Importa da un file (opzione consigliata per Edge Server)**, passare al percorso del file di configurazione della topologia esportato, selezionare il file con estensione zip, fare clic su **Apri** e quindi su **Avanti**.
    
      - Le informazioni di configurazione presenti nel file verranno lette e scritte nel file di configurazione XML nel computer locale.
    
      - Al termine del processo **Esecuzione comandi in corso**, fare clic su **Fine**.

6.  Nella distribuzione guidata fare clic su **passaggio 2: installazione o rimozione componenti di Lync Server** per installare i componenti perimetrali di lync Server 2013 specificati nel file di configurazione XML archiviato nel computer locale.

7.  Dopo aver completato l'installazione, utilizzare le informazioni contenute in [set up Edge Certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) per installare e assegnare i certificati necessari prima di avviare i servizi.

</div>

</div>

<span> </span>

</div>

</div>

</div>

