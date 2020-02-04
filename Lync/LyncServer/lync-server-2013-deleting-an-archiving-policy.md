---
title: 'Lync Server 2013: eliminazione di un criterio di archiviazione'
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
ms.openlocfilehash: 926cc7e45fe3e57c189b01ff92da49342506dc2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a>Eliminazione di un criterio di archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Puoi eliminare un criterio utente o un criterio del sito. Il criterio globale non può essere rimosso. Se si tenta di eliminare il criterio globale, Lync Server 2013 Reimposta automaticamente i criteri sui valori predefiniti.

<div>


> [!NOTE]  
> Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013 e le cassette postali vengono inserite. Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurazione dei criteri per l'archiviazione in Lync server 2013 quando si usa l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a>Per eliminare un criterio utente o del sito per l'archiviazione

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.

4.  Nell'elenco dei criteri di archiviazione fare clic sul criterio dell'utente o del sito che si desidera eliminare, fare clic su **modifica**e quindi su **Elimina**.

5.  Fare clic su **Commit**.

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a>Rimozione dei criteri di archiviazione tramite i cmdlet di Windows PowerShell

I criteri di archiviazione possono essere eliminati tramite Windows PowerShell e il cmdlet **Remove-CsArchivingPolicy** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-remove-a-specified-archiving-policy"></a>Per rimuovere un criterio di archiviazione specificato

  - Ad esempio, **Remove-CsArchivingPolicy** Elimina il criterio con il sito Identity: Redmond. Tieni presente che quando un criterio configurato nell'ambito del sito viene eliminato, gli utenti gestiti in precedenza dal criterio del sito verranno regolati automaticamente dal criterio di archiviazione globale. Con il comando seguente viene rimossa l'archiviazione applicata al sito Redmond:
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a>Per rimuovere tutti i criteri di archiviazione applicati all'ambito per utente

  - Questo comando rimuove tutti i criteri di archiviazione applicati all'ambito per utente:
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a>Per rimuovere tutti i criteri di archiviazione che disabilitano l'archiviazione interna

  - Questo comando rimuove tutti i criteri di archiviazione in cui l'archiviazione interna è stata disattivata:
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) .

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

