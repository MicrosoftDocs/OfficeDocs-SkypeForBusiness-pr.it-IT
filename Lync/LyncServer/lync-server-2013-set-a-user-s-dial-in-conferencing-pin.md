---
title: 'Lync Server 2013: impostare il PIN per le conferenze telefoniche con accesso esterno di un utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c344a848050d53027c094ad549f0285fbae09489
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a>Impostare il PIN di conferenza telefonica con accesso esterno di un utente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-06-10_

Per partecipare a una conferenza telefonica con accesso esterno come utente autenticato, un utente di Lync Server 2013 con le credenziali di servizi di dominio Active Directory richiede un codice PIN (Personal Identification Number). Se un utente dimentica il PIN per le conferenze telefoniche con accesso esterno o non ha impostato il PIN utilizzando Lync Server, è possibile impostare il PIN dell'utente dal pannello di controllo di Lync Server. È possibile generare automaticamente il PIN o crearne uno manualmente.

<div>


> [!NOTE]  
> Le caratteristiche specifiche del PIN, ad esempio la lunghezza minima, possono essere configurate come criterio. Oltre al criterio globale, è possibile configurare un criterio PIN per singoli siti o utenti. Per informazioni dettagliate sulla configurazione di un criterio PIN, vedere <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Configure Dial-in Conferencing Personal Identification Number (pin) Rules in Lync Server 2013</A>.



</div>

<div>

## <a name="to-set-a-users-pin"></a>Per impostare il PIN di un utente

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

6.  Fare clic su un utente nei risultati della ricerca, su **Azione** e quindi su **Imposta PIN**.

7.  Nella finestra di dialogo **Imposta PIN** eseguire una delle operazioni seguenti:
    
      - Per consentire a Lync Server 2013 di generare il PIN dell'utente, selezionare **genera automaticamente un PIN valido** (impostazione predefinita).
    
      - Per creare un PIN personalizzato, fare clic su **Immetti manualmente un PIN specifico**, fare clic sulla casella di testo e quindi digitare un PIN che soddisfi i requisiti PIN specificati nelle impostazioni del criterio PIN.

8.  Fare clic su **OK**.

9.  In **Imposta PIN** eseguire una delle operazioni seguenti:
    
      - Selezionare la casella di controllo **Mostra PIN** per visualizzare il PIN e quindi copiare il PIN e comunicarlo all'utente utilizzando il metodo preferito dell'organizzazione.
    
      - Fare clic su **Apri applicazione di posta elettronica per inviare il nuovo PIN all'utente** per inviare il PIN per posta elettronica. Se si utilizza Microsoft Office Outlook come client di posta elettronica, il PIN verrà copiato automaticamente in un nuovo messaggio di posta elettronica. Se invece si utilizza un altro client di posta elettronica, selezionare la casella di controllo **Mostra PIN** per visualizzare il PIN e quindi copiarlo nel messaggio di posta elettronica.

10. Fare clic su **Chiudi**.

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Assegnazione di un PIN utente tramite i cmdlet di Windows PowerShell

È possibile assegnare i numeri di PIN anche utilizzando il cmdlet Set-CsClientPin. È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a>Per assegnare automaticamente un numero di PIN a un utente

  - Il comando seguente assegna un numero PIN all'utente Ken Myer. Poiché il parametro PIN non è incluso, Lync Server genererà e assegnerà automaticamente il numero di PIN.
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a>Per assegnare un numero di PIN specifico a un utente

  - Questo comando usa il parametro Pin per assegnare il numero PIN 121989 all'utente Ken Myer.
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Numero di accesso esterno](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))  


[Configurare le regole del PIN (Personal Identification Number) per le conferenze telefoniche con accesso esterno in Lync Server 2013](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

