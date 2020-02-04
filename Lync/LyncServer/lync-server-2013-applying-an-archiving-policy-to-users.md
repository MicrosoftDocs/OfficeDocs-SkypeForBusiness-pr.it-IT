---
title: 'Lync Server 2013: applicazione di un criterio di archiviazione agli utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d1cf0db76b888b9774a16f7a6353ccf1b399eb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>Applicazione di criteri di archiviazione agli utenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Se un utente è stato abilitato per Lync Server 2013 ed è stato creato uno o più criteri utente per l'archiviazione per gli utenti ospitati in Lync Server 2013, è possibile implementare il supporto dell'archiviazione per utenti specifici applicando i criteri appropriati per gli utenti o i gruppi utente. Se ad esempio si crea un criterio per supportare l'archiviazione delle comunicazioni interne, è possibile applicarlo ad almeno un utente o un gruppo di utenti per supportare l'archiviazione delle comunicazioni di Lync Server 2013 dell'utente.

<div>


> [!NOTE]  
> Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di blocco sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013 e le cassette postali vengono messe sul posto. Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurazione dei criteri per l'archiviazione in Lync server 2013 quando si usa l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.<BR>Devi specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool</A> nella documentazione Operations.



</div>

Usare la procedura descritta in questo argomento per applicare un criterio utente di archiviazione creato in precedenza a uno o più account utente o gruppi di utenti.

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>Per applicare un criterio utente di archiviazione a un account utente

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **utenti**e quindi cercare l'account utente che si vuole configurare.

4.  Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.

5.  In **modifica utenti di Lync Server** in **criteri di archiviazione**Selezionare i criteri utente di archiviazione che si desidera applicare.
    
    <div>
    

    > [!NOTE]  
    > Le <STRONG> &lt;impostazioni&gt; automatiche</STRONG> applicano le impostazioni di installazione del server predefinite. Queste impostazioni vengono applicate automaticamente dal server.

    
    </div>

6.  Fare clic su **Commit**.

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Assegnazione di un criterio di archiviazione per utente tramite i cmdlet di Windows PowerShell

I criteri di archiviazione per utente possono essere assegnati tramite Windows PowerShell e il cmdlet **Grant-CsArchivingPolicy** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>Per assegnare un criterio di archiviazione per utente a un singolo utente

  - Con il comando seguente viene assegnato il criterio di archiviazione per utente RedmondArchivingPolicy all'utente Ken.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>Per assegnare criteri di archiviazione per utente a più utenti

  - Questo comando assegna il criterio di archiviazione per utente RedmondArchivingPolicy a tutti gli utenti che hanno account assegnati nel pool di registrazione atl-cs-001.litwareinc.com. Per informazioni dettagliate sul parametro Filter usato in questo comando, vedere la documentazione del cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>Per assegnare un criterio di archiviazione per utente

  - Il comando seguente annulla l'assegnazione di criteri di archiviazione per utente assegnati in precedenza a Ken. Dopo che il criterio per utente non è stato assegnato, Ken è gestito automaticamente tramite il criterio globale oppure, se disponibile, il criterio del sito locale. Un criterio di sito ha la precedenza sui criteri globali.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Per informazioni dettagliate, vedere la documentazione del cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[Assegnazione di criteri per utente in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

