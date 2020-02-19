---
title: 'Lync Server 2013: assegnare un criterio vocale per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6a10e2fb6d8e17352eb8a96be57b24e706fc5d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134392"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a>Assegnare un criterio vocale per utente in Lync Server 2013

 


I criteri vocali globali e a livello di sito vengono assegnati automaticamente a tutti gli account utente di Lync Server 2013 abilitati per VoIP aziendale. È inoltre possibile assegnare criteri vocali a utenti specifici utilizzando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell. Utilizzare le procedure descritte in questo argomento per assegnare in modo esplicito i criteri per utente agli utenti di Lync Server.

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a>Per assegnare un criterio vocale specifico dell'utente utilizzando il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.

4.  Nella tabella in cui sono elencati i risultati di ricerca, fare clic sull'account utente, scegliere **Modifica** e quindi **Mostra dettagli**.

5.  In **Modifica utente di Lync Server**, in **Criteri vocali**, selezionare i criteri utente da applicare.
    

    > [!NOTE]  
    > Le <STRONG> &lt;impostazioni&gt; automatiche</STRONG> applicano le impostazioni predefinite del server o dei criteri globali.



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a>Assegnazione di un criterio vocale per utente tramite i cmdlet di Windows PowerShell

È possibile assegnare criteri vocali per utente tramite Windows PowerShell e il cmdlet **Grant-CsVoicePolicy** . È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a>Per assegnare un criterio vocale per utente a un singolo utente

  - Il comando seguente assegna il criterio vocale per utente RedmondVoicePolicy all'utente Ken Myer.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a>Per assegnare criteri vocali per utente a più utenti

  - Questo comando assegnare il criterio vocale per utente FinanceVoicePolicy a tutti gli utenti con account nell'unità organizzativa Finance in Active Directory. Per ulteriori informazioni sul parametro OU utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a>Per annullare l'assegnazione di un criterio vocale per utente

  - Il comando seguente annulla l'assegnazione di qualsiasi criterio vocale per utente precedentemente assegnato a Ken Myer. Dopo aver annullato l'assegnazione del criterio vocale per utente, Ken Myer verrà automaticamente gestito mediante i criteri globali oppure, se esistente, i criteri a livello di sito locale. I criteri a livello di sito hanno precedenza sui criteri globali.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) .

## <a name="see-also"></a>Vedere anche


[Disabilitare un utente per VoIP aziendale in Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)

