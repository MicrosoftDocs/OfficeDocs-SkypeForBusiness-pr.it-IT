---
title: Configurare il profilo utente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2441fe97bb57ffdf0f6200f1201e192bfc6bf14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a>Configurare il profilo utente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2018-10-11_

Gli strumenti inclusi nel pacchetto dello strumento di stress e prestazioni di Lync Server 2013 consentono di creare e configurare gli account utente di test che è possibile usare per eseguire le simulazioni di caricamento. Usare lo strumento di creazione dell'utente di Lync Server 2013 per creare gli utenti. Per informazioni dettagliate, vedere [creare utenti e contatti](create-users-and-contacts.md). Dopo aver creato gli utenti, configurare i profili utente usando lo strumento di configurazione del caricamento di Lync Server 2013.

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a>Eseguire lo strumento di configurazione del caricamento di Lync Server 2013

Per configurare i profili utente, eseguire lo strumento di configurazione del carico di Lync Server 2013 (UserProfileGenerator. exe) e compilare tutte le schede. UserProfileGenerator. exe genera una directory per ogni computer client necessario per eseguire la simulazione. Ogni directory client include anche uno script per avviare tutte le istanze dello strumento di ottimizzazione dello stress e delle prestazioni di Lync Server 2013 (LyncPerfTool. exe).

<div>


> [!IMPORTANT]  
> I valori specifici dell'utente specificati in UserProfileGenerator devono corrispondere ai valori specificati nello strumento di creazione degli utenti di Lync Server 2013 (UserProvisioningTool) per il pool.



</div>

Compilare i campi di ogni scheda dello strumento di configurazione del carico di Lync Server 2013, come descritto nelle sezioni seguenti.

<div>

## <a name="common-configuration"></a>Configurazione comune

Nella figura seguente è illustrata la scheda **configurazione comune** dello strumento di configurazione del carico di Lync Server 2013. Compilare i campi della scheda **configurazione comune** , come descritto nella procedura seguente.

![Scheda Common Configuration.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Scheda Common Configuration.")

1.  In **numero di macchine disponibili**Digitare o fare clic sul numero di computer che si desidera utilizzare per eseguire LyncPerfTool. exe. Ti consigliamo di avere un computer per ogni utente di 4.500 che dovrai simulare. Questo numero può variare se si riduce il livello di carico o se si usa solo un sottoinsieme delle funzionalità disponibili. (I livelli di carico sono impostati nella scheda **scenari generali** ).

2.  In **prefisso per i nomi utente**Digitare il prefisso per il nome utente degli utenti. Per eseguire l'accesso, l'URI (Uniform Resource Identifier) sarà: Indice\[di inizio dell'utente di UserPrefix... (Numero di utenti-1) \]@User dominio.

3.  Nella **password per tutti gli utenti**immettere la password usata per la creazione degli utenti. Se si lascia vuoto questo campo, il nome utente verrà usato come password.

4.  Nell' **Indice Start utente**fare clic o digitare l'indice del primo utente da configurare. È possibile configurare intervalli diversi per diversi tipi o livelli di carico, ma è necessario eseguire UserProfileGenerator. exe una volta per l'intervallo che si vuole configurare.

5.  In **numero di utenti**fare clic o digitare il numero totale di utenti che si vuole configurare.

6.  In **dominio utente**Digitare il dominio usato per l'URI SIP. Viene usato per creare l'URI SIP di ogni utente per accedere al server front end server o Standard Edition di Lync Server 2013. Può essere diverso dal dominio dell'account.

7.  In **dominio account**Digitare l'accesso al dominio servizi di dominio Active Directory.

8.  Immettere il numero massimo di endpoint simultanei in **accesso al secondo (per istanza)** per cui si vuole che lo strumento acceda a tutti gli endpoint/utenti. La frequenza consigliata \<è = 2 per secondo/standard SKU Fe.

9.  In **FQDN del proxy o del pool di Access**Digitare il nome di dominio completo (FQDN) del server a cui si vuole connettere i client. Se gli utenti accedono esternamente, specificare il proxy di accesso. Se gli utenti sono interni, specificare il nome di dominio completo del pool o del server Standard Edition.

10. In **porta**fare clic o digitare la porta che si vuole che gli utenti usino per SIP (il valore predefinito è 5061).

Per le impostazioni del server di rete esterno, specificare il **proxy di accesso o il nome FQDN del pool** e la **porta**. Queste impostazioni vengono usate solo per la simulazione di caricamento degli endpoint esterni.

</div>

<div>

## <a name="general-scenarios"></a>Scenari generali

Nella figura seguente è illustrata la scheda **scenari generali** dello strumento di configurazione del carico di Lync Server 2013.

Configurare i livelli di carico e i parametri per ognuno degli scenari generali che si desidera eseguire o uscire da Disabled.

![Scheda General Scenarios.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Scheda General Scenarios.")

1.  Nella **messaggistica istantanea**, che include peer-to-peer e conferenze, specificare il valore appropriato per il livello di carico.
    
    <div>
    

    > [!NOTE]  
    > I valori del livello di caricamento per tutti i campi (ad eccezione dei servizi di informazioni sulla posizione) sono <STRONG>disabilitati</STRONG>, <STRONG>Bassi</STRONG>, <STRONG>medi</STRONG>, <STRONG>alti</STRONG>e <STRONG>personalizzati</STRONG>. Quando è selezionata l'opzione bassa, media, alta o personalizzata, le configurazioni verranno generate per ogni modalità e client. Alto comporterà il carico massimo supportato da generare per il server, media corrisponde a 60% del carico e basso corrisponde al 30% del carico.

    
    </div>

2.  In **servizi di audioconferenza,** che è solo audioconferenza, specificare il valore appropriato per il livello di carico. Le chiamate peer-to-peer sono descritte nella sezione scenari vocali più avanti in questo argomento. Per abilitare MultiView, aprire la scheda **Avanzate** per tale modalità.

3.  In **condivisione applicazioni**specificare il valore appropriato per il livello di carico.

4.  In **collaborazione**con i dati, che include i servizi di conferenza dati, specificare il valore appropriato per il livello di carico.

5.  In **espansione elenco di distribuzione**specificare il valore appropriato per il livello di carico. Devi anche fare clic sul pulsante **Avanzate** e quindi compilare i campi con gli stessi valori configurati nella scheda lista di **distribuzione** dello strumento di creazione degli utenti di Lync Server (UserProvisioningTool. exe). Per informazioni dettagliate su questi campi, vedere [creare utenti e contatti](create-users-and-contacts.md)

6.  In **query Web**Rubrica, che è il servizio di ricerca rubrica (non il download di file della rubrica), specificare il valore appropriato per il livello di carico. Per abilitare i download della Rubrica, fare clic sul pulsante **Avanzate** corrispondente e quindi impostare **EnableABSDownload** su true.

7.  In **Response Group Service**specificare il valore appropriato per il livello di carico. Devi anche fare clic sul pulsante **avanzato** corrispondente e quindi specificare gli URI dei gruppi di risposte già creati durante il provisioning degli agenti del servizio Response Group. Devi specificare almeno un gruppo di risposte. Usare i punti e virgola per separare più gruppi di risposta. Aggiornare RGSUriSuffixStartIndex e RGSUriSuffixEndIndex ai valori effettivi.

8.  In **Servizi informazioni sulla posizione**selezionare il valore appropriato per il livello di carico. Il livello di carico per i servizi di informazioni sulla posizione deve essere **abilitato** o **disabilitato**.

<div>


> [!NOTE]  
> Ogni scenario include un pulsante <STRONG>avanzato</STRONG> che si trova accanto a esso e un set di caselle di controllo che consentono varianti degli scenari. Mezzi <STRONG>ad hoc</STRONG> per generare una simulazione di conferenze che verranno create per tutta l'ora. <STRONG>Grande conf</STRONG> significa che verrà simulato lo scenario di conferenza di grandi dimensioni. Mezzi <STRONG>esterni</STRONG> per simulare anche utenti esterni.<BR>I pulsanti e le caselle di controllo consentono l'accesso a valori specifici di ogni scenario che cambierà il comportamento dello strumento di LyncPerfTool (stress and performance) di Lync Server 2013 e renderanno possibile la personalizzazione. Per ogni scenario nella scheda <STRONG>scenari generali</STRONG> (ad eccezione di servizi di informazioni sulla posizione), se il valore del livello di carico è <STRONG>personalizzato</STRONG>, la frequenza di conversazione verrà calcolata usando il campo corrispondente nella finestra di dialogo <STRONG>Avanzate</STRONG> . Il nome del campo è diverso, a seconda dello scenario, ma la descrizione del campo verrà visualizzata "Nota: questo numero verrà usato solo se è selezionato personalizzato dal menu a discesa." In generale, i valori <STRONG>alto</STRONG>, <STRONG>medio</STRONG>e <STRONG>basso</STRONG> altereranno i tassi di conversazione per modalità in linea con il modello utente che rappresenta un bilanciamento di tutti gli scenari. Se è necessario modificare il livello di carico per modalità a causa di una differenza nell'utilizzo previsto, è consigliabile usare una frequenza di conversazione <STRONG>personalizzata</STRONG> .<BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a>Scenari vocali

Nella figura seguente è illustrata la scheda **scenari vocali** dello strumento di configurazione del carico di Lync Server 2013.

Usare la scheda **scenari vocali** per configurare tutti gli scenari relativi alla voce.

![Scheda Voice Scenarios.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Scheda Voice Scenarios.")

1.  In **VoIP**fare clic sul pulsante **Avanzate** e quindi specificare i valori per i campi **PhoneAreaCode** e **LocationProfile** (dial plan). Devi anche specificare un valore per il **livello di carico**. Se il livello di carico per **VoIP** e **gateway UC/PSTN** è abilitato, viene sempre generato un file di configurazione PSTN (Public Switched Telephone Network) to Unified Communications (UC) che simula le chiamate esterne.

2.  Nel **gateway UC/PSTN**specificare un valore per il livello di carico. Se si seleziona un livello di carico diverso da **disabled**, è necessario specificare un valore per il **codice dell'area PSTN** facendo clic sul pulsante **Aggiungi** in Mediation Server e PSTN. Verificare di avere una route configurata per il prefisso.
    
    <div>
    

    > [!NOTE]  
    > È possibile usare il pannello di controllo di Lync Server o Lync Server Management Shell per verificare la configurazione della route vocale.

    
    </div>

3.  In **Operatore Conferenza**specificare un valore per il livello di carico. La selezione di un livello di carico (diverso da **disabled**) consentirà il campo **numero di telefono** . Immettere il numero di telefono dell'operatore automatico che si vuole usare. Fai anche clic sul pulsante **Avanzate** e quindi specifica un valore per il campo **LocationProfile** .

4.  In **servizio parcheggio di chiamata**specificare il valore appropriato per il **livello di carico**.

5.  In **Mediation Server e PSTN**, per ogni Mediation Server che si vuole usare, è necessario disporre di un simulatore PSTN distinto. Dopo aver determinato il client che si vuole usare come simulatore, è necessario configurare il Mediation Server per instradare le chiamate al computer nella porta di simulazione PSTN configurata. Fare clic su **Aggiungi** per configurare il valore per il Mediation Server.

<div>


> [!NOTE]  
> Ogni scenario contiene un pulsante <STRONG>avanzato</STRONG> che si trova accanto. Questi pulsanti consentono l'accesso a valori specifici di ogni scenario che cambierà il comportamento dello strumento di LyncPerfTool (stress and Performance Tool) di Lync Server 2013 e consentirà la personalizzazione. Per ogni scenario della scheda <STRONG>scenari vocali</STRONG> , se il valore del <STRONG>livello di carico</STRONG> è <STRONG>personalizzato</STRONG>, la frequenza di conversazione verrà calcolata utilizzando il campo corrispondente nella finestra di dialogo <STRONG>Avanzate</STRONG> . Il nome del campo è diverso, a seconda dello scenario, ma la descrizione del campo verrà visualizzata "Nota: questo numero verrà usato solo se è selezionato personalizzato dal menu a discesa."



</div>

</div>

<div>

## <a name="reach"></a>Raggiungere

REACH è una nuova esperienza in Lync Server 2013 che supporta scenari di conferenza tramite il server UCWA (Unified Communications Web API) installato nel server front-end. La scheda **REACH** dello strumento di configurazione del carico di Lync Server 2013 è illustrata nella figura seguente.

Usare la scheda **REACH** per configurare tutti gli scenari correlati a REACH.

![Scheda Reach.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Scheda Reach.")

1.  Fare clic sul pulsante **Avanzate** accanto a **Impostazioni generali di REACH**. Impostare il campo **UcwaTargetServerUrl** sul Virtual IP del pool di Director (VIP) o sul pool VIP di front-end.

2.  Nella **condivisione delle applicazioni**, nella **collaborazione ai dati**e nella **messaggistica istantanea**selezionare il valore appropriato per il **livello di carico**.

<div>


> [!NOTE]  
> Ogni scenario contiene un pulsante <STRONG>avanzato</STRONG> che si trova accanto. Questi pulsanti consentono l'accesso a valori specifici di ogni scenario che cambierà il comportamento dello strumento di LyncPerfTool (stress and Performance Tool) di Lync Server 2013 e consentirà la personalizzazione. Per ogni scenario REACH, se il livello di <STRONG>carico</STRONG> è <STRONG>personalizzato</STRONG>, viene usato il valore specificato nel campo <STRONG>ConversationsPerHour</STRONG> al posto di quello predefinito.



</div>

Usare la scheda **mobilità** per configurare tutti gli scenari relativi alla mobilità.

![Scheda Mobility.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Scheda Mobility.")

1.  Fare clic sul pulsante **Avanzate** accanto a **mobilità (UCWA)**. Impostare il campo **UcwaTargetServerUrl** sul Virtual IP del pool di Director (VIP) o sul pool VIP di front-end.

2.  In **presenza e audio di messaggistica\\istantanea P2P**Selezionare il valore appropriato per il **livello di carico** per abilitare la simulazione dello scenario di mobilità.

<div>


> [!NOTE]  
> Ogni scenario contiene un pulsante <STRONG>avanzato</STRONG> che si trova accanto. Questi pulsanti consentono l'accesso a valori specifici di ogni scenario che cambierà il comportamento dello strumento di LyncPerfTool (stress and Performance Tool) di Lync Server 2013 e consentirà la personalizzazione. Per ogni scenario REACH, se il livello di <STRONG>carico</STRONG> è <STRONG>personalizzato</STRONG>, viene usato il valore specificato nel campo <STRONG>ConversationsPerHour</STRONG> al posto di quello predefinito.



</div>

</div>

<div>

## <a name="summary"></a>Riepilogo

La scheda **Riepilogo** dello strumento di configurazione del carico di Lync Server 2013 è illustrata nella figura seguente.

![Scheda Summary.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Scheda Summary.")

La scheda **Riepilogo** indica gli utenti da usare per ogni scenario. È possibile configurare manualmente gli intervalli di numeri degli utenti selezionando la casella di controllo Abilita generazione di intervalli di **utenti personalizzati** e facendo doppio clic sullo scenario nella tabella che contiene l' **intervallo di utenti** che si vuole personalizzare. Selezionare (RunClient. bat) il ritardo di accesso per includere i ritardi nei file batch generati in modo che corrispondano alla frequenza di accesso. Questa operazione è utile per impedire l'overload del server quando si esegue l'accesso a un numero elevato di utenti. Fare clic su **genera file**e selezionare la cartella in cui si vuole generare la configurazione. Quando i file sono stati creati correttamente, verrà visualizzata una finestra di dialogo simile alla figura seguente.

![Conferma della creazione dei file.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Conferma della creazione dei file.")

</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare utenti e contatti](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
