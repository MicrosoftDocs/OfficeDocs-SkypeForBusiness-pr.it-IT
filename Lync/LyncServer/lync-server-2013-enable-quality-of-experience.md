---
title: "Lync Server 2013: abilitare la qualità dell'esperienza"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dbccfd145ad8143edab10f92a10901e626075e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a>Abilitare la qualità dell'esperienza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

La qualità dell'esperienza (QoE) registra i dati numerici che indicano la qualità del supporto e le informazioni sui partecipanti, i nomi di dispositivo, i driver, gli indirizzi IP e i tipi di endpoint coinvolti in chiamate e sessioni. Per informazioni dettagliate, vedere [pianificazione del monitoraggio in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) nella documentazione relativa alla pianificazione.

Usare la procedura seguente per abilitare QoE per l'intera organizzazione o per ogni sito dell'organizzazione.

<div>


> [!NOTE]  
> Per abilitare QoE, è prima necessario configurare il monitoraggio e un database back-end di monitoraggio. Per informazioni dettagliate, vedere <A href="lync-server-2013-deploying-monitoring.md">distribuzione del monitoraggio in Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a>Per abilitare QoE tramite il pannello di controllo di Lync Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.

4.  Nella pagina **qualità di dati esperienza** fare clic sulla raccolta appropriata dalla tabella, fare clic su **azione**e quindi su **Abilita QoE**.

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Abilitazione di QoE usando i cmdlet di Windows PowerShell

Puoi abilitare QoE usando Windows PowerShell e il cmdlet **Set-CsQoEConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-enable-qoe-for-a-single-location"></a>Per abilitare QoE per una singola posizione

  - Per abilitare QoE, imposta il parametro EnableQoE su true ($True).
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a>Per disabilitare QoE per una singola posizione

  - Per disabilitare QoE, imposta il parametro EnableQoE su false ($False). Questo non disinstalla il monitoraggio. Sospende la raccolta e lo spazio di archiviazione dei dati QoE.
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>Per usare un singolo comando per abilitare QoE in più posizioni

  - Questo comando abilita QoE per tutte le impostazioni di configurazione QoE attualmente in uso nell'organizzazione.
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

Per informazioni dettagliate, vedere [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione del monitoraggio in Lync Server 2013](lync-server-2013-planning-for-monitoring.md)  
[Distribuzione del monitoraggio in Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

