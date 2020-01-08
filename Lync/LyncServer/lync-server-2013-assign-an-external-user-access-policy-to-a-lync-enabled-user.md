---
title: 'Lync Server 2013: Assegnare criteri di accesso per gli utenti esterni a un utente abilitato per Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec487f8aacdc26f910f30a0864ecead1fdb1a745
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>Assegnare criteri di accesso per gli utenti esterni a un utente abilitato per Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

Se un utente è stato abilitato per Lync Server, è possibile configurare la federazione SIP, la Federazione XMPP, l'accesso degli utenti remoti e la connettività messaggistica istantanea pubblica nel pannello di controllo di Lync Server applicando i criteri appropriati a utenti specifici. Se ad esempio è stato creato un criterio per supportare l'accesso degli utenti remoti, è necessario applicarlo all'utente prima che l'utente possa connettersi a Lync Server da una posizione remota e collaborare con utenti interni dalla posizione remota.

<div>


> [!NOTE]  
> Per supportare l'accesso degli utenti esterni, è necessario abilitare il supporto per ogni tipo di accesso utente esterno che si vuole supportare e configurare i criteri appropriati e altre opzioni per controllarne l'utilizzo. Per informazioni dettagliate, vedere <A href="lync-server-2013-configuring-support-for-external-user-access.md">configurazione del supporto per l'accesso degli utenti esterni in Lync server 2013</A> nella documentazione di distribuzione o <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">gestione della Federazione e accesso esterno a Lync Server 2013</A> nella documentazione delle operazioni.



</div>

Usare la procedura descritta in questo argomento per applicare un criterio di accesso utente esterno creato in precedenza a uno o più account utente.

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Per applicare un criterio utente esterno a un account utente

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.

4.  Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.

5.  In **modifica utenti di Lync Server** in **criteri di accesso esterno**Selezionare i criteri utente che si desidera applicare.
    
    <div>
    

    > [!NOTE]  
    > Le <STRONG> &lt;impostazioni&gt; automatiche</STRONG> applicano le impostazioni predefinite del server o dei criteri globali.

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Assegnazione di criteri di accesso esterno per utente tramite i cmdlet di Windows PowerShell

I criteri di accesso esterno per utente possono essere assegnati tramite Windows PowerShell e il cmdlet Grant-CsExternalAccessPolicy. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Per assegnare un criterio di accesso esterno per utente a un singolo utente

  - Questo comando assegna il criterio di accesso esterno per utente RedmondExternalAccessPolicy all'utente Ken.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Per assegnare un criterio di accesso esterno per utente a più utenti

  - Questo comando assegna il criterio di accesso esterno per utente USAExternalAccessPolicy a tutti gli utenti che hanno account nell'UO degli Stati Uniti in Active Directory. Per altre informazioni sul parametro OU usato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>Per annullare l'assegnazione di un criterio di accesso esterno per utente

  - Questo comando Annulla l'assegnazione di qualsiasi criterio di accesso esterno per utente assegnato in precedenza a Ken. Dopo che il criterio per utente non è stato assegnato, Ken è gestito automaticamente tramite il criterio globale oppure, se disponibile, il criterio del sito locale. Un criterio di sito ha la precedenza sui criteri globali.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

