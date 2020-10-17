---
title: 'Lync Server 2013: bloccare o sbloccare il PIN di un utente'
description: 'Lync Server 2013: bloccare o sbloccare il PIN di un utente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lock or unlock a user PIN
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49733618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cf04be333e9d17dd0a06e6eb98d314c2960c3b7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570552"
---
# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a>Bloccare o sbloccare il PIN di un utente in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

È possibile bloccare o sbloccare il PIN di un utente dalla sezione **utenti** del pannello di controllo di Lync Server 2013.

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a>Per bloccare il PIN di un utente nel pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Utenti**.

4.  Utilizzare uno dei metodi seguenti per individuare un utente:
    
      - Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.
    
      - Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.

5.  (Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:
    
    1.  Fare clic su **Aggiungi filtro**.
    
    2.  Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.
    
    3.  Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Diverso da**.
    
    4.  A seconda della proprietà utente selezionata, immettere i criteri che si desidera utilizzare per filtrare i risultati della ricerca digitandoli oppure facendo clic sulla freccia nell'elenco a discesa.
        
        <div>
        

        > [!TIP]  
        > Per aggiungere ulteriori clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.

        
        </div>
    
    5.  Fare clic su **Trova**.
    
    6.  Fare clic sull'utente, su **Azione** e quindi su **Blocca PIN**.

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a>Per sbloccare il PIN di un utente nel pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Utenti**.

4.  Utilizzare uno dei metodi seguenti per individuare un utente:
    
      - Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.
    
      - Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.

5.  (Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:
    
    1.  Fare clic su **Aggiungi filtro**.
    
    2.  Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.
    
    3.  Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Diverso da**.
    
    4.  A seconda della proprietà utente selezionata, immettere i criteri che si desidera utilizzare per filtrare i risultati della ricerca digitandoli oppure facendo clic sulla freccia nell'elenco a discesa.
        
        <div>
        

        > [!TIP]  
        > Per aggiungere ulteriori clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.

        
        </div>
    
    5.  Fare clic su **Trova**.
    
    6.  Fare clic sull'utente, su **Azione** e quindi su **Sblocca PIN**.

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>Blocco e sblocco dei PIN utente tramite i cmdlet di Windows PowerShell

È possibile bloccare e sbloccare i pin degli utenti utilizzando Windows PowerShell e i cmdlet Lock-CsClientPin e Unlock-CsClientPin. È possibile eseguire questi cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-lock-a-user-pin"></a>Per bloccare il PIN di un utente

  - Per bloccare il PIN di un utente, utilizzare il cmdlet Lock-CsClientPin. Ad esempio:
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a>Per sbloccare il PIN di un utente

  - Per sbloccare il PIN di un utente, utilizzare il cmdlet Unlock-CsClientPin. Ad esempio:
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo ai cmdlet [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) e [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

