---
title: 'Lync Server 2013: visualizzazione e analisi dei report di Monitoring Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7416b54e7b1ddb5bfc41c07502802c7c120a93ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523573"
---
# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>Visualizzazione e analisi dei report di Monitoring Server in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-19_

Monitoring Server Reports offre diverse misure di qualità vocale per monitorare gli QoE che vengono recapitati agli utenti finali. Monitoring Server include inoltre numerosi report incorporati che l'organizzazione può utilizzare per visualizzare le tendenze relative all'utilizzo e alla qualità dei contenuti multimediali sulla rete dell'organizzazione e risolvere i problemi relativi alla qualità multimediale che si verificano.

Una parte principale del mantenimento dei rapporti di Monitoring Server che interessano le operazioni quotidiane e settimanali è la visualizzazione e l'analisi dei rapporti sulla qualità multimediale, in particolare:

  - Riepilogo QoE/rapporti di tendenza

  - Rapporti sulle prestazioni QoE

<div>

## <a name="view-reports-from-the-monitoring-server"></a>Visualizzare i report dal Monitoring Server

1.  Da un Web browser, individuare i server che ospitano SQL Reporting Services.

2.  Visualizzare i report necessari dalla schermata del browser.

3.  Optional Esportare un report selezionando l'opzione Esporta e il formato di output necessario.

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>Configurare la registrazione dettagli chiamata (CDR)

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins o con autorizzazioni equivalenti oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.

3.  Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Registrazione dettagli chiamata**.

4.  Nella pagina **Registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, fare clic su **Modifica** e quindi su **Mostra dettagli**.

5.  Per attivare l'eliminazione, selezionare **Abilita eliminazione per i server di monitoraggio**.

6.  In **Mantieni registrazioni dettagli chiamata per durata massima (giorni):** selezionare il numero massimo di giorni in cui devono essere conservate le registrazioni dettagli chiamata.

7.  In **Mantieni dati delle segnalazioni errori per durata massima (giorni)** selezionare il numero massimo di giorni per cui mantenere le segnalazioni degli errori.

8.  Fare clic su **Commit**.

</div>

<div>

## <a name="configure-qoe"></a>Configurare QoE

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere Delegate Setup Permissions.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.

3.  Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.

4.  Nella pagina **Dati QoE** fare clic sul sito appropriato nella tabella, fare clic su **Modifica** e quindi su **Mostra dettagli**.

5.  Per attivare l'eliminazione, selezionare **Abilita eliminazione per i server di monitoraggio**.

6.  In **Mantieni registrazioni dettagli chiamata per durata massima (giorni):** selezionare il numero massimo di giorni in cui i dati QoE devono essere conservati.

7.  Fare clic su Commit.

</div>

<div>

## <a name="change-the-archiving-policy"></a>Modificare i criteri di archiviazione

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.

3.  Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.

4.  Fare clic su **Globale** nell'elenco dei criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.

5.  In **Modifica Criteri di archiviazione - Globale** eseguire le operazioni seguenti:

6.  Per abilitare o disabilitare l'archiviazione interna per la distribuzione, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .

7.  Per abilitare o disabilitare l'archiviazione esterna per la distribuzione, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .

8.  Fare clic su **Commit**.

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>Applicazione di un criterio di archiviazione a un utente

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.

3.  Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.

4.  Nella tabella in cui sono elencati i risultati di ricerca, fare clic sull'account utente, scegliere **Modifica** e quindi **Mostra dettagli**.

5.  In **modifica utente di Lync Server** in **criteri di archiviazione**Selezionare i criteri utente di archiviazione che si desidera applicare.

6.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Utilizzo di report di monitoraggio in Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
[Report sulle prestazioni del server in Lync Server 2013](lync-server-2013-server-performance-report.md)  
[Rapporto di confronto qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

