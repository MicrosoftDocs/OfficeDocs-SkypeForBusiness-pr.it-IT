---
title: "Lync Server 2013: visualizzare le informazioni sul PIN dell'utente"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View user PIN information
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49733661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b338691813980130d60cd5424cc87dd9d0220f5f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-user-pin-information-in-lync-server-2013"></a>Visualizzare le informazioni sul PIN degli utenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Per partecipare a una conferenza telefonica con accesso esterno come utente autenticato, un utente di Lync Server 2013 con le credenziali di servizi di dominio Active Directory richiede un codice PIN (Personal Identification Number). È possibile visualizzare le informazioni sul PIN di un utente dal pannello di controllo di Lync Server 2013.

<div>


> [!NOTE]  
> È possibile visualizzare informazioni sullo stato del PIN, ad esempio per scoprire se il PIN è stato impostato o quando è stato modificato l'ultima volta, ma non è possibile vedere il PIN corrente controllandone lo stato. Se un utente ha perso il proprio PIN, è possibile reimpostarlo attenendosi alle procedure descritte in impostare il PIN per le conferenze telefoniche con <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">accesso esterno di un utente in Lync Server 2013</A>



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a>Per visualizzare il PIN di un utente nel pannello di controllo di Lync Server

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
    
    <div>
    

    > [!NOTE]  
    > Se il PIN è bloccato, è necessario sbloccarlo per poterlo impostare. Per sbloccare il PIN, fare clic sull'utente, su <STRONG>Azione</STRONG> e quindi su <STRONG>Sblocca PIN</STRONG>.

    
    </div>

6.  Fare clic su un utente nei risultati della ricerca, su **Azione** e quindi su **Visualizza stato PIN**.

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sul PIN utente tramite i cmdlet di Windows PowerShell

È possibile visualizzare le informazioni sul PIN degli utenti utilizzando il cmdlet Get-CsClientPinInfo. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-view-user-pin-information"></a>Per visualizzazione informazioni sul PIN di un utente

  - Per visualizzare le informazioni sul PIN per un utente, digitare un comando simile al seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    Verranno restituite informazioni simili alle seguenti:
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Impostare il PIN di conferenza telefonica con accesso esterno di un utente in Lync Server 2013](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[Bloccare o sbloccare il PIN di un utente in Lync Server 2013](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

