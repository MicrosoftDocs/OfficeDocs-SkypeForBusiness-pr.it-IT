---
title: 'Lync Server 2013: assegnazione di un criterio di conferenza per utente'
description: 'Lync Server 2013: assegnazione di un criterio di conferenza per utente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 819d1431a2a7a921ff8c306c47c8b5f86bf5d5bb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559922"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a>Assegnazione di un criterio di conferenza per utente in Lync Server 2013

 


I criteri di conferenza sono una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server.

La distribuzione di uno o più criteri di conferenza per utente è facoltativa. È inoltre possibile distribuire solo criteri di conferenza a livello globale o a livello di sito. Se si distribuiscono criteri per utente, è necessario assegnarli in modo esplicito a utenti, gruppi o oggetti contatto. Le autorizzazioni e i diritti utente per le conferenze vengono impostati automaticamente su quelli definiti nei criteri di conferenza a livello globale quando non sono assegnati criteri a livello di sito o per utente specifici.

Dopo aver creato criteri di conferenza per utente, utilizzare le procedure incluse in questo argomento per assegnare i criteri che specificano le autorizzazioni e i diritti utente che si desidera vengano concessi dal server alle riunioni organizzate da un utente specifico.

Per un elenco di tutte le impostazioni disponibili per i criteri di conferenza, vedere informazioni di [riferimento sulle impostazioni dei criteri di conferenza per Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

Per informazioni dettagliate sulla creazione di criteri di conferenza, vedere [Create or modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

## <a name="to-assign-a-per-user-conferencing-policy"></a>Per assegnare criteri di conferenza per utente

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

6.  Fare clic su un utente nei risultati della ricerca, fare clic su **Azione** e quindi su **Assegna criteri**.
    

    > [!TIP]  
    > Se si desidera applicare gli stessi criteri di conferenza per utente a più utenti, selezionare i diversi utenti nei risultati della ricerca, fare clic su <STRONG>Azioni</STRONG> e quindi su <STRONG>Assegna criteri</STRONG>.



7.  In **Criteri conferenza** in **Assegna criteri** eseguire una delle operazioni seguenti:
    

    > [!NOTE]  
    > Poiché esistono più criteri che è possibile configurare in <STRONG>Assegna criteri</STRONG>, <STRONG> &lt; Mantieni come è &gt; </STRONG> selezionato per impostazione predefinita per tutti i criteri nella finestra di dialogo. Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.

    
      - Selezionare questa opzione **\<Automatic\>** per consentire a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.
    
      - Fare clic sui nomi dei criteri di conferenza per utente definiti in precedenza nella pagina **Criteri conferenza**.
        

        > [!TIP]  
        > Per stabilire i criteri che si desidera assegnare, dopo avere fatto clic sui nomi dei criteri, fare clic su <STRONG>Visualizza</STRONG> per visualizzare le autorizzazioni e i diritti utente definiti nei criteri.



8.  Al termine, fare clic su **OK**.

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a>Assegnazione di un criterio di conferenza Per-User tramite i cmdlet di Windows PowerShell

I criteri di conferenza per utente possono essere assegnati utilizzando Windows PowerShell e il cmdlet Grant-CsConferencingPolicy. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a>Per assegnare criteri di conferenza per utente a un singolo utente

  - Il comando seguente assegna il criterio di conferenza per utente RedmondConferencingPolicy all'utente Ken Myer.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a>Per assegnare criteri di conferenza per utente a più utenti

  - Questo comando assegna il criterio di conferenza per utente HRConferencingPolicy a tutti gli utenti che lavorano nel dipartimento delle Risorse umane. Per ulteriori informazioni sul parametro LdapFilter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a>Per annullare l'assegnazione di un criterio di conferenza per utente

  - Il comando seguente annulla l'assegnazione di tutti i criteri di conferenza per utente precedentemente assegnati a Ken Myer. Dopo l'annullamento del criterio per utente, Ken Myer sarà gestito automaticamente dal criterio globale oppure dall'eventuale criterio del sito locale, che ha la precedenza sul criterio globale.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) .

## <a name="see-also"></a>Vedere anche


[Creare o modificare criteri di conferenza in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[Assegnazione di criteri per utente in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

