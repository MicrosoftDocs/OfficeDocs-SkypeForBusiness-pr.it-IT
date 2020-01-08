---
title: 'Lync Server 2013: impostare il PIN di conferenza telefonica con accesso esterno di un utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 258c6e5da1dc5b78d53bbc3779d50890935d7b58
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a>Impostare il PIN di conferenza telefonica con accesso esterno di un utente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-06-10_

Per partecipare a una conferenza telefonica con accesso esterno come utente autenticato, un utente di Lync Server 2013 con le credenziali di Active Directory Domain Services (AD DS) richiede un PIN (Personal Identification Number). Se un utente dimentica il PIN per i servizi di conferenza telefonica con accesso esterno o non ha impostato il PIN tramite Lync Server, è possibile impostare il PIN dell'utente dal pannello di controllo di Lync Server. È possibile generare automaticamente il PIN o crearne uno manualmente.

<div>


> [!NOTE]  
> Le caratteristiche specifiche del PIN, ad esempio la lunghezza minima, possono essere configurate come criteri. Oltre al criterio globale, è possibile configurare un criterio PIN per singoli siti o utenti. Per informazioni dettagliate sulla configurazione di un criterio PIN, vedere <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">configurare le regole pin (Personal Identification Number) di conferenza telefonica con accesso esterno in Lync Server 2013</A>.



</div>

<div>

## <a name="to-set-a-users-pin"></a>Per impostare il PIN di un utente

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
        
        <div>
        

        > [!TIP]  
        > Per aggiungere altre clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.

        
        </div>
    
    5.  Fare clic su **trova**.
    
    <div>
    

    > [!NOTE]  
    > Se il PIN è bloccato, è necessario sbloccare il PIN prima di poterlo impostare. Per sbloccare il PIN, fare clic sull'utente, fare clic su <STRONG>azione</STRONG>e quindi su <STRONG>Sblocca PIN</STRONG>.

    
    </div>

6.  Fare clic su un utente nei risultati della ricerca, fare clic su **azione**e quindi su **Imposta PIN**.

7.  Nella finestra di dialogo **Imposta PIN** eseguire una delle operazioni seguenti:
    
      - Per consentire a Lync Server 2013 di generare il PIN dell'utente, selezionare **genera automaticamente un PIN valido** (impostazione predefinita).
    
      - Per creare un PIN personalizzato, fare clic su **immettere manualmente un PIN specifico**, fare clic sulla casella di testo e quindi digitare un pin che soddisfi i requisiti del PIN specificati nelle impostazioni dei criteri PIN.

8.  Fare clic su **OK**.

9.  In **Imposta PIN**eseguire una delle operazioni seguenti:
    
      - Selezionare la casella di controllo **Mostra PIN** per visualizzare il PIN e quindi copiare il PIN e comunicarlo all'utente usando il metodo preferito dell'organizzazione.
    
      - Fare clic su **Apri l'applicazione di posta elettronica per inviare il nuovo PIN all'utente** per inviare il PIN tramite posta elettronica. Se Microsoft Office Outlook è il client di posta elettronica, il PIN viene copiato automaticamente in un nuovo messaggio di posta elettronica. Se si usa un altro client di posta elettronica, selezionare la casella di controllo **Mostra PIN** per visualizzare il PIN e quindi copiarlo nel messaggio di posta elettronica.

10. Fare clic su **Chiudi**.

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Assegnazione di un PIN utente tramite i cmdlet di Windows PowerShell

Puoi assegnare i numeri di PIN anche usando il cmdlet Set-CsClientPin. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a>Per assegnare automaticamente un numero PIN a un utente

  - Con il comando seguente viene assegnato un numero PIN all'utente Ken. Dato che il parametro PIN non è incluso, Lync Server genera automaticamente e assegna il numero di PIN.
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a>Per assegnare un numero PIN specifico a un utente

  - Questo comando usa il parametro PIN per assegnare il PIN numero 121989 all'utente Ken.
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Numero di accesso esterno](https://technet.microsoft.com/en-us/library/gg133674\(v=ocs.15\))  


[Configurare le regole PIN (Personal Identification Number) per le conferenze telefoniche con accesso esterno in Lync Server 2013](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

