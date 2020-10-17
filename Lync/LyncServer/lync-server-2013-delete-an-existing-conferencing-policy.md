---
title: 'Lync Server 2013: eliminare un criterio di conferenza esistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing conferencing policy
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49733688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29d8801c8ee58a65a60495789fdca66d16ce0c66
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514623"
---
# <a name="delete-an-existing-conferencing-policy-in-lync-server-2013"></a>Eliminare un criterio di conferenza esistente in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Eseguire questa procedura per eliminare un criterio di conferenza a livello di utente o di sito.

<div>


> [!NOTE]  
> Non è possibile eliminare il criterio di conferenza globale.



</div>

<div>

## <a name="to-delete-a-site-or-user-conferencing-policy"></a>Per eliminare un criterio di conferenza a livello di utente o di sito

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri conferenza**.

4.  Nell'elenco dei criteri conferenza fare clic sul criterio sito o utente che si desidera eliminare, fare clic su **modifica**e quindi su **Elimina**.

</div>

<div>

## <a name="removing-conferencing-policies-by-using-windows-powershell-cmdlets"></a>Rimozione dei criteri di conferenza tramite i cmdlet di Windows PowerShell

È possibile eliminare i criteri di conferenza utilizzando Lync Server Management Shell e il cmdlet **Remove-CsConferencingPolicy** . È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specified-conferencing-policy"></a>Per rimuovere un criterio di conferenza specifico.

  - Il comando seguente rimuove il criterio di conferenza con identità (Identity) RedmondConferencingPolicy.
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-policies-applied-to-the-per-user-scope"></a>Per rimuovere tutti i criteri di conferenza applicati all'ambito "per utente"

  - Questo comando rimuove tutti i criteri di conferenza configurati nell'ambito "per utente":
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-polices-that-allow-recording-by-external-users"></a>Per rimuovere tutti i criteri di conferenza che consentono la registrazione da parte degli utenti esterni

  - Questo comando rimuove tutti i criteri di conferenza configurati che consentono la registrazione da parte degli utenti esterni:
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

</div>

Per informazioni dettagliate, vedere [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy).

</div>

</div>

<span> </span>

</div>

</div>

</div>

