---
title: 'Lync Server 2013: assegnare un criterio per dispositivi mobili per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1014bce74e0e7dcd789c9b2948c029f4b40ecb9a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030139"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a>Assegnare un criterio per dispositivi mobili per utente in Lync Server 2013

 


I criteri per dispositivi mobili sono una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server o in Lync Server Management Shell.

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a>Per assegnare criteri dispositivi mobili per utente con il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Utenti**.

4.  Utilizzare uno dei metodi seguenti per individuare un utente:
    
      - Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.
    
      - Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.

5.  (Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:
    
    1.  Fare clic su **Aggiungi filtro**.
    
    2.  Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.
    
    3.  Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Non uguale a**).
    
    4.  A seconda della proprietà utente selezionata, immettere i criteri da utilizzare per filtrare i risultati della ricerca digitandoli o facendo clic sulla freccia dell'elenco a discesa.
        

        > [!TIP]  
        > Per aggiungere ulteriori clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.

    
    5.  Fare clic su **Trova**.

6.  Fare clic su un utente all'interno dei risultati della ricerca, fare clic su **Azione** e quindi fare clic su **Assegna criteri**.
    

    > [!TIP]  
    > Se si desidera applicare lo stesso criterio per dispositivi mobili per utente a più utenti, selezionare più utenti nei risultati della ricerca, quindi fare clic su <STRONG>azioni</STRONG>e quindi su <STRONG>Assegna criteri</STRONG>.



7.  In **Assegna criteri**, in **criteri dispositivi mobili**, eseguire una delle operazioni seguenti:
    

    > [!NOTE]  
    > Poiché esistono più criteri che è possibile configurare in <STRONG>Assegna criteri</STRONG>, <STRONG> &lt;Mantieni come è&gt; </STRONG> selezionato per impostazione predefinita per tutti i criteri nella finestra di dialogo. Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.

    
      - Selezionare ** \<automatico\> ** per consentire a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.
    
      - Fare clic sul nome di un criterio dispositivi mobili per utente definito in precedenza nella pagina **criteri dispositivi mobili** .
        

        > [!TIP]  
        > Per decidere quali criteri assegnare, dopo aver selezionato un nome di criteri, fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definite nei criteri.



8.  Al termine, fare clic su **OK**.

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a>Assegnazione di un criterio per dispositivi mobili per utente tramite i cmdlet di Windows PowerShell

È possibile assegnare criteri per dispositivi mobili per utente utilizzando Windows PowerShell e il cmdlet **Grant-CsMobilityPolicy** . È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a>Per assegnare criteri dispositivi mobili per utente a un singolo utente

  - Il comando seguente assegna il criterio per dispositivi mobili per utente RedmondMobilityPolicy all'utente Ken.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a>Per assegnare criteri dispositivi mobili per utente a più utenti

  - Il comando seguente assegna il criterio per dispositivi mobili per utente RedmondMobilityPolicy a tutti gli utenti a cui è attualmente assegnato il criterio NorthAmericaMobilityPolicy. Per informazioni dettagliate sul parametro Filter utilizzato in questo comando, vedere [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a>Per annullare l'assegnazione di un criterio per dispositivi mobili per utente

  - Il comando seguente annulla l'assegnazione di qualsiasi criterio di mobilità per utente precedentemente assegnato a Ken. Dopo l'annullamento dell'assegnazione dei criteri per utente, Ken Myer verrà gestito automaticamente mediante l'utilizzo dei criteri globali o dei criteri del sito locale, se esistenti. I criteri del sito hanno la precedenza sui criteri globali.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

Per informazioni dettagliate, vedere [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\)).

## <a name="see-also"></a>Vedere anche


[Configurazione di criteri per dispositivi mobili in Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)

