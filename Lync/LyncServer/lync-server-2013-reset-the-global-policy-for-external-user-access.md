---
title: "Lync Server 2013: Reimpostare i criteri globali per l'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 971239018f3a8e1bcc92c036f50ed36616256ac7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a>Reimpostare i criteri globali per l'accesso degli utenti esterni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

Non è possibile eliminare completamente un criterio globale. L'uso dell'opzione **Elimina** nel criterio globale reimposta solo il criterio globale sulle impostazioni predefinite, che non includono il supporto per le opzioni di accesso degli utenti esterni.

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Per reimpostare il criterio globale sulle impostazioni predefinite

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**, fare clic su **criteri di accesso esterno**.

4.  Nella scheda **criteri di accesso esterno** fare clic sul criterio globale, scegliere **modifica**e quindi fare clic su **Elimina**.

5.  Quando viene richiesto di confermare l'eliminazione, fare clic su **OK**. Nella parte superiore della pagina viene visualizzato un messaggio che informa che il criterio globale è stato reimpostato.

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Reimpostazione del criterio di accesso esterno globale con i cmdlet di Windows PowerShell

Il criterio di accesso esterno globale può essere reimpostato tramite Windows PowerShell e il cmdlet Remove-CsExternalAccessPolicy. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-reset-the-global-external-access-policy"></a>Per reimpostare i criteri di accesso esterno globale

  - Questo comando Reimposta il criterio di accesso esterno globale:
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

