---
title: "Lync Server 2013: utilizzo dell'autenticazione a due fattori con il client Lync"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5af9e9b5268fd218bfe5856473124514cfe34945
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a>Uso dell'autenticazione a due fattori con Lync client e Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-11_

Questo argomento descrive come sfruttare l'autenticazione a due fattori con il client Lync 2013.

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a>Accedere a Lync 2013 per la prima volta

Le informazioni di accesso di Lync vengono in genere configurate automaticamente al momento dell'installazione di Lync 2013. Ma la prima volta che si usa Lync, potrebbe essere necessario avviare manualmente il client.

**Per accedere a Lync per la prima volta**

1.  Accedere alla rete dell'organizzazione.

2.  Selezionare **Avvia** \> **tutti i programmi** \> **Microsoft \> Lync Lync 2013**.
    
    La schermata di accesso di Lync dovrebbe essere visualizzata.
    
      - Se la casella indirizzo di accesso è già stata compilata, verificare che l'indirizzo visualizzato sia corretto.
    
      - Se non è corretto o se la casella è vuota, immettere l'indirizzo di accesso di Lync (in genere corrisponde all'indirizzo di posta elettronica).
    
      - Se viene visualizzata una casella password vuota, aggiungere la password.

3.  Selezionare **Accedi**.

</div>

<div>

## <a name="sign-out-of-lync"></a>Disconnettersi da Lync

Dopo aver completato l'uso di Lync, è possibile chiudere la visualizzazione, disconnettersi dalla sessione o uscire dal menu file. La tabella seguente illustra le differenze tra le opzioni.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Opzione</th>
<th>Cosa fa</th>
<th>Come eseguirlo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Vicino</p></td>
<td><p>Chiude la visualizzazione Lync ma consente di continuare a eseguire la sessione Lync identificata con l'ID utente. In questo modo puoi continuare a ricevere notifiche e interagire con altri utenti.</p>
<p>È possibile ripristinare la visualizzazione in qualsiasi momento facendo clic sull'icona di Lync nella barra delle applicazioni o nell'area di notifica nella parte inferiore dello schermo.</p></td>
<td><p>Nella finestra principale di Lync eseguire una delle operazioni seguenti:</p>
<ol>
<li><p>Selezionare il pulsante <strong>Opzioni</strong> , quindi selezionare <strong>file</strong> &gt; <strong>Chiudi</strong>.</p></li>
<li><p>Fare clic sul pulsante <strong>Chiudi</strong> (X) nell'angolo in alto a destra della finestra.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>Disconnettersi</p></td>
<td><p>Termina la sessione Lync associata all'ID utente, ma Lync continua a essere eseguito in background. Quando ci si disconnette, verrà visualizzata la finestra di accesso.</p>
<div>

> [!TIP]  
> Selezionare <STRONG>Elimina le informazioni</STRONG> di accesso quando si esce per rimuovere il record dell'ID di accesso e della password dal computer. In questo modo, puoi semplificare la risoluzione dei problemi di accesso per il supporto delle persone. Può anche essere utile garantire che le informazioni di accesso siano più sicure, rendendo difficile per gli utenti non autorizzati l'accesso con le credenziali.


</div></td>
<td><p>Nella finestra principale di Lync selezionare il pulsante <strong>Opzioni</strong> e quindi fare clic su <strong>Disconnetti</strong> <strong>file</strong> &gt; .</p></td>
</tr>
<tr class="odd">
<td><p>Uscita</p></td>
<td><p>Termina la sessione di Lync e arresta Lync nel computer. Dopo l'uscita, se si vuole riavviare Lync, selezionare <strong>Avvia</strong> &gt; <strong>tutti i programmi</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</p></td>
<td><p>Nella finestra principale di Lync selezionare il pulsante <strong>Opzioni</strong> e quindi selezionare Esci <strong>file</strong> &gt; <strong></strong>.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a>Accedere a Lync con una smart card

Alcune organizzazioni usano ora un processo di accesso a più passaggi, denominato autenticazione a due fattori, per aumentare la sicurezza per gli utenti di Lync 2013. Se si prevede di usare questa opzione, è necessaria una "smart card" per accedere a Lync. Le smart card sono disponibili in due tipi, fisico e virtuale:

  - **Fisiche**   delle dimensioni di una carta di credito. Quando si effettua l'accesso, è possibile inserirla in un lettore di smart card.

  - **Virtual**   non è un oggetto fisico, ma un identificatore elettronico che viene scritto in un chip speciale nel computer, che in sostanza crea la smart card nel computer. Disponibile solo per l'uso con i computer Windows 8 che contengono il chip TPM (Trusted Platform Module).

<div>

## <a name="enroll-your-smart-card"></a>Registrare la smart card

Prima di poter accedere con una smart card, la scheda deve essere "registrata", ovvero le credenziali utente devono essere identificate con la scheda. Questo è il caso che la carta sia fisica o virtuale. Questo processo può essere già eseguito dall'amministratore di Lync Server. Verificare se non si è certi che sia stato fatto.

<div>


> [!NOTE]  
> Poiché ogni smart card virtuale è associata solo al dispositivo in cui è installato, sarà necessario registrare una scheda separata per ogni computer Windows 8 usato.



</div>

**Per registrare manualmente la smart card**

1.  Accedere al computer in cui verrà eseguito Lync.

2.  Usando Internet Explorer, passare alla pagina di registrazione Web dell'autorità di certificazione dell'organizzazione.
    
    Rivolgersi all'amministratore di Lync Server per l'indirizzo Web della risorsa, se non è già disponibile. L'URL avrà un aspetto simile al seguente https://MyCA.\: [\]NomeSocietà. com/certsrv.
    
    <div>
    

    > [!NOTE]  
    > Se si usa Internet Explorer 10, potrebbe essere necessario visualizzare il sito Web in modalità compatibilità.

    
    </div>

3.  Quando viene richiesto di accedere alla pagina certificazione, accedere con l'account di dominio (anziché come amministratore del computer).

4.  Nella pagina di benvenuto del sito Web selezionare **Richiedi un certificato**.

5.  Selezionare **richiesta avanzata**.

6.  Selezionare **Crea e inviare una richiesta alla CA**, quindi fare clic su **Avanti**.

7.  Ora verrà visualizzata una pagina denominata stazione di registrazione smart card. Approva la richiesta di installazione del controllo ActiveX e quindi compila il modulo di richiesta Advanced Certificate nel modo seguente:
    
    1.  Selezionare **utente smartcard** nell'elenco a discesa **modello di certificato** .
    
    2.  Selezionare **Crea nuovo set di tasti**.
    
    3.  Trovare le informazioni sul produttore nell'etichetta della smart card e selezionare tale produttore nell'elenco a discesa **CSP** .
    
    4.  Selezionare **CSP** come formato di richiesta, se non è già selezionato.
    
    5.  Selezionare **SHA1** nell'elenco a discesa algoritmo hash, se non è già selezionato.
    
    6.  Assegnare un nome al certificato che verrà riconosciuto e quindi fare clic su **Invia**.

8.  Inserire ora la smart card vuota nel lettore di schede collegata alla stazione di registrazione e fare clic su **registra**.

9.  Quando richiesto, immettere il PIN (Personal Identification Number) e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Se la persona del supporto tecnico non ha ricevuto un PIN speciale da usare per la registrazione della smart card, usare il valore PIN della smart card predefinito, ovvero 12345678.

    
    </div>

10. Selezionare l'opzione per forzare l'utente a cambiare il PIN per la prima volta che viene usata la smart card.

11. Inserire ora la smart card vuota nel lettore di schede collegata alla stazione di registrazione e fare clic su **registra**.

12. Quando richiesto, immettere il PIN (Personal Identification Number) e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Se la persona del supporto tecnico non ha ricevuto un PIN speciale da usare per la registrazione della smart card, usare il valore PIN della smart card predefinito, ovvero 12345678.

    
    </div>

13. Selezionare l'opzione per forzare l'utente a cambiare il PIN per la prima volta che viene usata la smart card.

14. Fare clic su **OK** per confermare che il certificato visualizzato contiene le informazioni.

15. Quando viene visualizzato l'avviso che il certificato è stato emesso, fare clic su **installa questo certificato** per completare il processo di registrazione.

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a>Accedere a Lync con le credenziali della smart card

Prima di usare la smart card per la prima volta, è consigliabile fare clic su **Elimina le informazioni di accesso** nella pagina di accesso di Lync. In questo modo vengono cancellate le credenziali di accesso archiviate nel computer e viene eliminata una possibile origine di errore.

**Per accedere a Lync con le credenziali della smart card**

1.  Avviare il client Lync.

2.  Nella schermata di accesso digitare il nome dell'account utente di accesso nella casella **indirizzo di accesso** e quindi fare clic su **Accedi**.

3.  Se si usa una smart card virtuale, ignorare questo passaggio.
    
    Se si usa una smart card fisica, inserire la smart card nel lettore di smart card e quindi fare clic su **OK** quando viene rilevata la scheda.

4.  Digitare il PIN number per la smart card e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Se il numero di PIN della smart card non è stato assegnato dalla persona di supporto, usare il valore predefinito, ovvero 12345678.

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

