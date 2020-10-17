---
title: 'Lync Server 2013: abilitare o disabilitare il controllo delle versioni client'
description: 'Lync Server 2013: abilitare o disabilitare il controllo delle versioni client.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bbd190e827e028efc37365c3cd8ecab16b35dac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546622"
---
# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>Abilitare o disabilitare il controllo delle versioni client in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Le impostazioni di configurazione della versione client vengono utilizzate per abilitare o disabilitare il controllo della versione client, a livello globale o per siti particolari. La configurazione globale della versione client viene installata con Lync Server 2013 e viene utilizzata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server. Quando la configurazione globale è abilitata, tutti i criteri di versione client sul posto avranno effetto quando gli utenti tentano di eseguire l'accesso. È possibile disabilitare la configurazione della versione client globale se non si desidera che venga eseguito alcun controllo della versione client. È possibile abilitare o disabilitare il controllo delle versioni client da Lync Server 2013 Control Panel o Lync Server 2013 Management Shell.

<div>


> [!NOTE]  
> Poiché gli utenti anonimi non sono associati ad alcun utente, sito o servizio, sono interessati solo dai criteri a livello globale.



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>Per abilitare o disabilitare il controllo delle versioni dei client tramite il pannello di gestione di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi fare clic sul pulsante di spostamento **Configurazione versione client** .

4.  Eseguire le operazioni seguenti:
    
      - Per abilitare o disabilitare globalmente il controllo delle versioni dei client, fare doppio clic sulla configurazione **globale** e quindi modificare le impostazioni.
    
      - Per abilitare o disabilitare il controllo delle versioni dei client per un sito specifico, fare clic su **nuovo**, selezionare il sito, fare clic su **OK**e quindi modificare le impostazioni del sito.

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione del controllo delle versioni dei client tramite i cmdlet di Windows PowerShell

È possibile abilitare o disabilitare il controllo delle versioni client utilizzando il cmdlet **set-CsClientVersionConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-client-versioning"></a>Per abilitare il controllo delle versioni client

  - È possibile abilitare il controllo delle versioni dei client impostando la proprietà **Enabled** su True ($true).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>Per disabilitare il controllo delle versioni client

  - È possibile disabilitare il controllo delle versioni dei client impostando la proprietà **Enabled** su False ($false).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

