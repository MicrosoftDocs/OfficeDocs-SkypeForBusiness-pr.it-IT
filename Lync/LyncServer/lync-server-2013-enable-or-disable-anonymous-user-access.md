---
title: "Lync Server 2013: abilitare o disabilitare l'accesso degli utenti anonimi"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d78569770f136244e3ddd5e7f9fa2f02ca3d8e6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a>Abilitazione o disabilitazione dell'accesso degli utenti anonimi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Gli utenti anonimi sono utenti che non dispongono di un account utente nei servizi di dominio Active Directory dell'organizzazione o in un dominio federato supportato, ma possono essere invitati a partecipare in remoto in una conferenza locale. Consentendo la partecipazione anonima alle riunioni, si consente agli utenti anonimi, ovvero agli utenti la cui identità viene verificata solo mediante la chiave riunione o conferenza, di partecipare alle riunioni. A tale scopo, è necessario abilitare la partecipazione anonima per la propria organizzazione.

Se successivamente si desidera impedire temporaneamente o definitivamente l'accesso da parte di utenti anonimi, è possibile disabilitarlo per l'organizzazione. Eseguire la procedura illustrata in questa sezione per abilitare o disabilitare l'accesso utente anonimo per la propria organizzazione.

<div>


> [!NOTE]  
> Abilitando l'accesso utente anonimo per l'organizzazione, si specifica solo che i server che eseguono il servizio Access Edge supportano l'accesso da parte di utenti anonimi. Tali utenti non possono partecipare alle riunioni dell'organizzazione finché non viene configurato e applicato almeno un criterio di conferenza a uno o più utenti o gruppi di utenti. Gli unici utenti che possono invitare utenti anonimi alle riunioni sono quelli a cui è stato assegnato il criterio di conferenza configurato per supportare l'invito di utenti anonimi. Per informazioni dettagliate sulla configurazione dei criteri di conferenza per supportare l'invito degli utenti anonimi, vedere <A href="lync-server-2013-conferencing-policies.md">Conferencing Policies in Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Per abilitare o disabilitare l'accesso utente anonimo per l'organizzazione

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Configurazione Access Edge**.

4.  Nella pagina **Configurazione Access Edge** fare clic su **Globale**, **Modifica** e quindi su **Mostra dettagli**.

5.  In **Modifica configurazione Access Edge** eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso utente anonimo per l'organizzazione, selezionare la casella di controllo **Abilita comunicazioni con utenti anonimi**.
    
      - Per disabilitare l'accesso utente anonimo per l'organizzazione, deselezionare la casella di controllo **Abilita comunicazioni con utenti anonimi**.

6.  Fare clic su **Commit**.

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione dell'accesso degli utenti anonimi tramite i cmdlet di Windows PowerShell

È possibile gestire l'accesso degli utenti anonimi utilizzando Windows PowerShell e il cmdlet **Set-CsAccessEdgeConfiguration** . È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-enable-anonymous-user-access"></a>Per abilitare l'accesso degli utenti anonimi

  - Per abilitare l'accesso utente anonimo, impostare il valore della proprietà **AllowAnonymousUsers** su True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a>Per disabilitare l'accesso degli utenti anonimi

  - Per disabilitare l'accesso utente anonimo, impostare il valore della proprietà **AllowAnonymousUsers** su False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Informazioni di riferimento sulle impostazioni dei criteri di conferenza per Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

