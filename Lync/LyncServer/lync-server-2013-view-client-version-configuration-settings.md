---
title: 'Lync Server 2013: visualizzare le impostazioni di configurazione della versione client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View client version configuration settings
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923062(v=OCS.15)
ms:contentKeyID: 50675353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9db03377f8f2fc880de61639f4eedc5b1c302d21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-configuration-settings-in-lync-server-2013"></a>Visualizzare le impostazioni di configurazione della versione client in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Le impostazioni di configurazione della versione client vengono utilizzate per attivare o disattivare il controllo della versione client. La configurazione della versione client globale viene installata con Lync Server 2013 e viene usata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server. Se la configurazione globale è abilitata, tutti i criteri relativi alla versione client disponibili verranno applicati quando gli utenti tentano l'accesso. È possibile visualizzare le impostazioni di configurazione della versione client dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.

<div>


> [!NOTE]  
> Poiché gli utenti anonimi non sono associati ad alcun utente, sito o servizio, sono interessati solo dai criteri a livello globale.



</div>

<div>

## <a name="to-view-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Per visualizzare le impostazioni di configurazione della versione client tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento della **configurazione della versione client** .

4.  Fare doppio clic sul nome della configurazione della versione client che si vuole visualizzare.

</div>

<div>

## <a name="viewing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle impostazioni di configurazione della versione client con i cmdlet di Windows PowerShell

Puoi visualizzare le impostazioni di configurazione della versione client usando il cmdlet **Get-CsClientVersionConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-view-client-version-configuration-information"></a>Per visualizzare le informazioni sulla configurazione della versione client

  - Per visualizzare informazioni su tutte le impostazioni di configurazione della versione client, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsClientVersionConfiguration
    
    Questo restituirà informazioni simili alla seguente:
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

</div>

Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

