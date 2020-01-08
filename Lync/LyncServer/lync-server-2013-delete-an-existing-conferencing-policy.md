---
title: 'Lync Server 2013: eliminare un criterio di conferenza esistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing conferencing policy
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49733688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3571c7b731579c0397da62d2c5805be19dcfa809
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-conferencing-policy-in-lync-server-2013"></a>Eliminare un criterio di conferenza esistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Seguire questa procedura per eliminare un criterio di conferenza a livello di utente o a livello di sito.

<div>


> [!NOTE]  
> Non è possibile eliminare i criteri di conferenza globale.



</div>

<div>

## <a name="to-delete-a-site-or-user-conferencing-policy"></a>Per eliminare un criterio di conferenza per un sito o un utente

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su servizi di **conferenza** e quindi su **criteri di conferenza**.

4.  Nell'elenco dei criteri di conferenza fare clic sul sito o sui criteri utente da eliminare, fare clic su **modifica**e quindi su **Elimina**.

</div>

<div>

## <a name="removing-conferencing-policies-by-using-windows-powershell-cmdlets"></a>Rimozione dei criteri di conferenza tramite i cmdlet di Windows PowerShell

È possibile eliminare i criteri di conferenza tramite Lync Server Management Shell e il cmdlet **Remove-CsConferencingPolicy** . Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-remove-a-specified-conferencing-policy"></a>Per rimuovere un criterio di conferenza specificato

  - Il comando seguente rimuove i criteri di conferenza con Identity RedmondConferencingPolicy:
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-policies-applied-to-the-per-user-scope"></a>Per rimuovere tutti i criteri di conferenza applicati all'ambito per utente

  - Il comando seguente rimuove tutti i criteri di conferenza configurati nell'ambito per utente:
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-polices-that-allow-recording-by-external-users"></a>Per rimuovere tutti i criteri di conferenza che consentono la registrazione da parte di utenti esterni

  - Il comando seguente elimina qualsiasi criterio di conferenza che consente agli utenti esterni di registrare la conferenza:
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

</div>

Per informazioni dettagliate, vedere [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy).

</div>

</div>

<span> </span>

</div>

</div>

</div>

