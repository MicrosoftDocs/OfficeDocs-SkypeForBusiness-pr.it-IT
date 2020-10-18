---
title: 'Lync Server 2013: eliminazione di un criterio di archiviazione'
description: 'Lync Server 2013: eliminazione di un criterio di archiviazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecf465a62cf8f54777b03a1634d9a95f1b565c9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575802"
---
# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a>Eliminazione di un criterio di archiviazione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

È possibile eliminare un criterio utente o un criterio sito. Non è possibile rimuovere i criteri globali. Se si tenta di eliminare il criterio globale, Lync Server 2013 Reimposta automaticamente il criterio sui valori predefiniti.

<div>


> [!NOTE]  
> Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013 e le relative cassette postali vengono inserite In-Place. Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">impostazione dei criteri per l'archiviazione in Lync server 2013 quando si utilizza l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a>Per eliminare un criterio utente o sito per l'archiviazione

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.

4.  Nell'elenco dei criteri di archiviazione fare clic sul criterio utente o sito che si desidera eliminare, su **Modifica** e quindi su **Elimina**.

5.  Fare clic su **Commit**.

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a>Rimozione dei criteri di archiviazione tramite i cmdlet di Windows PowerShell

I criteri di archiviazione possono essere eliminati utilizzando Windows PowerShell e il cmdlet **Remove-CsArchivingPolicy** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specified-archiving-policy"></a>Per rimuovere un criterio di archiviazione specificato

  - Ad esempio,**Remove-CsArchivingPolicy** elimina il criterio con identità site:Redmond. Si noti che, quando viene eliminato un criterio configurato nell'ambito del sito, gli utenti precedentemente gestiti da quel criterio verranno automaticamente controllati dal criterio di archiviazione globale. Il comando seguente rimuove l'archiviazione applicata al sito Redmond:
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a>Per rimuovere tutti i criteri di archiviazione applicati all'ambito per utente

  - Questo comando rimuove tutti i criteri di archiviazione applicati all'ambito per utente:
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a>Per rimuovere tutti i criteri di archiviazione che disabilitano l'archiviazione interna

  - Questo comando rimuove tutti i criteri di archiviazione in cui è stata disabilitata l'archiviazione interna:
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

