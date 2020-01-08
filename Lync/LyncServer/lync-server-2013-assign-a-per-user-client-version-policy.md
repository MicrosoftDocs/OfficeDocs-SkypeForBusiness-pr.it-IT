---
title: 'Lync Server 2013: assegnare un criterio di versione client per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bfd26aff4ae2e5d8dacf7ec145bec0e3247facf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985533"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a>Assegnare criteri di versione client per utente in Lync Server 2013

 


Il criterio di versione client è una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server.

La distribuzione di uno o più criteri di versione client per utente è facoltativa. È anche possibile distribuire solo criteri di versione client a livello globale o criteri di versione del client a livello di sito o a livello di pool. Se si distribuiscono criteri per utente, è necessario assegnarli esplicitamente a utenti, gruppi o oggetti contatto. Quando non sono assegnati criteri specifici a livello di sito, a livello di pool o per utente, i client predefiniti consentiti per la registrazione con Lync Server 2013 sono quelli definiti nel criterio di versione client a livello globale.

Dopo aver creato almeno un criterio di versione client per utente, usare le procedure descritte in questo argomento per assegnare i criteri che specificano le versioni client che si desidera consentire la registrazione con Lync Server.

Per informazioni dettagliate sulla creazione di criteri di versione client per utente, vedere [specificare le applicazioni client che è possibile usare per accedere a Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).

## <a name="to-assign-a-per-user-client-version-policy"></a>Per assegnare un criterio di versione client per utente

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
    > Se si desidera che gli stessi criteri di versione client per utente vengano applicati a più utenti, selezionare più utenti nei risultati della ricerca, quindi fare clic su <STRONG>azioni</STRONG>e quindi su <STRONG>Assegna criteri</STRONG>.



7.  In **Assegna criteri**, in **criteri di versione client**, eseguire una delle operazioni seguenti:
    

    > [!NOTE]  
    > Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo <STRONG>Assegna criteri</STRONG> , <STRONG> &lt;Mantieni come&gt; </STRONG> è selezionato per impostazione predefinita per ogni criterio nella finestra di dialogo. Continuare a usare il criterio precedentemente assegnato all'utente senza apportare alcuna modifica a questa impostazione.

    
      - Consenti a Lync Server di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito o a livello di pool.
    
      - Fare clic sul nome di un criterio di versione client per utente definito in precedenza nella pagina dei **criteri di versione client** .
        

        > [!TIP]  
        > Per decidere i criteri da assegnare, fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definiti nel criterio dopo aver fatto clic su un nome di criterio.



8.  Al termine, fare clic su **OK**.

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a>Assegnazione di un criterio di versione client per utente tramite i cmdlet di Windows PowerShell

Puoi assegnare criteri di versione client per utente usando il cmdlet Grant-CsClientVersionPolicy. Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a>Per assegnare un criterio di versione client per utente a un singolo utente

  - Con il comando seguente viene assegnato il criterio di versione client per utente RedmondClientVersionPolicy all'utente Ken.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a>Per assegnare criteri di versione client per utente a più utenti

  - Questo comando assegna il criterio di versione client per utente RedmondClientVersionPolicy a tutti gli utenti a cui è attualmente assegnato il criterio vocale RedmondVoicePolicy. Per altre informazioni sul parametro Filter usato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a>Per annullare l'assegnazione di un criterio di versione client per utente

  - Il comando seguente annulla l'assegnazione di criteri di versione client per utente assegnati in precedenza a Ken. Dopo che il criterio per utente non è stato assegnato, Ken è gestito automaticamente tramite il criterio globale, i criteri del sito locale (se disponibile) o i criteri di ambito del servizio assegnati al suo registrar. I criteri di ambito del servizio hanno la precedenza su qualsiasi criterio di sito e i criteri del sito hanno la precedenza sui criteri globali.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) .

## <a name="see-also"></a>Vedere anche


[Assegnazione di criteri per utente in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
[Gestione di dispositivi, telefoni e applicazioni client in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

