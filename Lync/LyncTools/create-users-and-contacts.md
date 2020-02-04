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
ms.openlocfilehash: b1463a7caaad2bcf36996eaac4bd47e2bab25e6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a>Creare utenti e contatti

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

È necessario usare lo strumento di provisioning degli utenti di Lync Server 2013 (UserProvisioningTool. exe) per creare utenti e contatti in preparazione per i test di stress e di carico delle prestazioni.

Ecco un elenco di termini e definizioni che potrebbero risultare utili durante la lettura di questo argomento.

  - Unità organizzativa: unità organizzativa servizi di dominio Active Directory.

  - Federati/pool incrociati: gli utenti che saranno abilitati a comunicare con gli utenti di altri servizi di messaggistica istantanea, come la rete MSN di Internet Services, AOL® e\!Yahoo®.

  - Liste di distribuzione: gli oggetti in servizi di dominio Active Directory che contengono un elenco di utenti di servizi di dominio Active Directory usati per avviare comunicazioni con gruppi di persone.

  - Servizio info posizione-il servizio Lync Server 2013 che, quando è abilitato e configurato per telefono, consente il recupero della posizione fisica per i servizi avanzati di 9-1-1 (E9-1-1).

  - Numeri di telefono statunitensi: i numeri di telefono assegnati agli utenti, oltre all'URI SIP usato per il routing delle chiamate in ingresso e in uscita e per la ricerca di numeri inversa (RNL).

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Creare utenti e contatti con UserProvisioningTool. exe

Per creare utenti e contatti per la simulazione di caricamento, devi usare lo strumento di provisioning utenti di Lync Server. Lo strumento di provisioning degli utenti di Lync Server viene installato con il pacchetto di strumenti di stress e prestazioni di Lync Server. Assicurarsi che il programma di installazione del pacchetto (CapacityPlanningTool. msi) sia stato eseguito nel server front-end o nel server Standard Edition. Avviare lo strumento di provisioning degli utenti di Lync Server eseguendo il file UserProvisioningTool. exe (che si trova in\\% InstalledDirectory% LyncStressAndPerfTool LyncStress) nel server front-end o nel server Standard Edition.

<div>


> [!IMPORTANT]  
> Per eseguire UserProvisioningTool. exe, è necessario avere effettuato l'accesso come membro del gruppo di sicurezza Domain Admins. È necessario eseguire da questo contesto perché UserProvisioningTool. exe sarà la creazione e la configurazione di nuovi utenti di servizi di dominio Active Directory.



</div>

<div>


> [!NOTE]  
> Quando si crea un numero significativo di utenti (10.000 o più), eseguire UserProvisioningTool. exe da un computer di fascia alta. Tieni presente che il controller di dominio avvertirà anche il carico elevato durante la creazione degli utenti.



</div>

Quando si apre lo strumento di provisioning degli utenti di Lync Server, fare clic su **configurazione** e selezionare **Carica configurazione**. Per iniziare a configurare utenti e contatti, caricare il file predefinito incluso nel pacchetto SampleData. XML. Verranno precompilati i campi con dati di esempio che è necessario rivedere per il sistema. Se si ha un file XML preconfigurato che contiene già impostazioni personalizzate, caricare il file. Compilare i campi dello strumento di provisioning degli utenti di Lync Server, come descritto nelle sezioni seguenti.

![Scheda User Creation.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Scheda User Creation.")

Per configurare le opzioni del server, eseguire la procedura seguente.

1.  In **FQDN del pool Front-End**Digitare il nome di dominio completo (FQDN) del server Standard Edition o del pool Front-end in cui si vogliono ospitare gli utenti.

2.  In **prefisso nome utente**Digitare un prefisso che si vuole usare per creare nomi utente a scopo di test.

3.  In **password**specificare una password che verrà applicata a tutti gli account utente di test.

4.  Nel **dominio SIP**Digitare il nome di dominio da usare per gli URI SIP degli utenti di test (Uniform Resource Identifier).

5.  In **dominio account**Digitare il nome di dominio del dominio di servizi di dominio Active Directory corrente in cui si desidera creare gli utenti di test.

6.  In **unità organizzativa**Digitare il nome dell'unità organizzativa servizi di dominio Active Directory in cui si desidera creare gli oggetti utente. Se l'unità organizzativa non esiste, verrà creata.

7.  Nel **codice area telefono**Digitare il codice di area a tre cifre che verrà usato per gli account utente di test. Assicurarsi che il codice dell'area telefonica non sia in conflitto con i codici di area di altri utenti in servizi di dominio Active Directory.

8.  Selezionare la casella di controllo **abilitata** per la voce se si vuole abilitare gli utenti di test per VoIP aziendale.

9.  In **numero di utenti**specificare il numero totale di utenti di test che si desidera creare.

10. In **Avvia Indice**specificare il numero iniziale che verrà usato come suffisso per il prefisso del nome utente.

<div>

## <a name="create-users-button"></a>Pulsante Crea utenti

Quando si fa clic sul pulsante Crea utenti, verranno convalidati tutti i parametri di input.

  - In caso di errori di convalida, verrà chiesto di correggere i valori di input.

  - Se tutti i valori di input sono corretti, inizierà a creare utenti in servizi di dominio Active Directory. Nella parte inferiore del modulo verrà visualizzata una barra di stato. Ti consigliamo di non chiudere l'applicazione mentre l'indicatore di stato è attivo.

La creazione di un utente è un processo lento. Possono essere necessarie diversi minuti. Se il numero di utenti è molto grande, il processo potrebbe richiedere anche qualche ora. Se gli utenti sono già presenti, verranno aggiornati con le eventuali modifiche. Puoi verificare che gli utenti siano stati creati effettuando l'accesso come uno degli utenti nell'intervallo. Usare il prefisso utente, il numero utente e @sipDomain come nome utente, ad esempio LyncUser10@contoso.net, insieme alla password specificata.

</div>

<div>

## <a name="delete-users-button"></a>Pulsante Elimina utenti

Quando si fa clic sul pulsante Elimina utenti, verranno convalidati tutti i parametri di input.

  - In caso di errori di convalida, verrà chiesto di correggere i valori di input.

  - Se tutti i valori di input sono corretti, verrà avviata la disattivazione ed eliminazione degli utenti in servizi di dominio Active Directory. Nella parte inferiore del modulo verrà visualizzata una barra di stato. Ti consigliamo di non chiudere l'applicazione mentre l'indicatore di stato è attivo.

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P>Sono supportati solo i numeri di telefono formattati negli Stati Uniti. I numeri di telefono vengono sempre assegnati agli utenti e tutti gli utenti creati da UserProvisioningTool. exe sono abilitati per VoIP aziendale. Qualsiasi scenario che usa il numero di telefono, ad esempio l'operatore automatico di conferenza o le chiamate UC-PSTN, usa questo numero di telefono per instradare correttamente le chiamate. Per questo motivo, ogni utente deve avere un numero di telefono univoco. Se è necessario creare due volte gli utenti, il comando avrà esito negativo a meno che non si usi un codice di area diverso o se gli utenti precedenti sono stati disabilitati usando il cmdlet <STRONG>Disable-CsUser</STRONG> .</P>
> <LI>
> <P>Prima di creare contatti, è necessario prima di tutto eseguire la replica dell'utente, eseguita dalla scheda utenti. Se gli utenti sono stati appena creati, è necessario attendere il completamento della replica di Lync Server e la compilazione degli account utente nel database. Se gli utenti non hanno terminato la replica, verrà visualizzato un messaggio di errore. Sarà possibile sapere quando gli utenti hanno terminato la replica se il servizio front-end di Lync Server 2013 è stato avviato oppure eseguendo correttamente il cmdlet <STRONG>Get-CsUser</STRONG> sull'ultimo utente.</P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a>Scheda creazione contatti

La scheda creazione contatti consente di specificare i dettagli per i contatti degli utenti.

![Scheda Contacts Creation.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Scheda Contacts Creation.")

Per configurare i contatti degli utenti, seguire questa procedura.

1.  In contatti medi per utente, specificare il numero medio di contatti da popolare negli elenchi di contatti per ognuno degli utenti.

2.  Selezionare la casella di controllo fissa se si vuole creare un numero uguale di contatti per ogni utente. Se si vuole variare il numero di contatti creati per gli utenti, deselezionare la casella di controllo.

3.  In media gruppi di contatti per utente specificare il numero di gruppi di contatti per ogni utente. Questo numero deve essere inferiore ai contatti medi per ogni utente.

4.  Nella percentuale di contatti federativi/di pool incrociati specificare un numero compreso tra 0 e 100. Questa percentuale di contatti verrà creata con gli utenti federati.

5.  Nel prefisso utente federativo/Cross pool specificare il nome utente per gli utenti federati che verranno aggiunti agli elenchi di contatti degli utenti locali.

6.  Nel dominio SIP utente federativo/pool incrociato specificare il nome di dominio SIP degli utenti federati.
    
    <div>
    

    > [!NOTE]  
    > Nessuno degli utenti deve essere connesso durante la creazione di contatti.

    
    </div>

7.  Nella scheda Creazione utente verificare che i parametri siano corretti. L'intervallo di utenti per cui verranno creati i contatti viene ottenuto dalla scheda Creazione utente.

8.  Fare clic su Crea contatti per iniziare la creazione del contatto. Questo processo può richiedere diversi minuti. Al termine, verrà visualizzata una finestra di dialogo con il messaggio "operazione completata correttamente". Puoi convalidare i contatti creati eseguendo l'accesso come utente creato dalla scheda Creazione utente.
    
    <div>
    

    > [!NOTE]  
    > Dopo aver creato i contatti, questo strumento ricomincerà tutti i server front-end nel pool di destinazione. In base al numero di contatti creati da questa operazione, potrebbe essere necessario più tempo (fino a 2 ore) per avviare i server front-end.

    
    </div>

</div>

<div>

## <a name="distribution-list"></a>Elenco di distribuzione

Una delle caratteristiche dello strumento di sviluppo dello stress e delle prestazioni di Lync Server 2013 consiste nel simulare la caratteristica di espansione della lista di distribuzione (DL) in Lync 2013. Se non si vuole abilitare l'espansione DL in UserProvisioningTool, è possibile ignorare questo passaggio.

![Scheda Distribution List Creation.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Scheda Distribution List Creation.")

La scheda lista di distribuzione consente di creare un DLs che lo strumento stress e prestazioni userà per la caratteristica di espansione della lista di distribuzione. Prima di creare DLs, Lync Server 2013 deve essere già installato. È necessario che sia stato eseguito Lync Server 2013 ForestPrep. In caso contrario, gli attributi DL non sono presenti nello schema Servizi di dominio Active Directory e lo strumento non sarà in grado di creare DLs.

Per configurare le liste di distribuzione, seguire questa procedura.

1.  In numero di liste di distribuzione specificare il numero totale di DLs che si vuole creare. (Ti consigliamo di iniziare con il doppio del numero di utenti). Sono numerati da 0 a n-1.

2.  Nel prefisso della lista di distribuzione specificare il prefisso che avrà il DLs. Ad esempio, se specifichi 100 DLs e un prefisso di testDL, il DLs sarà denominato testDL0, testDL1 e così via, attraverso testDL99.

3.  In membri minimi in un elenco dist. specificare il numero minimo di utenti da aggiungere in ogni lista di distribuzione.

4.  In massimo membri in un elenco dist. specificare il numero massimo di utenti da aggiungere in ogni lista di distribuzione.

<div>

## <a name="create-distribution-lists-button"></a>Pulsante Crea liste di distribuzione

Quando si fa clic sul pulsante Crea liste di distribuzione, lo strumento esegue una query in servizi di dominio Active Directory per verificare se sono già presenti elenchi di distribuzione corrispondenti al prefisso e ai numeri. Lo strumento creerà solo quelli che non sono già presenti. Quando si aggiungono membri a queste liste di distribuzione appena create, verranno scelti gli utenti dall'intervallo specificato nella scheda Creazione utente.

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a>Scheda configurazione del servizio info posizione

Una delle caratteristiche dello strumento di esecuzione dello stress e delle prestazioni di Lync Server 2013 è la creazione di file di configurazione fittizi per il servizio informazioni sulla posizione. Il servizio informazioni sulla posizione in genere non ha un impatto significativo sulle prestazioni nei server.

![Scheda Location Info Service Config.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Scheda Location Info Service Config.")

Se si sceglie di testare questa caratteristica, è possibile inserire i valori menzionati nel modulo e quindi fare clic sul pulsante genera file di configurazione LIS. Genererà file CSV denominati\_LIS subnet. csv,\_LIS switches. csv\_, LIS Ports. csv\_e LIS WAP. csv. È quindi possibile importare questi file CSV nel database LIS usando il cmdlet **Set-CsLisSubnet** , il cmdlet **Set-CsLisSwitch** , il cmdlet **Set-CsLisPort** e il cmdlet **set-CsWirelessAccessPoint** , rispettivamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

