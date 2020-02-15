---
title: "Lync Server 2013: reimpostare i criteri globali per l'accesso degli utenti esterni"
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
ms.openlocfilehash: 91d6d1b9462d57b9b087baf0461c9cd0897bf1de
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a>Reimpostare i criteri globali per l'accesso degli utenti esterni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

Non è possibile eliminare completamente i criteri globali. Utilizzando l'opzione **Elimina** per i criteri globali vengono solo reimpostate le impostazioni predefinite dei criteri, che non includono il supporto per opzioni di accesso utente esterno.

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Per reimpostare le impostazioni predefinite dei criteri globali

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.

4.  Nella scheda **Criteri di accesso esterno** fare clic sui criteri globali, quindi su **Modifica** e infine su **Elimina**.

5.  Quando viene richiesto di confermare l'eliminazione, fare clic su **OK**. Verrà visualizzato un messaggio nella parte superiore della pagina che informa che i criteri globali sono stati reimpostati.

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Reimpostazione del criterio di accesso esterno globale mediante i cmdlet di Windows PowerShell

Il criterio di accesso esterno globale può essere reimpostato utilizzando Windows PowerShell e il cmdlet Remove-CsExternalAccessPolicy. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-reset-the-global-external-access-policy"></a>Per reimpostare il criterio di accesso esterno globale

  - Questo comando reimposta i criteri globali per l'accesso esterno
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

