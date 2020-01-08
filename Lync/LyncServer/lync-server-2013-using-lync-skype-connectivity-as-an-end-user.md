---
title: 'Lync Server 2013: Uso della connettività Lync-Skype come utente finale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2bf4584f3332171942f941cc382d22bb6a8db7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a>Uso della connettività Lync-Skype in Lync Server 2013 come utente finale

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-12-27_

La connettività di Lync-Skype consente agli utenti Skype e agli utenti di Lync di aggiungersi l'un l'altro come contatti, scambiare messaggi istantanei e effettuare chiamate audio e video. Quando un utente Skype aggiunge un utente di Lync, un utente Skype creerà un contatto in Skype contenente l'URI (Uniform Resource Identifier) SIP (Session Initiation Protocol) dell'utente di Lync. Viceversa, quando un utente di Lync aggiunge un contatto Skype, l'utente Lync creerà un contatto in Lync che conterrà l'account Microsoft (MSA) dell'utente Skype e non il nome utente Skype.

**Che cos'è un MSA?** Gli utenti di Skype devono accedere a Skype con un account Microsoft (in precedenza denominato Windows Live ID) per comunicare con i contatti di Lync.Un account Microsoft è costituito dalla combinazione di un indirizzo di posta elettronica e di una password, che è anche possibile usare per accedere a servizi come Microsoft OneDrive Storage Technology, Windows Phone, Microsoft Xbox LIVE online Game Service e messaggistica di Microsoft Outlook e il client di collaborazione (e, in precedenza, il servizio di posta elettronica basato sul Web di Microsoft Hotmail o Windows Live Messenger).Se si usa un indirizzo di posta elettronica e una password per accedere a questi o ad altri servizi, si ha già un account Microsoft.Per informazioni dettagliate sulla creazione di un account Microsoft, vedere la pagina di iscrizione all' [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)account Microsoft. È possibile unire l'account Skype esistente con il proprio account Microsoft per Single Sign-on, in un'ampia gamma di applicazioni e servizi. Dopo l'Unione dell'account, un utente Skype può inviare una richiesta di contatto agli utenti di Lync.

<div>


> [!IMPORTANT]  
> Per consentire agli utenti di Lync e Skype di comunicare pienamente tra loro, è necessario soddisfare i requisiti seguenti: 
> <UL>
> <LI>
> <P>Gli utenti Skype devono essere connessi al client Skype con un account Microsoft (MSA).</P>
> <LI>
> <P>Gli utenti di Lync devono essere abilitati per la connettività di messaggistica istantanea pubblica dall'amministratore di Lync.</P>
> <LI>
> <P>Quando un utente Skype aggiunge un contatto Lync, verificare che la parola Lync venga visualizzata sotto il nome del contatto. Questo indica che è stato trovato un URI di Lync.</P>
> <LI>
> <P>Quando un utente Skype aggiunge un contatto Lync e viene restituito zero risultati della ricerca per il dominio Lync, il processo di provisioning di PIC potrebbe non essere stato completato o il dominio Lync non è ancora stato configurato.</P>
> <LI>
> <P>A seconda delle impostazioni di privacy degli utenti di Lync e Skype, la messaggistica istantanea, il video e la presenza potrebbero non funzionare finché i nuovi contatti non vengono accettati da ogni utente.</P></LI></UL>



</div>

**Per aggiungere un contatto Skype a Lync 2013**

1.  In Lync fare clic su **Aggiungi contatto, aggiungere un contatto non presente nell'organizzazione**.

2.  Nell'elenco dei provider di contatti disponibili selezionare **Skype**.

3.  Nel campo **indirizzo di messaggistica istantanea** immettere l'account Microsoft (MSA) dell'utente Skype.

4.  Nella casella a discesa **Aggiungi a gruppo di contatti** selezionare un gruppo di contatti a cui aggiungere l'utente.

5.  Nella casella di riepilogo a discesa **imposta relazione di privacy** selezionare l'impostazione di contatto appropriata e quindi fare clic su **OK**.

6.  Ora l'utente verrà visualizzato come contatto in Lync. Selezionare l'utente, fare clic con il pulsante destro del mouse sul nome utente e quindi fare clic su **Visualizza scheda contatto** per visualizzare le proprietà utente. Ora puoi stabilire una chiamata audio o video con l'utente Skype appena aggiunto.

Per altre informazioni sul supporto per i contatti, vedere [aggiungere un contatto in Lync](https://support.office.com/en-us/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).

Quando l'account Microsoft di un utente Skype usa un nome di dominio personalizzato, ad esempio <strong>bob@contoso.com</strong> , un utente di Lync può aggiungere l'account Microsoft a Lync in due modi:

1.  Usare l'icona **Aggiungi contatto** o

2.  Usare la casella **trova una persona o una sala o** un campo numerico.

In ogni istanza l'utente di Lync deve immettere la posta elettronica dell'utente Skype con il formato seguente: <strong>utente (nome di dominio) @msn. com</strong> .

<div>


> [!IMPORTANT]  
> Questo passaggio non è necessario per gli account Microsoft che usano i nomi di dominio seguenti: <STRONG>@live. com, @hotmail. com o @outlook. com</STRONG>. Per altre informazioni sui nomi di dominio personalizzati supportati, vedere <A href="https://support.microsoft.com/kb/897567">domini di messaggistica istantanea pubblici supportati</A>.



</div>

**Per aggiungere un contatto Skype a Lync quando si usa un nome di dominio personalizzato**

1.  In Lync fare clic su **Aggiungi contatto, aggiungere un contatto non presente nell'organizzazione**.

2.  Nell'elenco dei provider di contatti disponibili selezionare **Skype**.

3.  Nel campo **indirizzo di messaggistica istantanea** immettere l'account Microsoft (MSA) dell'utente Skype in formato <strong>utente (nome di dominio) @msn. com</strong>. Quindi, per l'utente bob@contoso.com, la voce <strong>sarebbe Bob (contoso. com) @msn.<strong> com.

4.  Nella casella di riepilogo a discesa **Aggiungi al gruppo di contatti** selezionare un gruppo di contatti a cui aggiungere l'utente.

5.  Nella casella di riepilogo a discesa **imposta relazione di privacy** selezionare l'impostazione di contatto appropriata e quindi fare clic su **OK**.

6.  Un utente di Lync può anche usare la casella **trova una persona o una sala oppure chiamare un campo numerico** in Lync e aggiungere un indirizzo simile all' <strong>utente seguente (nome di dominio) @msn. com</strong> . Quindi, per l'account Microsoft bob@contoso.com, la voce sarebbe <strong>Bob (contoso. com) @msn. com</strong> .

7.  Seguire i passaggi 4 e 5 descritti in precedenza in questa procedura per aggiungere il contatto a un gruppo di contatti e selezionare la relazione di privacy appropriata.

**Per aggiungere un contatto Lync a Skype**

1.  Accedere a Skype. L'utente Skype deve essere connesso al client Skype con un account Microsoft (MSA).

2.  Selezionare l'icona Aggiungi contatti.

3.  Immettere l'URI SIP dell'utente di Lync. Ad esempio, bob@contoso.com.

4.  Quando Skype trova la corrispondenza nei risultati della ricerca, cercare la parola **Lync** sotto il nome dell'utente di Lync. Questo indica che Skype ha individuato correttamente l'URI SIP del client Lync. Fare clic sul nome.

5.  Nell'angolo in alto a destra della finestra fare clic su Aggiungi ai contatti.

6.  Il nuovo contatto viene ora aggiunto all'elenco contatti, ma verrà visualizzato un punto interrogativo anziché l'icona di stato finché non accetteranno la richiesta. Quando il nuovo contatto accetta la richiesta, sarà possibile vedere quando sono online, avviare conversazioni ISTANTANEe e effettuare chiamate audio e video.
    
    <div>
    

    > [!IMPORTANT]  
    > L'amministratore di Lync Server deve configurare le impostazioni dei criteri dell'utente di Lync per consentire le richieste in arrivo. In caso contrario, l'utente di Lync non riceverà le richieste di contatto dall'utente Skype. A seconda della configurazione delle impostazioni dei criteri dell'utente di Lync, la richiesta di aggiunta dell'utente Skype verrà visualizzata nella <STRONG>nuova</STRONG> scheda del client Lync. Per iniziare a comunicare con l'utente Skype, l'utente di Lync deve aggiungere l'utente Skype all'elenco Preferiti o a un elenco di contatti. L'immagine seguente mostra la posizione della <STRONG>nuova</STRONG> scheda nel client Lync.

    
    </div>

Un utente di Lync deve configurare gli avvisi di Lync per verificare che le richieste inviate da un utente Skype vengano visualizzate e siano individuabili dall'utente di Lync. Per configurare gli avvisi di Lync, completare la procedura seguente.

**Per configurare gli avvisi di Lync**

1.  Dal client Lync fare clic sull'icona **Opzioni** .

2.  Selezionare **avvisi**.

3.  In **avvisi generali**, controlla **quando qualcuno mi aggiunge all'elenco contatti**.

4.  In **contatti che non usano Lync**selezionare **Consenti invita ma blocca tutte le altre comunicazioni**.

5.  Fare clic su **OK** per chiudere la finestra Opzioni.

</div>

<span> </span>

</div>

</div>

</div>

