---
title: 'Lync Server 2013: assegnare un criterio di posizione per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3a53ae779ccc6fb19bb2d16274e007b8fc405c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739396"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a>Assegnare criteri di posizione per utente in Lync Server 2013

 


Il criterio di posizione è una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server.

La distribuzione di uno o più criteri di posizione per utente è facoltativa. È anche possibile distribuire solo un criterio di posizione a livello globale o un criterio di posizione a livello di subnet. Se si distribuiscono criteri per utente, è necessario assegnarli esplicitamente a utenti, gruppi o oggetti contatto. Le impostazioni avanzate di 9-1-1 (E9-1-1) vengono predefinite automaticamente a quelle definite nel criterio di posizione a livello globale quando non viene assegnato alcun criterio specifico a livello di subnet o per utente.

Dopo aver creato almeno un criterio di posizione per utente, usare le procedure descritte in questo argomento per assegnare i criteri che specificano le impostazioni che il server deve applicare per le chiamate di emergenza poste da un determinato utente.

Per un elenco di tutte le impostazioni dei criteri di posizione disponibili, vedere [definizione dei criteri di posizione per Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Per informazioni dettagliate sulla creazione di criteri di posizione, vedere [creare criteri di posizione in Lync Server 2013](lync-server-2013-create-location-policies.md).

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a>Per assegnare un criterio di posizione per utente con il pannello di controllo di Lync Server

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
    > Se si desidera che gli stessi criteri di posizione per utente vengano applicati a più utenti, selezionare più utenti nei risultati della ricerca, quindi fare clic su <STRONG>azioni</STRONG>e quindi su <STRONG>Assegna criteri</STRONG>.



7.  In **Assegna criteri**, in **criteri di posizione**, eseguire una delle operazioni seguenti:
    

    > [!NOTE]  
    > Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo <STRONG>Assegna criteri</STRONG> , <STRONG> &lt;Mantieni come&gt; </STRONG> è selezionato per impostazione predefinita per ogni criterio nella finestra di dialogo. Continuare a usare il criterio precedentemente assegnato all'utente senza apportare alcuna modifica a questa impostazione.

    
      - Consenti a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di subnet.
    
      - Fare clic sul nome dei criteri di posizione per utente definiti in precedenza eseguendo il cmdlet **New-CsLocationPolicy** .
        

        > [!TIP]  
        > Per decidere i criteri da assegnare, fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definiti nel criterio dopo aver fatto clic su un nome di criterio.



8.  Al termine, fare clic su **OK**.

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a>Assegnazione di un criterio di posizione per utente tramite i cmdlet di Lync Server Management Shell

È possibile assegnare criteri di posizione per utente usando il cmdlet Grant-CsLocationPolicy. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a>Per assegnare un criterio di posizione per utente a un singolo utente

  - Con il comando seguente viene assegnato il criterio di posizione per utente RedmondLocationPolicy all'utente Ken.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a>Per assegnare un criterio di posizione per utente a più utenti

  - Questo comando assegna il criterio di posizione per utente AccountingDepartmentLocationPolicy a tutti gli utenti che lavorano per il reparto contabilità. Per altre informazioni sul parametro LdapFilter usato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a>Per annullare l'assegnazione di un criterio di posizione per utente

  - Il comando seguente annulla l'assegnazione di criteri di posizione per utente assegnati in precedenza a Ken. Dopo che il criterio per utente non è stato assegnato, Ken è gestito automaticamente tramite il criterio globale oppure, se disponibile, il criterio del sito locale. Un criterio di sito ha la precedenza sui criteri globali.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) .

