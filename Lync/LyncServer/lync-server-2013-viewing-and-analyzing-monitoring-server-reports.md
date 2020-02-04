---
title: 'Lync Server 2013: visualizzazione e analisi dei report del server di monitoraggio'
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
ms.openlocfilehash: 9e4fce6cf17601d2a68a07a3b832e6b50c10b759
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>Visualizzazione e analisi dei report del server di monitoraggio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-19_

Monitoring Server Reports offre diverse misure di qualità vocale per monitorare gli QoE che vengono recapitati agli utenti finali. Il server di monitoraggio include inoltre diversi report predefiniti che l'organizzazione può usare per guardare l'uso e le tendenze della qualità multimediale nella rete dell'organizzazione e risolvere i problemi di qualità dei contenuti multimediali che si verificano.

Una parte principale della gestione dei report del server di monitoraggio che interessano le operazioni quotidiane e settimanali è la visualizzazione e l'analisi dei report sulla qualità multimediale, in particolare:

  - Riepilogo QoE/report di tendenza

  - Report prestazioni QoE

<div>

## <a name="view-reports-from-the-monitoring-server"></a>Visualizzare i report dal server di monitoraggio

1.  In un Web browser individuare i server che ospitano SQL Reporting Services.

2.  Visualizzare i report necessari dalla schermata del browser.

3.  Opzionale Esportare un report selezionando l'opzione Esporta e il formato di output richiesto.

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>Configurare la registrazione dettagli chiamata (CDR)

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con autorizzazioni equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **registrazione dettagli chiamata**.

4.  Nella pagina **registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  Per attivare l'eliminazione, selezionare **Abilita eliminazione per i server di monitoraggio**.

6.  In **Mantieni registrazioni dei dettagli delle chiamate per la durata massima (giorni):** selezionare il numero massimo di giorni in cui le registrazioni dei dettagli delle chiamate devono essere mantenute.

7.  In **Mantieni i dati del report sugli errori per la durata massima (giorni):** selezionare il numero massimo di giorni in cui devono essere mantenuti i report degli errori.

8.  Fare clic su **Commit**.

</div>

<div>

## <a name="configure-qoe"></a>Configurare QoE

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere delegare le autorizzazioni di configurazione.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.

4.  Nella pagina **qualità di dati esperienza** fare clic sul sito appropriato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  Per attivare l'eliminazione, selezionare **Abilita eliminazione per i server di monitoraggio**.

6.  In **Mantieni registrazioni dei dettagli delle chiamate per la durata massima (giorni):** selezionare il numero massimo di giorni di conservazione dei dati QoE.

7.  Fare clic su Commit.

</div>

<div>

## <a name="change-the-archiving-policy"></a>Modificare i criteri di archiviazione

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.

4.  Fare clic su **Globale** nell'elenco dei criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.

5.  In **modifica criteri di archiviazione-globale**eseguire le operazioni seguenti:

6.  Per abilitare o disabilitare l'archiviazione interna per la distribuzione, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .

7.  Per abilitare o disabilitare l'archiviazione esterna per la distribuzione, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .

8.  Fare clic su **Commit**.

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>Applicare un criterio di archiviazione a un utente

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.

3.  Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.

4.  Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.

5.  In **modifica utenti di Lync Server** in **criteri di archiviazione**Selezionare i criteri utente di archiviazione che si desidera applicare.

6.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Uso di report di monitoraggio in Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
[Report prestazioni server in Lync Server 2013](lync-server-2013-server-performance-report.md)  
[Report di confronto qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

