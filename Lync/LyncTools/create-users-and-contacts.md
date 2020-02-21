---
title: Creare utenti e contatti
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76b8016079cd130a814da410df5e5a5b151d8702
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a>Creare utenti e contatti

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

È necessario utilizzare lo strumento di provisioning degli utenti di Lync Server 2013 (UserProvisioningTool. exe) per creare utenti e contatti in preparazione per i test di carico di stress e prestazioni.

Di seguito sono elencati i termini e le definizioni che è possibile trovare utili durante la lettura di questo argomento.

  - Unità organizzativa – unità organizzativa servizi di dominio Active Directory.

  - Federati/pool incrociato: utenti che saranno abilitati a comunicare con utenti di altri servizi di messaggistica istantanea, quali la rete MSN di servizi Internet, AOL® e Yahoo\!®.

  - Liste di distribuzione: gli oggetti in servizi di dominio Active Directory che contengono un elenco di utenti di servizi di dominio Active Directory, utilizzati per avviare comunicazioni con gruppi di persone.

  - Servizio informazioni percorso – il servizio Lync Server 2013 che, se abilitato e configurato per telefono, consente di recuperare il percorso fisico per i servizi Enhanced 9-1-1 (E9-1-1).

  - Numeri di telefono degli Stati Uniti: i numeri di telefono assegnati agli utenti, oltre all'URI SIP utilizzato per il routing delle chiamate in ingresso e in uscita e la ricerca di numeri inversi (inversa).

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Creare utenti e contatti utilizzando UserProvisioningTool. exe

Per creare utenti e contatti per la simulazione di carico, è necessario utilizzare lo strumento di provisioning utente di Lync Server. Lo strumento di provisioning degli utenti di Lync Server viene installato con il pacchetto dello strumento di prestazioni e stress di Lync Server. Assicurarsi che il programma di installazione del pacchetto (CapacityPlanningTool. msi) sia stato eseguito nel front end server o nel server Standard Edition. Avviare lo strumento di provisioning degli utenti di Lync Server eseguendo il file UserProvisioningTool. exe, che si trova in\\% InstalledDirectory% LyncStressAndPerfTool LyncStress, nel front end server o nel server Standard Edition.

<div>


> [!IMPORTANT]  
> Per poter eseguire UserProvisioningTool. exe, è necessario essere connessi come membri del gruppo di sicurezza Domain Admins. È necessario eseguire da questo contesto perché UserProvisioningTool. exe sarà la creazione e la configurazione di nuovi utenti di servizi di dominio Active Directory.



</div>

<div>


> [!NOTE]  
> Quando si crea un numero significativo di utenti (10.000 o più), eseguire UserProvisioningTool. exe da un computer high-end. Si noti che il controller di dominio verificherà un carico elevato anche durante la creazione degli utenti.



</div>

Quando si apre lo strumento di provisioning dell'utente di Lync Server, fare clic su **configurazione** e selezionare **Carica configurazione**. Per iniziare a configurare utenti e contatti, caricare il file predefinito incluso nel pacchetto SampleData. XML. Verranno precompilati i campi con i dati di esempio che dovranno essere rielaborati per il sistema. Se si dispone di un file XML preconfigurato che già contiene impostazioni personalizzate, caricare il file. Compilare i campi dello strumento di provisioning degli utenti di Lync Server, come descritto nelle sezioni seguenti.

![Scheda Creazione utente.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Scheda Creazione utente.")

Per configurare le opzioni del server, attenersi alla seguente procedura.

1.  Nell' **FQDN del pool Front End**Digitare il nome di dominio completo (FQDN) del server Standard Edition o del pool Front end in cui si desidera ospitare gli utenti.

2.  In **prefisso nome utente**Digitare un prefisso che si desidera utilizzare per creare i nomi utente a scopo di test.

3.  In **password**specificare una password che verrà applicata a tutti gli account utente di test.

4.  Nel **dominio SIP**, digitare il nome di dominio da utilizzare per gli URI SIP degli utenti di test (Uniform Resource Identifiers).

5.  In **dominio account**Digitare il nome di dominio del dominio di servizi di dominio Active Directory corrente, in cui si desidera creare gli utenti di test.

6.  In **unità organizzativa**, digitare il nome dell'unità organizzativa di servizi di dominio Active Directory in cui si desidera creare gli oggetti utente. Se l'unità organizzativa non esiste, verrà creata.

7.  In **codice area telefono**Digitare il codice area a tre cifre che verrà utilizzato per gli account utente di test. Assicurarsi che il codice area telefono non sia in conflitto con i codici di area di altri utenti in servizi di dominio Active Directory.

8.  Selezionare la casella di controllo **abilitata** per la voce se si desidera abilitare gli utenti di test per VoIP aziendale.

9.  In **numero di utenti**specificare il numero totale di utenti di test che si desidera creare.

10. In **Start index**specificare il numero iniziale che verrà utilizzato come suffisso per il prefisso del nome utente.

<div>

## <a name="create-users-button"></a>Pulsante Crea utenti

Quando si fa clic sul pulsante Crea utenti, verranno convalidati tutti i parametri di input.

  - Se si verificano errori di convalida, viene richiesto di correggere tali valori di input.

  - Se tutti i valori di input sono corretti, verrà avviata la creazione di utenti in servizi di dominio Active Directory. La barra di avanzamento verrà visualizzata nella parte inferiore del modulo. Si consiglia di non chiudere l'applicazione mentre la barra di stato è attiva.

La creazione di un utente è una procedura lenta. Possono essere necessari alcuni minuti. Se il numero di utenti è molto grande, il processo potrebbe richiedere anche alcune ore. Se gli utenti sono già presenti, vengono aggiornati con le modifiche apportate. È possibile verificare che gli utenti siano stati creati accedendo come uno degli utenti nell'intervallo. Utilizzare il prefisso utente, il numero di utente e il @sipDomain come nome utente (ad esempio, LyncUser10@contoso.net), insieme alla password specificata.

</div>

<div>

## <a name="delete-users-button"></a>Pulsante Elimina utenti

Quando si fa clic sul pulsante Elimina utenti, verranno convalidati tutti i parametri di input.

  - Se si verificano errori di convalida, viene richiesto di correggere tali valori di input.

  - Se tutti i valori di input sono corretti, inizierà a disabilitare ed eliminare gli utenti in servizi di dominio Active Directory. La barra di avanzamento verrà visualizzata nella parte inferiore del modulo. Si consiglia di non chiudere l'applicazione mentre la barra di stato è attiva.

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P>Sono supportati solo i numeri di telefono formattati negli Stati Uniti. I numeri di telefono vengono sempre assegnati agli utenti e tutti gli utenti creati da UserProvisioningTool. exe sono abilitati per VoIP aziendale. Tutti gli scenari che utilizzano il numero di telefono, ad esempio l'operatore automatico di conferenza o le chiamate di UC-PSTN, utilizzano questo numero di telefono per instradare correttamente le chiamate. Per questo motivo, ogni utente deve disporre di un numero di telefono univoco. Se è necessario creare due volte gli utenti, il comando avrà esito negativo a meno che non si utilizzi un codice area diverso o se gli utenti precedenti sono stati disabilitati utilizzando il cmdlet <STRONG>Disable-CsUser</STRONG> .</P>
> <LI>
> <P>Prima di creare contatti, è necessario prima completare la replica utente, eseguita dalla scheda utenti. Se gli utenti sono stati appena creati, è necessario attendere il completamento della replica di Lync Server e la compilazione degli account utente nel database. Se gli utenti non hanno completato la replica, verrà visualizzato un messaggio di errore. È possibile sapere quando gli utenti hanno finito di replicare se Lync Server 2013 front end Service è stato avviato o se il cmdlet <STRONG>Get-CsUser</STRONG> è stato eseguito correttamente nell'ultimo utente.</P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a>Scheda creazione contatti

La scheda creazione contatti consente di specificare i dettagli per i contatti degli utenti.

![Scheda creazione contatti.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Scheda creazione contatti.")

Per configurare i contatti degli utenti, attenersi alla seguente procedura.

1.  In media contatti per utente, specificare il numero medio di contatti da popolare negli elenchi di contatti per ciascuno degli utenti.

2.  Selezionare la casella di controllo fisso se si desidera creare un numero uguale di contatti per ogni utente. Se si desidera variare il numero di contatti creati per gli utenti, deselezionare la casella di controllo.

3.  In media gruppi di contatti per utente, specificare il numero di gruppi di contatti per utente. Questo numero deve essere inferiore ai contatti medi per utente.

4.  Nella percentuale contatti federati/pool incrociato specificare un numero compreso tra 0 e 100. Questa percentuale di contatti verrà creata con gli utenti federati.

5.  In prefisso utente federativo/pool incrociato specificare il nome utente per gli utenti federati che verranno aggiunti agli elenchi di contatti degli utenti locali.

6.  Nel dominio SIP dell'utente federata o di pool incrociato specificare il nome di dominio SIP degli utenti federati.
    
    <div>
    

    > [!NOTE]  
    > Nessuno degli utenti deve essere connesso quando si creano contatti.

    
    </div>

7.  Nella scheda Creazione utente, verificare che i parametri siano corretti. L'intervallo di utenti per il quale verranno creati i contatti viene ottenuto dalla scheda Creazione utente.

8.  Fare clic su Crea contatti per iniziare la creazione dei contatti. Questo processo può richiedere alcuni minuti. Al termine dell'operazione, verrà visualizzata una finestra di dialogo con il messaggio "Operation completed successfully". È possibile convalidare i contatti creati accedendo come utente creato dalla scheda Creazione utente.
    
    <div>
    

    > [!NOTE]  
    > Dopo la creazione dei contatti, questo strumento riavvierà tutti i Front End Server nel pool di destinazione. Potrebbe essere necessario più tempo (fino a 2 ore) per l'avvio dei Front End Server, a seconda del numero di contatti creati dall'operazione.

    
    </div>

</div>

<div>

## <a name="distribution-list"></a>Lista di distribuzione

Una delle caratteristiche dello strumento di sviluppo dello stress e delle prestazioni di Lync Server 2013 è quella di simulare la funzionalità di espansione della lista di distribuzione (DL) in Lync 2013. Se non si intende abilitare l'espansione DL in UserProvisioningTool, è possibile ignorare questo passaggio.

![Scheda Creazione elenco di distribuzione.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Scheda Creazione elenco di distribuzione.")

La scheda della lista di distribuzione consente di creare un DLs che lo strumento di stress e prestazioni utilizzerà per la funzionalità di espansione della lista di distribuzione. Prima di creare DLs, è necessario che Lync Server 2013 sia già installato. È necessario aver eseguito Lync Server 2013 ForestPrep. In caso contrario, gli attributi DL non sono presenti nello schema dei servizi di dominio Active Directory e lo strumento non sarà in grado di creare DLs.

Per configurare le liste di distribuzione, attenersi alla seguente procedura.

1.  In numero di liste di distribuzione specificare il numero totale di DLs che si desidera creare. (Si consiglia di iniziare con il doppio del numero di utenti). Sono numerati da 0 a n-1.

2.  Nel prefisso della lista di distribuzione, specificare il prefisso che avrà il DLs. Ad esempio, se si specifica 100 DLs e un prefisso di testDL, il DLs sarà denominato testDL0, testDL1 e così via, tramite testDL99.

3.  Nei membri minimi di un elenco dist specificare il numero minimo di utenti da aggiungere in ogni lista di distribuzione.

4.  Nei membri massimi di un elenco di dist. specificare il numero massimo di utenti da aggiungere in ogni lista di distribuzione.

<div>

## <a name="create-distribution-lists-button"></a>Pulsante Crea liste di distribuzione

Quando si fa clic sul pulsante Crea liste di distribuzione, lo strumento esegue una query nei servizi di dominio Active Directory per verificare se sono già presenti liste di distribuzione corrispondenti al prefisso e ai numeri. Lo strumento creerà solo quelli che non esistono già. Quando si aggiungono membri a queste liste di distribuzione appena create, verranno scelti gli utenti dall'intervallo specificato nella scheda Creazione utente.

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a>Scheda configurazione del servizio informazioni percorso

Una delle caratteristiche dello strumento Lync Server 2013 stress and performance è quella di generare file di configurazione fittizi per il servizio informazioni percorso. Il servizio informazioni percorso in genere non ha un impatto significativo sulle prestazioni nei server.

![Scheda configurazione del servizio informazioni percorso.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Scheda configurazione del servizio informazioni percorso.")

Se si sceglie di verificare questa funzionalità, è possibile inserire i valori indicati nel modulo e quindi fare clic sul pulsante genera file di configurazione LIS. Genererà file CSV denominati\_LIS subnet. csv,\_LIS switches. csv\_, LIS Ports. csv\_e LIS WAP. csv. È quindi possibile importare questi file CSV nel database LIS utilizzando il cmdlet **Set-CsLisSubnet** , il cmdlet **Set-CsLisSwitch** , il cmdlet **Set-CsLisPort** e il cmdlet **set-CsWirelessAccessPoint** , rispettivamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

