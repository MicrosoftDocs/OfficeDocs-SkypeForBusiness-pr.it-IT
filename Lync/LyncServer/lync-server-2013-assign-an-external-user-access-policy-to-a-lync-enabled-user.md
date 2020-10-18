---
title: 'Lync Server 2013: assegnare un criterio di accesso utente esterno a un utente abilitato per Lync'
description: 'Lync Server 2013: assegnare un criterio di accesso utente esterno a un utente abilitato per Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2be3ea52e6e44400b3967d7c3346da2297220675
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573462"
---
# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>Assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

Se un utente è stato abilitato per Lync Server, è possibile configurare la federazione SIP, la Federazione XMPP, l'accesso degli utenti remoti e la connettività per la messaggistica istantanea pubblica nel pannello di controllo di Lync Server applicando i criteri corretti a utenti specifici. Ad esempio, se è stato creato un criterio per supportare l'accesso degli utenti remoti, è necessario applicarlo all'utente prima che l'utente possa connettersi a Lync Server da una posizione remota e collaborare con utenti interni dalla postazione remota.

<div>


> [!NOTE]  
> Per supportare l'accesso utente esterno, è necessario abilitare il supporto per ogni tipo di accesso utente esterno desiderato e configurare i criteri appropriati e altre opzioni per il controllo. Per ulteriori informazioni, vedere <A href="lync-server-2013-configuring-support-for-external-user-access.md">configurazione del supporto per l'accesso degli utenti esterni in Lync server 2013</A> nella documentazione relativa alla distribuzione o <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">gestione della Federazione e dell'accesso esterno a Lync Server 2013</A> nella documentazione relativa alle operazioni.



</div>

Utilizzare la procedura contenuta in questo argomento per applicare criteri di accesso utente esterno creati in precedenza a uno o più account utente.

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Per applicare criteri di accesso utente esterno a un account utente

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.

4.  Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, fare clic su **Modifica** e quindi su **Mostra dettagli**.

5.  In **Criteri di accesso esterno** in **Modifica utente di Lync Server** selezionare i criteri utente che si desidera applicare.
    
    <div>
    

    > [!NOTE]  
    > Le impostazioni <STRONG> &lt; automatiche &gt; </STRONG> applicano le impostazioni predefinite del server o dei criteri globali.

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Assegnazione di Per-User criteri di accesso esterno tramite i cmdlet di Windows PowerShell

I criteri di accesso esterno per utente possono essere assegnati utilizzando Windows PowerShell e il cmdlet Grant-CsExternalAccessPolicy. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Per assegnare un criterio di accesso esterno per utente a un singolo utente

  - Questo comando assegna il criterio di accesso esterno per utente RedmondExternalAccessPolicy all'utente Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Per assegnare criteri di accesso esterno per utente a più utenti

  - Questo comando assegna il criterio di accesso esterno per utente USAExternalAccessPolicy a tutti gli utenti che dispongono di account nell'unità organizzativa UnitedStates in Active Directory. Per ulteriori informazioni sul parametro OU utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>Per annullare l'assegnazione di un criterio di accesso esterno per utente

  - Questo comando annulla l'assegnazione di tutti i criteri di accesso esterno per utente precedentemente assegnati a Ken Myer. Dopo l'annullamento del criterio per utente, Ken Myer sarà gestito automaticamente dal criterio globale oppure dall'eventuale criterio del sito locale, che ha la precedenza sul criterio globale.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

