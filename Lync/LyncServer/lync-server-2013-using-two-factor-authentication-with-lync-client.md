---
title: "Lync Server 2013: utilizzo dell'autenticazione a due fattori con client Lync"
description: "Lync Server 2013: utilizzo dell'autenticazione a due fattori con client Lync."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbfde1d04d4e641c8fbe4817ffce214df891b565
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547282"
---
# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a>Utilizzo dell'autenticazione a due fattori con Lync client e Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-11_

In questo argomento viene descritto come utilizzare l'autenticazione a due fattori con il client Lync 2013.

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a>Accedere a Lync 2013 per la prima volta

Le informazioni di accesso di Lync vengono in genere configurate automaticamente quando viene installato Lync 2013. Tuttavia, la prima volta che si utilizza Lync, potrebbe essere necessario avviare manualmente il client.

**Per accedere a Lync per la prima volta**

1.  Accedere alla rete dell'organizzazione.

2.  Selezionare **Avvia** \> **tutti i programmi** \> **Microsoft Lync \> Lync 2013**.
    
    Verrà visualizzata la schermata di accesso di Lync.
    
      - Se la casella indirizzo di accesso è già stata compilata, verificare che l'indirizzo visualizzato sia corretto.
    
      - Se non è corretto o se la casella è vuota, immettere l'indirizzo di accesso di Lync (in genere corrisponde all'indirizzo di posta elettronica).
    
      - Se viene visualizzata una casella password vuota, aggiungere la password.

3.  Selezionare **accesso**.

</div>

<div>

## <a name="sign-out-of-lync"></a>Disconnessione di Lync

Al termine dell'utilizzo di Lync, è possibile chiudere la visualizzazione, disconnettersi dalla sessione o uscire dal programma, tutto dal menu file. Nella tabella seguente vengono illustrate le differenze tra le opzioni.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Opzione</th>
<th>Funzione</th>
<th>Modalità di esecuzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chiudere</p></td>
<td><p>Chiude la visualizzazione di Lync ma consente di continuare a eseguire la sessione di Lync identificata con l'ID utente. In questo modo è possibile continuare a ricevere notifiche e interagire con altri utenti.</p>
<p>È possibile ottenere la visualizzazione in qualsiasi momento facendo clic sull'icona di Lync sulla barra delle applicazioni o nell'area di notifica nella parte inferiore dello schermo.</p></td>
<td><p>Nella finestra principale di Lync eseguire una delle operazioni seguenti:</p>
<ol>
<li><p>Selezionare il pulsante <strong>Opzioni</strong> , quindi fare <strong>File</strong> clic su &gt; <strong>Chiudi</strong>file.</p></li>
<li><p>Fare clic sul pulsante <strong>Chiudi</strong> (X) nell'angolo in alto a destra della finestra.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>Disconnessione</p></td>
<td><p>Termina la sessione di Lync associata all'ID utente, ma Lync continua a essere eseguito in background. Quando si effettua l'accesso, verrà visualizzata la finestra di accesso.</p>
<div>

> [!TIP]  
> Selezionare <STRONG>Elimina le informazioni</STRONG> di accesso quando si effettua l'accesso per rimuovere il record dell'ID di accesso e della password dal computer. In questo modo, è possibile facilitare la risoluzione dei problemi di accesso per il supporto alle persone. È inoltre possibile garantire che le informazioni di accesso siano più sicure rendendo difficile per gli utenti non autorizzati l'accesso con le credenziali.


</div></td>
<td><p>Nella finestra principale di Lync selezionare il pulsante <strong>Opzioni</strong> , quindi selezionare <strong>File</strong> &gt; <strong>disconnessione</strong>file.</p></td>
</tr>
<tr class="odd">
<td><p>Uscita</p></td>
<td><p>Termina la sessione di Lync e arresta Lync nel computer. Dopo l'uscita, se si desidera riavviare Lync, selezionare <strong>Avvia</strong> &gt; <strong>tutti i programmi</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</p></td>
<td><p>Nella finestra principale di Lync, selezionare il pulsante <strong>Opzioni</strong> , quindi selezionare <strong>File</strong> &gt; <strong>Esci</strong>file.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a>Accedere a Lync con una smart card

Alcune organizzazioni ora utilizzano un processo di accesso a più passaggi, denominato autenticazione a due fattori, per aumentare la sicurezza per gli utenti di Lync 2013. Se si prevede di utilizzare questa opzione, sarà necessario disporre di una "smart card" per accedere a Lync. Le smart card sono disponibili in due tipi, fisico e virtuale:

  - **Fisica**     Circa le dimensioni di una carta di credito. È possibile inserirlo in un lettore di smart card quando si effettua l'accesso.

  - **Virtuale**     Non è un oggetto fisico, ma un identificatore elettronico che viene scritto in un chip speciale sul computer, che in sostanza crea la smart card nel computer in uso. Disponibile solo per l'utilizzo con i computer Windows 8 che contengono il chip TPM (Trusted Platform Module).

<div>

## <a name="enroll-your-smart-card"></a>Registrare la smart card

Prima di poter accedere con una smart card, è necessario che la scheda sia "registrazione", ovvero che le credenziali utente debbano essere identificate con la scheda. Questo è il caso se la scheda è fisica o virtuale. Questo processo potrebbe essere già stato eseguito dall'amministratore di Lync Server. Verifica se non si è certi che l'operazione sia stata completata.

<div>


> [!NOTE]  
> Poiché ogni smart card virtuale è associata solo al dispositivo in cui è installato, sarà necessario registrare una scheda separata per ogni computer Windows 8 utilizzato.



</div>

**Per registrare manualmente la smart card**

1.  Eseguire l'accesso al computer in cui verrà eseguito Lync.

2.  Tramite Internet Explorer, passare alla pagina di registrazione Web dell'autorità di certificazione dell'organizzazione.
    
    Rivolgersi all'amministratore di Lync Server per l'indirizzo Web di questa risorsa se non è già presente. L'URL avrà un aspetto analogo al seguente: https://MyCA.\ [YourCompanyName \] . com/certsrv.
    
    <div>
    

    > [!NOTE]  
    > Se si utilizza Internet Explorer 10, potrebbe essere necessario visualizzare questo sito Web in modalità compatibilità.

    
    </div>

3.  Quando viene richiesto di accedere alla pagina certificazione, eseguire l'accesso utilizzando l'account di dominio (anziché l'amministratore del computer).

4.  Nella pagina di benvenuto del sito Web, selezionare **Richiedi un certificato**.

5.  Selezionare **richiesta avanzata**.

6.  Selezionare **Crea e invia una richiesta all'autorità di certificazione**, quindi fare clic su **Avanti**.

7.  Verrà visualizzata una pagina denominata stazione di registrazione smart card. Approvare la richiesta di installazione del controllo ActiveX e quindi completare il modulo di richiesta Advanced Certificate come indicato di seguito:
    
    1.  Selezionare **utente smartcard** nell'elenco a discesa **modello di certificato** .
    
    2.  Selezionare **Crea nuovo set di chiavi**.
    
    3.  Trovare le informazioni sul produttore nell'etichetta della smart card e selezionarlo nell'elenco a discesa **CSP** .
    
    4.  Selezionare **CSP** come formato di richiesta, se non è già selezionato.
    
    5.  Selezionare **SHA1** dall'elenco a discesa dell'algoritmo hash, se non è già selezionato.
    
    6.  Assegnare un nome al certificato che si desidera riconoscere e fare clic su **Invia**.

8.  A questo punto, inserire la smart card vuota nel lettore di schede collegato alla stazione di registrazione e fare clic su **registra**.

9.  Quando richiesto, immettere il proprio PIN (Personal Identification Number) e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Se la persona del supporto tecnico non ha fornito un PIN speciale da utilizzare per registrare la smart card, utilizzare il valore del PIN della smart card predefinita, che è 12345678.

    
    </div>

10. Selezionare l'opzione per imporre all'utente di modificare il PIN al primo utilizzo della smart card.

11. A questo punto, inserire la smart card vuota nel lettore di schede collegato alla stazione di registrazione e fare clic su **registra**.

12. Quando richiesto, immettere il proprio PIN (Personal Identification Number) e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Se la persona del supporto tecnico non ha fornito un PIN speciale da utilizzare per registrare la smart card, utilizzare il valore del PIN della smart card predefinita, che è 12345678.

    
    </div>

13. Selezionare l'opzione per imporre all'utente di modificare il PIN al primo utilizzo della smart card.

14. Fare clic su **OK** per confermare che il certificato visualizzato contiene le informazioni su di esso.

15. Dopo aver visualizzato l'avviso che il certificato è stato emesso, fare clic su **installa questo certificato** per completare il processo di registrazione.

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a>Accedere a Lync con le credenziali smart card

Prima di utilizzare la smart card per la prima volta, si consiglia di fare clic su **Elimina le informazioni di accesso** nella pagina di accesso di Lync. In questo modo vengono cancellate le credenziali di accesso archiviate nel computer e viene eliminata una possibile origine di errore.

**Per accedere a Lync con le credenziali smart card**

1.  Avviare il client Lync.

2.  Nella schermata di accesso digitare il nome dell'account utente di accesso nella casella **indirizzo di accesso** e quindi fare clic su **Accedi**.

3.  Se si utilizza una smart card virtuale, ignorare questo passaggio.
    
    Se si utilizza una smart card fisica, inserire la smart card nel lettore di smart card e quindi fare clic su **OK** quando la scheda viene rilevata.

4.  Digitare il numero di PIN per la smart card e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Se non è stato assegnato un numero PIN della smart card dalla persona di supporto, utilizzare il valore predefinito, che è 12345678.

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

