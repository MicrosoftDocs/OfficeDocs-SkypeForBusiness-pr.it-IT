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
ms.openlocfilehash: 1528ef6124193023a0e5938caac7b40c2c6187a2
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943929"
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
    > Le impostazioni <STRONG> &lt; automatiche &gt; </STRONG> applicano le impostazioni predefinite del server o dei criteri globali.



## <a name="assign-per-user-voice-policies"></a>Assegnare criteri vocali per utente

È possibile assegnare criteri vocali per utente tramite Windows PowerShell e il cmdlet **Grant-CsVoicePolicy** . È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per ulteriori informazioni sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere il post del Blog di Windows PowerShell di Lync Server: [Quick Start: Managing Microsoft Lync server 2010 using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).

### <a name="assign-a-per-user-voice-policy-to-a-single-user"></a>Assegnare un criterio vocale per utente a un singolo utente

  - Il comando seguente assegna il criterio vocale per utente RedmondVoicePolicy all'utente Ken Myer.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="assign-a-per-user-voice-policy-to-multiple-users"></a>Assegnazione di un criterio vocale per utente a più utenti

  - Questo comando assegnare il criterio vocale per utente FinanceVoicePolicy a tutti gli utenti con account nell'unità organizzativa Finance in Active Directory. Per ulteriori informazioni sul parametro OU utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="unassign-a-per-user-voice-policy"></a>Annullamento dell'assegnazione di un criterio vocale per utente

  - Il comando seguente annulla l'assegnazione di qualsiasi criterio vocale per utente precedentemente assegnato a Ken Myer. Dopo aver annullato l'assegnazione del criterio vocale per utente, Ken Myer verrà automaticamente gestito mediante i criteri globali oppure, se esistente, i criteri a livello di sito locale. I criteri a livello di sito hanno precedenza sui criteri globali.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) .

## <a name="see-also"></a>Vedere anche


[Disabilitare un utente per VoIP aziendale in Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)

