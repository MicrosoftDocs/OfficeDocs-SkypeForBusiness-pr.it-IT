---
title: "Lync Server 2013: Abilitare o disabilitare l'accesso degli utenti anonimi"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d07bf27f5424f121c5dcf070f5231e2fd8c324f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a>Abilitare o disabilitare l'accesso degli utenti anonimi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Gli utenti anonimi sono utenti che non dispongono di un account utente nei servizi di dominio Active Directory dell'organizzazione o in un dominio federato supportato, ma possono essere invitati a partecipare in remoto in una conferenza locale. Consentendo la partecipazione anonima alle riunioni, è possibile abilitare gli utenti anonimi, ovvero gli utenti la cui identità viene verificata solo tramite la riunione o la chiave di conferenza, per partecipare alle riunioni. Per consentire la partecipazione anonima, è necessario abilitarla per l'organizzazione.

Se in seguito si vuole impedire temporaneamente o definitivamente l'accesso da parte di utenti anonimi, è possibile disabilitarlo per l'organizzazione. Usare la procedura descritta in questa sezione per abilitare o disabilitare l'accesso degli utenti anonimi per l'organizzazione.

<div>


> [!NOTE]  
> Abilitando l'accesso degli utenti anonimi per l'organizzazione, devi solo specificare che i server che esegue il servizio Access Edge supportano l'accesso da parte di utenti anonimi. Gli utenti anonimi non possono partecipare a riunioni dell'organizzazione fino a quando non vengono configurati almeno un criterio di conferenza e lo si applicano a uno o più utenti o gruppi di utente. Gli unici utenti che possono invitare utenti anonimi alle riunioni sono gli utenti a cui sono assegnati i criteri di conferenza configurati per il supporto degli utenti anonimi. Per informazioni dettagliate sulla configurazione dei criteri di conferenza per il supporto dell'invito agli utenti anonimi, vedere <A href="lync-server-2013-conferencing-policies.md">criteri di conferenza in Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Per abilitare o disabilitare l'accesso degli utenti anonimi per l'organizzazione

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **configurazione bordo di Access**.

4.  Nella pagina **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **modifica configurazione di Access Edge**eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti anonimi per l'organizzazione, selezionare la casella di controllo **Abilita comunicazioni con utenti anonimi** .
    
      - Per disabilitare l'accesso degli utenti anonimi per l'organizzazione, deselezionare la casella di controllo **Abilita comunicazioni con utenti anonimi** .

6.  Fare clic su **Commit**.

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione dell'accesso degli utenti anonimi tramite i cmdlet di Windows PowerShell

Per gestire l'accesso degli utenti anonimi, è possibile usare Windows PowerShell e il cmdlet **Set-CsAccessEdgeConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-enable-anonymous-user-access"></a>Per abilitare l'accesso degli utenti anonimi

  - Per abilitare l'accesso degli utenti anonimi, imposta il valore della proprietà **AllowAnonymousUsers** su True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a>Per disabilitare l'accesso degli utenti anonimi

  - Per disabilitare l'accesso anonimo agli utenti, imposta il valore della proprietà **AllowAnonymousUsers** su False ($false):
    
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

