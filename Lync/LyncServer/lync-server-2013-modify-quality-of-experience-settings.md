---
title: "Lync Server 2013: modificare la qualità delle impostazioni dell'esperienza"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify Quality of Experience settings
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48184996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2cf4745f76fa4667d14c9da5ca2b4e5309767b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a>Modificare le impostazioni di qualità delle esperienze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Per impostazione predefinita, i dati di qualità dell'esperienza (QoE) vengono eliminati dopo 60 giorni. Per mantenere i dati per un periodo di tempo più lungo o più breve, è possibile usare le impostazioni nella pagina di **dati qualità della prova** . Se si disattiva QoE, anche i dati acquisiti prima dell'abilitazione di QoE saranno soggetti all'eliminazione.

<div>


> [!NOTE]  
> Devi configurare la registrazione dei dettagli delle chiamate (CDR) e QoE per mantenere i dati per lo stesso numero di giorni. Ogni chiamata nei report dettagli chiamata (CDRs), disponibile nella Home page dei report di monitoraggio, include informazioni CDR e QoE. Se la durata di eliminazione per CDR e QoE è diversa, alcune chiamate possono includere solo dati CDR, mentre altre possono includere solo dati QoE.



</div>

La procedura seguente descrive come configurare le impostazioni di eliminazione dei dati QoE.

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a>Per specificare la conservazione dei dati QoE tramite il pannello di controllo di Lync Server

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.

4.  Nella pagina **qualità di dati esperienza** fare clic sul sito appropriato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  Per attivare l'eliminazione, selezionare **Abilita l'eliminazione di QoE**.

6.  In **Mantieni QoE per la durata massima (giorni)** selezionare il numero massimo di giorni in cui devono essere conservati i dati QoE.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Specifica della conservazione QoE usando i cmdlet di Windows PowerShell

È possibile creare impostazioni di conservazione QoE usando Windows PowerShell e il cmdlet **Set-CsQoEConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a>Per specificare la conservazione QoE per una posizione specifica

  - Questo comando consente l'eliminazione dei dati QoE per il sito Redmond e configura il sito per la gestione dei dati QoE per 20 giorni.
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a>Per specificare la conservazione QoE per più posizioni

  - Questo comando configura la conservazione QoE per tutte le impostazioni di configurazione QoE in uso in un'organizzazione.
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Distribuzione del monitoraggio in Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

