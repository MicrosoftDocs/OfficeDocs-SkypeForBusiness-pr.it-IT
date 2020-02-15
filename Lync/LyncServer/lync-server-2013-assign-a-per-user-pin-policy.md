---
title: 'Lync Server 2013: assegnare un criterio PIN per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user PIN policy
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48185475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9523794808ca3b689cf1f3213c1f4ad657c83c25
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030119"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a>Assegnare un criterio PIN per utente in Lync Server 2013

 


Il criterio PIN (Personal Identification Number) per le conferenze telefoniche con accesso esterno è una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server 2013.

La distribuzione di uno o più criteri PIN per utente è facoltativa. È inoltre possibile distribuire solo un criterio PIN a livello globale o criteri PIN a livello di sito. Se si distribuiscono i criteri per utente, è necessario assegnarli in modo esplicito agli utenti, ai gruppi o agli oggetti contatto. I diritti utente e le autorizzazioni per l'utilizzo dei pin per le conferenze telefoniche con accesso esterno vengono automaticamente predefiniti rispetto a quelli definiti nel criterio PIN a livello globale quando non vengono assegnati criteri specifici a livello di sito o per utente.

Dopo aver creato almeno un criterio PIN per utente, utilizzare le procedure descritte in questo argomento per assegnare i criteri che specificano i vincoli che il server deve imporre sui pin creati e utilizzati da un determinato utente.

Per informazioni dettagliate sulla creazione di criteri PIN per le conferenze telefoniche con accesso esterno per utente, vedere [creare o modificare le impostazioni del PIN per le conferenze telefoniche con accesso esterno in Lync Server 2013 per un sito o un gruppo di utenti](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).

## <a name="to-assign-a-per-user-pin-policy"></a>Per assegnare un criterio PIN per utente

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
    > Se si desidera applicare lo stesso criterio PIN per utente a più utenti, selezionare più utenti nei risultati della ricerca, quindi fare clic su <STRONG>azioni</STRONG>e quindi su <STRONG>Assegna criteri</STRONG>.



7.  In **Assegna criteri**, in **criteri PIN**, eseguire una delle operazioni seguenti:
    

    > [!NOTE]  
    > Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo <STRONG>Assegna criteri</STRONG> , <STRONG> &lt;Mantieni come è&gt; </STRONG> selezionato per impostazione predefinita per tutti i criteri nella finestra di dialogo. Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.

    
      - Consenti a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.
    
      - Fare clic sul nome di un criterio PIN per utente definito in precedenza nella pagina **criteri PIN** .
        

        > [!TIP]  
        > Per decidere quali criteri assegnare, dopo aver selezionato un nome di criteri, fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definite nei criteri.



8.  Al termine, fare clic su **OK**.

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Assegnazione di un criterio PIN per utente tramite i cmdlet di Windows PowerShell

È possibile assegnare criteri PIN per utente tramite Windows PowerShell e il cmdlet **Grant-CsPinPolicy** . È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>Per assegnare criteri PIN per utente a un singolo utente

  - Il comando seguente assegna il criterio PIN per utente RedmondPinPolicy all'utente Ken.
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>Per assegnare criteri PIN per utente a più utenti

  - Il comando seguente assegna il criterio PIN per utente RedmondUsersPinPolicy a tutti gli utenti che lavorano nella città di Redmond. Per informazioni dettagliate sul parametro LdapFilter utilizzato in questo comando, vedere [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a>Per annullare l'assegnazione di un criterio PIN per utente

  - Il comando seguente annulla l'assegnazione di un criterio PIN per utente precedentemente assegnato a Ken remario. Dopo l'annullamento dell'assegnazione dei criteri per utente, Ken Myer verrà gestito automaticamente mediante l'utilizzo dei criteri globali o dei criteri del sito locale, se esistenti. I criteri del sito hanno la precedenza sui criteri globali.
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

Per informazioni dettagliate, vedere [Grant-CsPinPolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\)).

## <a name="see-also"></a>Vedere anche


[Creare un nuovo criterio PIN in Lync Server 2013](lync-server-2013-create-a-new-pin-policy.md)  


[Assegnazione di criteri per utente in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

