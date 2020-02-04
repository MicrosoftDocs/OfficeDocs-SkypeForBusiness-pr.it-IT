---
title: 'Lync Server 2013: specificare la conservazione dei dati CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying retention of CDR data
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182581(v=OCS.15)
ms:contentKeyID: 48185299
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32eee413b25da3231d5633e89571bbc08deb1f38
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-retention-of-cdr-data-in-lync-server-2013"></a>Specifica della conservazione dei dati CDR in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Per impostazione predefinita, i dati della registrazione dei dettagli delle chiamate (CDR) vengono eliminati dopo 60 giorni. È possibile usare le impostazioni nella pagina **registrazione dettagli chiamata** per mantenere i dati per un periodo di tempo più lungo o più breve. Se si disattiva CDR, anche i dati acquisiti prima dell'abilitazione di CDR saranno soggetti all'eliminazione.

<div>


> [!NOTE]  
> È necessario configurare CDR e la qualità dell'esperienza (QoE) per mantenere i dati per lo stesso numero di giorni. Ogni chiamata nei report dettagli chiamata (CDRs), disponibile dalla pagina Web monitoraggio report server, include informazioni CDR e QoE. Se la durata di eliminazione per CDR e QoE è diversa, alcune chiamate potrebbero includere solo dati CDR, mentre altre possono includere solo dati QoE.



</div>

Usare le procedure seguenti per configurare le impostazioni di eliminazione dei dati CDR.

<div>

## <a name="to-specify-retention-of-cdr-data"></a>Per specificare la conservazione dei dati CDR

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **registrazione dettagli chiamata**.

4.  Nella pagina **registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  Per attivare l'eliminazione, selezionare **Abilita l'eliminazione di CDRS**.

6.  In **Mantieni CDRS per la durata massima (giorni):** selezionare il numero massimo di giorni in cui le registrazioni dei dettagli delle chiamate devono essere mantenute.

7.  In **Mantieni i dati del report sugli errori per la durata massima (giorni):** selezionare il numero massimo di giorni in cui devono essere mantenuti i report degli errori.

8.  Fare clic su **Commit**.

</div>

<div>

## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Specifica della conservazione CDR con i cmdlet di Windows PowerShell

È possibile creare impostazioni di conservazione CDR tramite Windows PowerShell e il cmdlet Set-CsCdrConfiguration. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-specify-cdr-retention-for-a-specific-location"></a>Per specificare la conservazione CDR per una posizione specifica

  - Questo comando consente l'eliminazione dei dati CDR per il sito Redmond e configura il sito per la gestione dei dati CDR e dei rapporti di errore per 20 giorni.
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<div>

## <a name="to-specify-cdr-retention-for-multiple-locations"></a>Per specificare la conservazione CDR per più posizioni

  - Questo comando configura la conservazione CDR per tutte le impostazioni di configurazione CDR in uso in un'organizzazione.
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Registrazione dettagli chiamata (CDR) in Lync Server 2013](lync-server-2013-call-detail-recording-cdr.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

