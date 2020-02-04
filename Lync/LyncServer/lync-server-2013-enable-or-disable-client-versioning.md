---
title: 'Lync Server 2013: abilitare o disabilitare il controllo delle versioni dei client'
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
ms.openlocfilehash: f413df3ec1d35438155492a32d9fdff449aec3c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>Abilitare o disabilitare il controllo delle versioni client in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Le impostazioni di configurazione della versione client vengono usate per attivare o disattivare il controllo della versione client, sia a livello globale che per siti particolari. La configurazione della versione client globale viene installata con Lync Server 2013 e viene usata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server. Quando la configurazione globale è abilitata, i criteri di versione client in vigore saranno effettivi quando gli utenti tenteranno di accedere. È possibile disabilitare la configurazione della versione client globale se non si vuole che venga eseguito alcun controllo della versione client. È possibile abilitare o disabilitare il controllo delle versioni del client da Lync Server 2013 Control Panel o Lync Server 2013 Management Shell.

<div>


> [!NOTE]  
> Poiché gli utenti anonimi non sono associati ad alcun utente, sito o servizio, sono interessati solo dai criteri a livello globale.



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>Per abilitare o disabilitare il controllo delle versioni del client tramite il pannello di controlli di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento della **configurazione della versione client** .

4.  Effettuare le seguenti operazioni:
    
      - Per abilitare o disabilitare globalmente il controllo delle versioni dei client, fare doppio clic sulla configurazione **globale** e quindi modificare le impostazioni.
    
      - Per abilitare o disabilitare il controllo delle versioni dei client per un determinato sito, fare clic su **nuovo**, selezionare il sito, fare clic su **OK**e quindi modificare le impostazioni per il sito.

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione del controllo delle versioni client con i cmdlet di Windows PowerShell

Puoi abilitare o disabilitare il controllo delle versioni del client usando il cmdlet **set-CsClientVersionConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-enable-client-versioning"></a>Per abilitare il controllo delle versioni del client

  - Puoi abilitare il controllo delle versioni del client impostando la proprietà **Enabled** su True ($true).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>Per disabilitare il controllo delle versioni del client

  - Puoi disabilitare il controllo delle versioni dei client impostando la proprietà **Enabled** su False ($false).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

