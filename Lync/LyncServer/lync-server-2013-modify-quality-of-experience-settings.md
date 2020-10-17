---
title: 'Lync Server 2013: modificare le impostazioni di qualità delle esperienze'
description: 'Lync Server 2013: modificare le impostazioni di qualità delle esperienze.'
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
ms.openlocfilehash: 8e1372a41adaf8107e2e1ed02042cbcfe3223705
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566982"
---
# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a>Modificare le impostazioni di qualità delle esperienze in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Per impostazione predefinita, i dati relativi alla QoE (Quality of Experience) vengono eliminati dopo 60 giorni. È possibile utilizzare le impostazioni nella pagina **Dati QoE** per conservare i dati per un periodo superiore o inferiore. Se si disabilita la funzionalità QoE, verranno eliminati anche i dati acquisiti prima dell'abilitazione di questa funzionalità.

<div>


> [!NOTE]  
> È consigliabile configurare la registrazione dettagli chiamata (CDR, Call Detail Recording) e QoE in modo che mantengano i dati per lo stesso numero di giorni. Ogni chiamata inclusa nei rapporti Dettagli chiamata, disponibili dalla home page dei rapporti di monitoraggio, include informazioni di registrazione dettagli chiamata e QoE. Se il periodo che precede l'eliminazione è diverso, alcune chiamate potrebbero includere solo dati di registrazione dettagli chiamata e altre solo dati QoE.



</div>

Nella procedura seguente viene descritto come configurare le impostazioni per l'eliminazione dei dati QoE.

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a>Per specificare il mantenimento dei dati QoE utilizzando il pannello di controllo di Lync Server

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.

4.  Nella pagina **Dati QoE** fare clic sul sito appropriato nella tabella, fare clic su **Modifica** e quindi su **Mostra dettagli**.

5.  Per abilitare l'eliminazione, selezionare **Abilita eliminazione dei dati QoE**.

6.  In **Mantieni dati QoE per durata massima (giorni)** selezionare il numero massimo di giorni per cui mantenere i dati QoE.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Impostazione della conservazione QoE tramite i cmdlet di Windows PowerShell

È possibile creare impostazioni di conservazione QoE utilizzando Windows PowerShell e il cmdlet **Set-CsQoEConfiguration** . È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a>Per specificare il mantenimento dei dati QoE per una posizione specifica

  - Questo comando consente di abilitare l'eliminazione dei dati QoE per il sito Redmond e di configurare il sito per mantenere i dati QoE per 20 giorni.
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a>Per specificare il mantenimento dei dati QoE per più posizioni

  - Questo comando consente di configurare il mantenimento dei dati QoE per tutte le impostazioni di configurazione QoE in uso in un'organizzazione.
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) .

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

