---
title: "Lync Server 2013: Abilitare o disabilitare l'accesso degli utenti remoti"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 476cc3b90a2fdb603303789f3f9bfceb67766f5c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>Abilitare o disabilitare l'accesso degli utenti remoti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Gli utenti remoti sono utenti dell'organizzazione che hanno un'identità Active Directory persistente all'interno dell'organizzazione. Gli utenti remoti spesso accedono a Lync Server dall'esterno della rete usando una rete privata virtuale (VPN) quando non sono connessi alla rete dell'organizzazione. Gli utenti remoti includono dipendenti che lavorano a casa o in viaggio e altri lavoratori remoti, ad esempio fornitori attendibili, a cui sono state concesse le credenziali dell'organizzazione. Se si Abilita l'accesso utente remoto per gli utenti remoti, gli utenti remoti supportati si connettono tramite Internet e non devono connettersi tramite una VPN per collaborare con utenti interni tramite Lync Server.

Per supportare l'accesso degli utenti remoti, è necessario abilitare l'accesso degli utenti remoti. Quando si Abilita l'accesso remoto agli utenti, è possibile abilitarlo per l'intera organizzazione. Se in seguito si vuole impedire temporaneamente o definitivamente l'accesso degli utenti remoti, è possibile disabilitarlo per l'organizzazione. Usare la procedura descritta in questa sezione per abilitare o disabilitare l'accesso degli utenti remoti per l'organizzazione.

<div>


> [!NOTE]  
> L'abilitazione dell'accesso degli utenti remoti specifica solo che i server che gestiscono il servizio Access Edge supportano le comunicazioni con gli utenti remoti, ma gli utenti remoti non possono partecipare alla messaggistica istantanea o alle conferenze dell'organizzazione fino a quando non si configura anche in almeno un criterio per gestire l'uso dell'accesso degli utenti remoti. Le impostazioni dei criteri di Lync Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Lync Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza). Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto. Per informazioni dettagliate sulla configurazione dei criteri per l'uso dell'accesso remoto agli utenti, vedere <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">configurare i criteri per il controllo dell'accesso degli utenti remoti in Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Per abilitare o disabilitare l'accesso remoto agli utenti per l'organizzazione

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**e quindi su **configurazione bordo di Access**.

4.  Nella pagina **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **modifica configurazione di Access Edge**eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti remoti per l'organizzazione, selezionare la casella di controllo **Abilita accesso remoto agli utenti** .
    
      - Per disabilitare l'accesso degli utenti remoti per l'organizzazione, deselezionare la casella di controllo **Abilita accesso remoto agli utenti** .

6.  Fare clic su **Commit**.

Per consentire agli utenti remoti di accedere ai server che utilizzano Lync Server, è anche necessario configurare almeno un criterio di accesso esterno per supportare l'accesso degli utenti remoti. Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti remoti in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione dell'accesso degli utenti remoti tramite i cmdlet di Windows PowerShell

L'accesso degli utenti remoti può essere gestito tramite Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-enable-remote-user-access"></a>Per abilitare l'accesso remoto agli utenti

  - Per abilitare l'accesso remoto agli utenti, imposta il valore della proprietà **AllowOutsideUsers** su True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>Per disabilitare l'accesso remoto agli utenti

  - Per disabilitare l'accesso remoto agli utenti, imposta il valore della proprietà **AllowOutsideUsers** su False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

