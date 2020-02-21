---
title: "Lync Server 2013: abilitare o disabilitare l'accesso degli utenti remoti"
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
ms.openlocfilehash: b73381280b2d87ff73daa79162571f1f729086b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Gli utenti remoti sono utenti dell'organizzazione che dispongono di un'identità Active Directory permanente nell'organizzazione. Gli utenti remoti spesso accedono a Lync Server dall'esterno della rete utilizzando una rete privata virtuale (VPN, Virtual Private Network) quando non sono connessi alla rete dell'organizzazione. Tra gli utenti remoti sono inclusi i dipendenti che lavorano dalla propria abitazione o in viaggio e altri lavoratori remoti, ad esempio fornitori considerati attendibili a cui sono state concesse credenziali aziendali. Se si Abilita l'accesso utente remoto per gli utenti remoti, gli utenti remoti supportati si connettono su Internet e non devono connettersi utilizzando una VPN per collaborare con gli utenti interni utilizzando Lync Server.

Per supportare l'accesso degli utenti remoti, è necessario abilitarlo. Quando si abilita l'accesso degli utenti remoti, tale impostazione si applica all'intera organizzazione. Se successivamente si desidera impedire, in modo temporaneo o permanente, l'accesso degli utenti remoti, è possibile disabilitarlo per l'organizzazione. Attenersi alla procedura descritta in questa sezione per abilitare o disabilitare l'accesso degli utenti remoti per l'organizzazione.

<div>


> [!NOTE]  
> Abilitando l'accesso degli utenti remoti, si specifica soltanto che i server che eseguono il servizio Access Edge supportano le comunicazioni con gli utenti remoti, ma questi ultimi non possono utilizzare la messaggistica istantanea o partecipare a conferenze nell'organizzazione finché non si configura almeno un criterio per la gestione dell'utilizzo dell'accesso degli utenti remoti. Le impostazioni criteri di Lync Server applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Lync Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto. Per informazioni dettagliate sulla configurazione dei criteri per l'utilizzo dell'accesso degli utenti remoti, vedere <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to Control Remote User Access in Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Per abilitare o disabilitare l'accesso degli utenti remoti per l'organizzazione

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Configurazione Access Edge**.

4.  Nella pagina **Configurazione Access Edge** fare clic su **Globale**, **Modifica** e quindi su **Mostra dettagli**.

5.  In **Modifica configurazione Access Edge** eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti remoti per l'organizzazione, selezionare la casella di controllo **Abilita accesso remoto utenti**.
    
      - Per disabilitare l'accesso degli utenti remoti per l'organizzazione, deselezionare la casella di controllo **Abilita accesso remoto utenti**.

6.  Fare clic su **Commit**.

Per consentire agli utenti remoti di accedere ai server che eseguono Lync Server, è inoltre necessario configurare almeno un criterio di accesso esterno per supportare l'accesso degli utenti remoti. Per informazioni dettagliate, vedere [Configure policies to Control Remote User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione dell'accesso degli utenti remoti tramite i cmdlet di Windows PowerShell

È possibile gestire l'accesso degli utenti remoti tramite Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-enable-remote-user-access"></a>Per abilitare l'accesso degli utenti remoti

  - Per abilitare l'accesso degli utenti remoti, impostare il valore della proprietà **AllowOutsideUsers** su True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>Per disabilitare l'accesso degli utenti remoti

  - Per disabilitare l'accesso degli utenti remoti, impostare il valore della proprietà **AllowOutsideUsers** su False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

