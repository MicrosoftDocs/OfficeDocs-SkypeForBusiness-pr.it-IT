---
title: 'Lync Server 2013: eliminare le impostazioni di configurazione della qualità delle esperienze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Quality of Experience configuration settings
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48185954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bef2a59243d065f74c09dd4bc5c3aeb6a4451bbd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a>Eliminare le impostazioni di configurazione della qualità delle esperienze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Le metriche sulla qualità delle esperienze (QoE) tengono traccia della qualità delle chiamate audio e video effettuate nell'organizzazione, tra cui il numero di pacchetti di rete persi, il rumore di fondo e la quantità di "jitter" (differenze nel ritardo del pacchetto). Queste metriche sono archiviate in un database, oltre ad altri dati, ad esempio i record dettagli chiamata, che consentono di abilitare e disabilitare QoE indipendentemente da altre registrazioni di dati.

Quando si installa Microsoft Lync Server 2013, viene creata una singola raccolta globale di impostazioni di configurazione QoE. Gli amministratori hanno anche la possibilità di creare raccolte di impostazioni personalizzate che possono essere applicate a singoli siti. In base alla progettazione, le impostazioni configurate nell'ambito del sito hanno la precedenza sulle impostazioni configurate nell'ambito globale. Se si eliminano le impostazioni con ambito sito, QoE verrà gestito in tale sito utilizzando le impostazioni globali.

Tieni presente che puoi anche "eliminare" le impostazioni globali. Tuttavia, le impostazioni globali non verranno effettivamente rimosse. Tutte le proprietà della raccolta verranno invece reimpostate sui rispettivi valori predefiniti. Ad esempio, per impostazione predefinita, l'eliminazione è abilitata in una raccolta di impostazioni di configurazione QoE. Supponiamo che tu modifichi la raccolta globale in modo che l'eliminazione sia disabilitata. Se in seguito si eliminano le impostazioni globali, tutte le proprietà verranno reimpostate sui valori predefiniti. In questo caso, ciò significa che l'eliminazione sarà ancora una volta abilitata.

È possibile rimuovere le impostazioni di configurazione QoE usando il pannello di controllo di Lync Server o usando il cmdlet [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) .

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a>Per eliminare le impostazioni di configurazione QoE tramite il pannello di controllo di Lync Server

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.

4.  Nella pagina **qualità di dati esperienza** fare clic sui criteri desiderati, fare clic su **modifica**e quindi su **Elimina**.

5.  Fare clic su **OK**.

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione delle impostazioni di configurazione QoE con i cmdlet di Windows PowerShell

Puoi eliminare le impostazioni di configurazione QoE usando Windows PowerShell e il cmdlet **Remove-CsQoEConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>Per rimuovere una raccolta specificata di impostazioni di configurazione QoE

  - Questo comando rimuove le impostazioni di configurazione QoE applicate al sito Redmond:
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>Per rimuovere tutte le impostazioni di configurazione QoE applicate all'ambito del sito

  - Questo comando rimuove tutte le impostazioni di configurazione QoE applicate all'ambito del sito:
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Per rimuovere tutte le impostazioni di configurazione QoE in cui il monitoraggio QoE è disabilitato

  - Questo comando rimuove tutte le impostazioni di configurazione QoE in cui è stato disabilitato il monitoraggio QoE:
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

Per informazioni dettagliate, vedere [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

