---
title: 'Lync Server 2013: assegnare un criterio di versione client per utente'
description: 'Lync Server 2013: assegnare un criterio di versione client per utente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ec2fcbf9c005806a97dfbdceb22095fe0ff8f33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559978"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a>Assegnare criteri di versione client per utente in Lync Server 2013

 


I criteri di versione client sono una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server.

La distribuzione di uno o più criteri di versione client per utente è facoltativa. È anche possibile distribuire solo un criterio di versione client a livello globale oppure criteri di versione client a livello di sito o di pool. Se si distribuiscono i criteri per utente, è necessario assegnarli in modo esplicito a utenti, gruppi o oggetti contatto. Quando non vengono assegnati criteri specifici a livello di sito, a livello di pool o per utente, i client predefiniti che sono autorizzati a eseguire la registrazione con Lync Server 2013 sono quelli definiti nei criteri di versione client a livello globale.

Dopo aver creato almeno un criterio di versione client per utente, utilizzare le procedure descritte in questo argomento per assegnare i criteri che specificano le versioni client che si desidera consentire di eseguire la registrazione con Lync Server.

Per informazioni dettagliate sulla creazione di criteri di versione client per utente, vedere [specificare le applicazioni client che possono essere utilizzate per accedere a Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).

## <a name="to-assign-a-per-user-client-version-policy"></a>Per assegnare criteri di versione client per utente

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

6.  Fare clic su un utente nei risultati di ricerca, fare clic su **Azione** e quindi fare clic su **Assegna criteri**.
    

    > [!TIP]  
    > Se si desidera applicare a più utenti gli stessi criteri di versione client per utente, selezionare più utenti nei risultati di ricerca, fare clic su <STRONG>Azioni</STRONG> e quindi su <STRONG>Assegna criteri</STRONG>.



7.  In **Assegna criteri**, in **Criteri versione client** effettuare una delle operazioni seguenti:
    

    > [!NOTE]  
    > Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo <STRONG>Assegna criteri</STRONG> , <STRONG> &lt; Mantieni come è &gt; </STRONG> selezionato per impostazione predefinita per tutti i criteri nella finestra di dialogo. Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.

    
      - Consentire a Lync Server di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito o a livello di pool.
    
      - Fare clic sul nome dei criteri di versione client per utente precedentemente definiti nella pagina **Criteri versione client**.
        

        > [!TIP]  
        > Per decidere quali criteri assegnare, dopo aver selezionato un nome di criteri, fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definite nei criteri.



8.  Al termine, fare clic su **OK**.

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a>Assegnazione di un criterio di versione client di Per-User tramite i cmdlet di Windows PowerShell

È possibile assegnare un criterio di versione client per utente utilizzando il cmdlet Grant-CsClientVersionPolicy. È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a>Per assegnare un criterio di versione client per utente a un unico utente

  - Il comando seguente assegna il criterio di versione client per utente RedmondClientVersionPolicy all'utente Davide Garghentini.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a>Per assegnare un criterio di versione client per utente a più utenti

  - Il comando assegna il criterio di versione client per utente RedmondClientVersionPolicy a tutti gli utenti a cui è attualmente assegnato il criterio vocale RedmondVoicePolicy. Per ulteriori informazioni sul parametro Filter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a>Per annullare l'assegnazione dei criteri di versione client per utente

  - Il comando seguente annulla l'assegnazione del criterio di versione client per utente precedentemente assegnato a Davide Garghentini. Dopo che l'assegnazione del criterio per utente è stata annullata, Davide Garghentini verrà gestito automaticamente utilizzando il criterio globale, il relativo criterio sito globale (se esistente) o il criterio dell'ambito del servizio assegnato alla relativa Registrazione avanzata. Un criterio ambito del servizio ha la precedenza rispetto a un criterio sito e un criterio sito ha la precedenza rispetto al criterio globale.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) .

## <a name="see-also"></a>Vedere anche


[Assegnazione di criteri per utente in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
[Gestione di dispositivi, telefoni e applicazioni client in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

