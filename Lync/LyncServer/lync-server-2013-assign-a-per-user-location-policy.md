---
title: 'Lync Server 2013: assegnare un criterio percorso per utente'
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
ms.openlocfilehash: 1d66df7f2d0c8a2b8603f7c08312f5b8b6aaad56
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134432"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a>Assegnare un criterio percorso per utente in Lync Server 2013

 


Il criterio percorso è una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server.

La distribuzione di uno o più criteri percorso per utente è facoltativa. È inoltre possibile distribuire un solo criterio percorso a livello globale o a livello di subnet. Se si distribuiscono criteri per utente, è necessario assegnarli in modo esplicito agli utenti, ai gruppi o agli oggetti contatto. Se non sono assegnati criteri specifici a livello di subnet o per utente, per impostazione predefinita in Enhanced 9-1-1 (E9-1-1) vengono utilizzate automaticamente le impostazioni definite nel criterio a livello globale.

Dopo aver creato almeno un criterio percorso per utente, utilizzare le procedure descritte in questo argomento per assegnare il criterio che specifica le impostazioni che devono essere applicate dal server per le chiamate di emergenza effettuate da un utente specifico.

Per un elenco di tutte le impostazioni dei criteri di percorso disponibili, vedere [define the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Per informazioni dettagliate sulla creazione dei criteri percorso, vedere [create location Policies in Lync Server 2013](lync-server-2013-create-location-policies.md).

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a>Per assegnare un criterio percorso per utente con il pannello di controllo di Lync Server

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

6.  Fare clic su un utente nei risultati della ricerca, su **Azione** e quindi su **Assegna criteri**.
    

    > [!TIP]  
    > Se si desidera applicare lo stesso criterio percorso per utente a più utenti, selezionare più utenti nei risultati della ricerca, fare clic su <STRONG>Azioni</STRONG> e quindi su <STRONG>Assegna criteri</STRONG>.



7.  In **Criteri percorso** in **Assegna criteri** eseguire una delle operazioni seguenti:
    

    > [!NOTE]  
    > Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo <STRONG>Assegna criteri</STRONG> , <STRONG> &lt;Mantieni come è&gt; </STRONG> selezionato per impostazione predefinita per tutti i criteri nella finestra di dialogo. Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.

    
      - Consenti a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di subnet.
    
      - Fare clic sul nome di un criterio percorso per utente precedentemente definito eseguendo il cmdlet **New-CsLocationPolicy**.
        

        > [!TIP]  
        > Per agevolare la scelta dei criteri da assegnare, fare clic su un nome di criteri e quindi fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definiti nei criteri.



8.  Al termine, fare clic su **OK**.

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a>Assegnazione di un criterio percorso per utente tramite i cmdlet di Lync Server Management Shell

È possibile assegnare criteri percorso per utente utilizzando il cmdlet Grant-CsLocationPolicy. È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a>Per assegnare un criterio percorso per utente a un utente singolo

  - Il comando seguente consente di assegnare i criteri percorso per utente denominati RedmondLocationPolicy all'utente Ken Myer.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a>Per assegnare un criterio percorso per utente a più utenti

  - Questo comando assegna il criterio percorso per utente AccountingDepartmentLocationPolicy a tutti gli utenti che lavorano per il reparto Contabilità. Per ulteriori informazioni sul parametro LdapFilter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a>Per annullare l'assegnazione di un criterio percorso per utente

  - Il comando seguente annulla l'assegnazione dei criteri percorso per utente precedentemente assegnati all'utente Ken Myer. Dopo l'annullamento dell'assegnazione dei criteri per utente, Ken Myer verrà gestito automaticamente tramite i criteri globali oppure i criteri di sito locale, se esistenti. I criteri di sito sono prioritari rispetto ai criteri globali.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsLocationPolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) .

