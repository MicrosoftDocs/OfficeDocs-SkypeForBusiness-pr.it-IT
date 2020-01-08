---
title: 'Lync Server 2013: assegnare un criterio vocale per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e74bebc202a9e8d9fbc7b925c14bbe030e4c577
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975990"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a>Assegnare un criterio vocale per utente in Lync Server 2013

 


I criteri vocali globali e a livello di sito vengono assegnati automaticamente a tutti gli account utente di Lync Server 2013 abilitati per VoIP aziendale. È anche possibile assegnare criteri vocali a utenti specifici tramite il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell. Usare le procedure descritte in questo argomento per assegnare esplicitamente i criteri per utente agli utenti di Lync Server.

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a>Per assegnare un criterio vocale specifico dell'utente tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.

4.  Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.

5.  In **modifica utenti di Lync Server** in **criteri vocali**Selezionare il criterio utente che si desidera applicare.
    

    > [!NOTE]  
    > Le <STRONG> &lt;impostazioni&gt; automatiche</STRONG> applicano le impostazioni predefinite del server o dei criteri globali.



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a>Assegnazione di un criterio vocale per utente tramite i cmdlet di Windows PowerShell

È possibile assegnare criteri vocali per utente tramite Windows PowerShell e il cmdlet **Grant-CsVoicePolicy** . Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a>Per assegnare un criterio vocale per utente a un singolo utente

  - Con il comando seguente viene assegnato il criterio vocale per utente RedmondVoicePolicy all'utente Ken.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a>Per assegnare un criterio vocale per utente a più utenti

  - Questo comando assegna il criterio vocale per utente FinanceVoicePolicy a tutti gli utenti che hanno account nell'unità organizzativa Finanza in Active Directory. Per altre informazioni sul parametro OU usato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a>Per annullare l'assegnazione di un criterio vocale per utente

  - Il comando seguente annulla l'assegnazione di qualsiasi criterio vocale per utente assegnato in precedenza a Ken. Dopo che il criterio per utente non è stato assegnato, Ken è gestito automaticamente tramite il criterio globale oppure, se disponibile, il criterio del sito locale. Un criterio di sito ha la precedenza sui criteri globali.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) .

## <a name="see-also"></a>Vedere anche


[Disabilitare un utente per VoIP aziendale in Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)

