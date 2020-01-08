---
title: 'Lync Server 2013: assegnare un criterio di mobilità per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e79a9b76ac4774bbbac7772bef19902d6d70f15a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980808"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a>Assegnare un criterio di mobilità per utente in Lync Server 2013

 


I criteri di mobilità sono una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server o in Lync Server Management Shell.

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a>Per assegnare un criterio di mobilità per utente con il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **utenti**.

4.  Usare uno dei metodi seguenti per individuare un utente:
    
      - Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente e quindi fare clic su **trova**.
    
      - Se si ha una query salvata, fare clic sull'icona **Apri query** , usare la finestra di dialogo **Apri** per recuperare la query (un file con estensione USF) e quindi fare clic su **trova**.

5.  Opzionale Specificare altri criteri di ricerca per restringere i risultati:
    
    1.  Fare clic su **Aggiungi filtro**.
    
    2.  Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare la proprietà.
    
    3.  Nell'elenco **a discesa uguale a** fare clic sull'operatore, ad esempio **uguale** a o diverso **da**.
    
    4.  A seconda della proprietà utente selezionata, immettere i criteri da usare per filtrare i risultati della ricerca digitando o facendo clic sulla freccia nell'elenco a discesa.
        

        > [!TIP]  
        > Per aggiungere altre clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.

    
    5.  Fare clic su **trova**.

6.  Fare clic su un utente nei risultati della ricerca, fare clic su **azione**e quindi su **Assegna criteri**.
    

    > [!TIP]  
    > Se si vuole che gli stessi criteri di mobilità per utente vengano applicati a più utenti, selezionare più utenti nei risultati della ricerca, quindi fare clic su <STRONG>azioni</STRONG>e quindi su <STRONG>Assegna criteri</STRONG>.



7.  In **Assegna criteri**, in **criteri di mobilità**, eseguire una delle operazioni seguenti:
    

    > [!NOTE]  
    > Poiché esistono più criteri <STRONG> &lt;che è possibile&gt; </STRONG> configurare in <STRONG>Assegna criteri</STRONG>, è selezionata per impostazione predefinita per ogni criterio nella finestra di dialogo. Continuare a usare il criterio precedentemente assegnato all'utente senza apportare alcuna modifica a questa impostazione.

    
      - Selezionare ** \<automatico\> ** per consentire a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.
    
      - Fare clic sul nome di un criterio di mobilità per utente definito in precedenza nella pagina dei **criteri di mobilità** .
        

        > [!TIP]  
        > Per decidere i criteri da assegnare, fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definiti nel criterio dopo aver fatto clic su un nome di criterio.



8.  Al termine, fare clic su **OK**.

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a>Assegnazione di un criterio di mobilità per utente tramite i cmdlet di Windows PowerShell

È possibile assegnare criteri di mobilità per utente tramite Windows PowerShell e il cmdlet **Grant-CsMobilityPolicy** . Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a>Per assegnare un criterio di mobilità per utente a un singolo utente

  - Con il comando seguente viene assegnato il criterio di mobilità per utente RedmondMobilityPolicy all'utente Ken.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a>Per assegnare un criterio di mobilità per utente a più utenti

  - Con il comando seguente viene assegnato il criterio di mobilità per utente RedmondMobilityPolicy a tutti gli utenti a cui è attualmente assegnato il criterio NorthAmericaMobilityPolicy. Per informazioni dettagliate sul parametro Filter usato in questo comando, vedere [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a>Per annullare l'assegnazione di un criterio di mobilità per utente

  - Il comando seguente annulla l'assegnazione di criteri di mobilità per utente assegnati in precedenza a Ken. Dopo che il criterio per utente non è stato assegnato, Ken è gestito automaticamente tramite il criterio globale oppure, se disponibile, il criterio del sito locale. Un criterio di sito ha la precedenza sui criteri globali.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

Per informazioni dettagliate, vedere [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/hh690038\(v=ocs.15\)).

## <a name="see-also"></a>Vedere anche


[Configurazione dei criteri per dispositivi mobili in Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)

