---
title: Eliminare una raccolta esistente di impostazioni di configurazione della versione client
description: Eliminare una raccolta esistente di impostazioni di configurazione della versione client.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25a7d384bdfd84a1a6e04041988c16788a116626
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572882"
---
# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Eliminare una raccolta esistente di impostazioni di configurazione della versione client in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Se si desidera rimuovere le impostazioni di configurazione del client precedentemente configurate per un sito, è possibile rimuovere le impostazioni dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a>Per rimuovere le impostazioni di configurazione client utilizzando il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi fare clic sul pulsante di spostamento **Configurazione versione client** .

4.  Selezionare il sito, fare clic su **modifica**, scegliere **Elimina**e quindi fare clic su **OK**.

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione delle impostazioni di configurazione della versione client tramite i cmdlet di Windows PowerShell

Per eliminare le impostazioni di configurazione della versione client, è possibile utilizzare il cmdlet **Remove-CsClientVersionConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a>Per rimuovere una raccolta specificata di impostazioni di configurazione della versione client

  - Con il comando seguente vengono rimosse le impostazioni di configurazione della versione client applicate al sito Redmond:
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a>Per rimuovere tutte le impostazioni di configurazione della versione client applicate all'ambito del sito

  - Questo comando rimuove tutte le impostazioni di configurazione della versione client configurate nell'ambito del sito:
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a>Per rimuovere tutte le impostazioni di configurazione della versione client in base al valore della proprietà DefaultAction

  - Questo comando rimuove tutte le impostazioni di configurazione della versione client in cui l'azione predefinita è stata impostata su "blocca":
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

