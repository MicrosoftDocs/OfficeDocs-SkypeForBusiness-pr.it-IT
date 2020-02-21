---
title: 'Lync Server 2013: eliminazione di una configurazione di archiviazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b864bb96ea7d342dbfd449cc9a151b0d7c2dee6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a>Eliminazione di una configurazione di archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

È possibile eliminare la configurazione di un sito o la configurazione di un pool. La configurazione globale non può essere rimossa. Se si elimina la configurazione globale, viene reimpostata automaticamente sui valori predefiniti. Per informazioni dettagliate sulla modalità di implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a>Per eliminare la configurazione di un sito o di un pool per l'archiviazione

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.

4.  Nell'elenco delle configurazioni di archiviazione fare clic sulla configurazione di sito o di pool che si desidera eliminare, fare clic su **Modifica** e quindi su **Elimina**.

5.  Fare clic su **Commit**.

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione delle impostazioni di configurazione dell'archiviazione tramite i cmdlet di Windows PowerShell

È possibile eliminare le impostazioni di configurazione dell'archiviazione utilizzando Windows PowerShell e il cmdlet **Remove-CsArchivingConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a>Per rimuovere una raccolta specificata di impostazioni di configurazione di archiviazione

  - Il comando seguente rimuove le impostazioni della configurazione di archiviazione applicate al sito Redmond:
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a>Per rimuovere tutte le impostazioni di configurazione di archiviazione applicate all'ambito del sito

  - Questo comando rimuove tutte le impostazioni della configurazione di archiviazione applicate all'ambito del servizio:
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a>Per rimuovere le impostazioni di configurazione dell'archiviazione in base a un valore della proprietà specificato

  - Questo comando rimuove tutte le impostazioni della configurazione di archiviazione in cui l'archiviazione di Exchange è stata disabilitata:
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Funzionamento dell'archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

