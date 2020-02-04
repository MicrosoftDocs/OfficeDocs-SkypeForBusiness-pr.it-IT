---
title: "Lync Server 2013: Eliminare criteri di sito o utente per l'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b928fcb1347fdbc89099a5b0dc649deefffa19e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a>Eliminare criteri di sito o utente per l'accesso degli utenti esterni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

È possibile eliminare qualsiasi criterio di sito o utente elencato nel pannello di controllo di Lync Server nella pagina dei **criteri di accesso esterno** . L'eliminazione del criterio globale in realtà non lo elimina, ma lo reimposta solo sulle impostazioni predefinite, che non includono il supporto per le opzioni di accesso degli utenti esterni. Per informazioni dettagliate su come reimpostare il criterio globale, vedere [reimpostare il criterio globale per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Per eliminare un sito o un criterio utente per l'accesso degli utenti esterni

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Fare clic su **accesso utente esterno**, fare clic su **criteri di accesso esterno**.

4.  Nella scheda **criteri di accesso esterno** fare clic sul sito o sui criteri degli utenti da eliminare, fare clic su **modifica**e quindi su **Elimina**.

5.  Quando viene richiesto di confermare l'eliminazione, fare clic su **OK**.

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Rimozione dei criteri PIN tramite i cmdlet di Windows PowerShell

I criteri di accesso esterno possono essere eliminati tramite Windows PowerShell e il cmdlet Remove-CsExternalAccessPolicy. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-remove-a-specific-external-access-policy"></a>Per rimuovere un criterio di accesso esterno specifico

  - Questo comando rimuove il criterio di accesso esterno applicato al sito Redmond:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Per rimuovere tutti i criteri di accesso esterno applicati all'ambito per utente

  - Questo comando rimuove tutti i criteri di accesso esterno configurati nell'ambito per utente:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Per rimuovere tutti i criteri di accesso esterno in cui l'utente esterno è disabilitato

  - Questo comando Elimina tutti i criteri di accesso esterno in cui l'accesso esterno dell'utente è stato disabilitato:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

