---
title: 'Lync Server 2013: assegnare un criterio di archiviazione per utente'
description: 'Lync Server 2013: assegnare un criterio di archiviazione per utente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c81d7e426f16c298196aba733d720a92d0854bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559992"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a>Assegnare criteri di archiviazione per utente in Lync Server 2013

 


I criteri di archiviazione sono una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server 2013.

La distribuzione di uno o più criteri di archiviazione per utente è facoltativa. È inoltre possibile distribuire criteri di archiviazione solo a livello globale o a livello di sito. Se si distribuiscono i criteri per utente, è necessario assegnarli in modo esplicito agli utenti, ai gruppi o agli oggetti contatto. Se non sono assegnati criteri a livello di sito o per utente specifici, come requisiti di archiviazione predefiniti vengono impostati automaticamente quelli definiti nei criteri di conferenza a livello globale.

Dopo la creazione di almeno un criterio di archiviazione per utente, utilizzare le procedure descritte in questo argomento per assegnare i criteri in modo da stabilire per ogni utente se il server deve archiviare le comunicazioni interne, le comunicazioni esterne o le comunicazioni di entrambi i tipi.

Per informazioni dettagliate sulla creazione di criteri di archiviazione per utente, vedere [creazione di un criterio di archiviazione in Lync Server 2013 per abilitare o disabilitare l'archiviazione delle comunicazioni interne o esterne per siti o utenti specifici](lync-server-2013-create-archiving-policy-sites-users.md).

## <a name="to-assign-a-per-user-archiving-policy"></a>Per assegnare criteri di archiviazione per utente

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
    > Se si desidera applicare gli stessi criteri di archiviazione a più utenti, selezionare più utenti all'interno dei risultati di ricerca, fare clic su <STRONG>Azioni</STRONG> e quindi su <STRONG>Assegna criteri</STRONG>.



7.  In **Assegna criteri**, in **Criteri di archiviazione**, eseguire una delle operazioni seguenti:
    

    > [!NOTE]  
    > Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo <STRONG>Assegna criteri</STRONG> , <STRONG> &lt; Mantieni come è &gt; </STRONG> selezionato per impostazione predefinita per tutti i criteri nella finestra di dialogo. Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.

    
      - Consenti a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.
    
      - Fare clic sul nome di criteri di archiviazione per utente precedentemente definiti nella pagina **Criteri di archiviazione**.
        

        > [!TIP]  
        > Per agevolare la scelta dei criteri da assegnare, fare clic su un nome di criteri e quindi fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definiti nei criteri.



8.  Al termine, fare clic su **OK**.

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Assegnazione di un criterio di archiviazione Per-User tramite i cmdlet di Windows PowerShell

È possibile assegnare criteri di archiviazione per utente tramite Windows PowerShell e il cmdlet **Grant-CsArchivingPolicy** . È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>Per assegnare criteri di archiviazione per utente a un singolo utente

  - Il comando seguente assegna il criterio di archiviazione per utente RedmondArchivingPolicy all'utente Ken Myer:
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>Per assegnare criteri di archiviazione per utente a più utenti

  - Questo comando assegna il criterio di archiviazione per utente RedmondArchivingPolicy a tutti gli utenti i cui account si trovano nel pool di registrazione atl-cs-001.litwareinc.com. Per ulteriori informazioni sul parametro Filter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a>Per annullare l'assegnazione di un criterio di archiviazione per utente

  - Il comando seguente annulla l'assegnazione di qualsiasi criterio di archiviazione per utente precedentemente assegnato a Ken Myer. Dopo l'annullamento dell'assegnazione dei criteri per utente, Ken Myer verrà gestito automaticamente mediante l'utilizzo dei criteri globali o dei criteri del sito locale, se esistenti. I criteri del sito hanno la precedenza sui criteri globali.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) .

## <a name="see-also"></a>Vedere anche


[Creazione di un criterio di archiviazione in Lync Server 2013 per abilitare o disabilitare l'archiviazione delle comunicazioni interne o esterne per siti o utenti specifici](lync-server-2013-create-archiving-policy-sites-users.md)  


[Assegnazione di criteri per utente in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

