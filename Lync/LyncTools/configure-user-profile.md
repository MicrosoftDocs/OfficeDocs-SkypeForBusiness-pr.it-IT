---
title: Configurare il profilo utente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6615e283e0e426e738cd3cdaf714dd90f57b393e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a>Configurare il profilo utente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2018-10-11_

Gli strumenti inclusi nel pacchetto dello strumento di stress e prestazioni di Lync Server 2013 consentono di creare e configurare gli account utente di test che è possibile utilizzare per eseguire simulazioni di caricamento. Utilizzare lo strumento di creazione utente di Lync Server 2013 per creare gli utenti. Per informazioni dettagliate, vedere [creazione di utenti e contatti](create-users-and-contacts.md). Dopo aver creato gli utenti, configurare i profili utente utilizzando lo strumento di configurazione del caricamento di Lync Server 2013.

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a>Esecuzione dello strumento di configurazione del carico di Lync Server 2013

Per configurare i profili utente, eseguire lo strumento di configurazione del carico di Lync Server 2013 (UserProfileGenerator.exe) e compilare tutte le schede. UserProfileGenerator.exe genera una directory per ogni computer client che è necessario eseguire la simulazione. Ogni directory client include anche uno script per avviare tutte le istanze dello strumento di stress e prestazioni di Lync Server 2013 (LyncPerfTool.exe).

<div>


> [!IMPORTANT]  
> I valori specifici dell'utente specificati in UserProfileGenerator devono corrispondere ai valori specificati nello strumento di creazione degli utenti di Lync Server 2013 (UserProvisioningTool) per il pool.



</div>

Compilare i campi di ogni scheda dello strumento di configurazione del carico di Lync Server 2013, come descritto nelle sezioni seguenti.

<div>

## <a name="common-configuration"></a>Configurazione comune

La scheda **configurazione comune** dello strumento di configurazione del carico di Lync Server 2013 è illustrata nella figura seguente. Compilare i campi della scheda **configurazione comune** , come descritto nella procedura seguente.

![Scheda di configurazione comune.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Scheda di configurazione comune.")

1.  In **numero di macchine disponibili**Digitare o fare clic sul numero di computer che si desidera utilizzare per eseguire LyncPerfTool.exe. È consigliabile disporre di un solo computer per ogni 4.500 utenti da simulare. Questo numero può variare se si riduce il livello di carico o se si utilizza solo un sottoinsieme delle funzionalità disponibili. (I livelli di carico sono impostati nella scheda **scenari generali** ).

2.  In **prefisso per i nomi utente**, digitare il prefisso per il nome utente degli utenti. Per eseguire l'accesso, l'URI (Uniform Resource Identifier) sarà: \[ indice di avvio utente di UserPrefix... (Numero di utenti-1) \] @User dominio.

3.  In **password per tutti gli utenti**, immettere la password utilizzata per la creazione degli utenti. Se si lascia vuoto questo campo, il nome utente verrà utilizzato come password.

4.  In **Indice inizio utente**fare clic su o digitare l'indice del primo utente da configurare. È possibile configurare diversi intervalli per diversi tipi o livelli di carico, ma è necessario eseguire UserProfileGenerator.exe una volta per l'intervallo che si desidera configurare.

5.  In **numero di utenti**, fare clic su o digitare il numero totale di utenti che si intende configurare.

6.  In **dominio utente**Digitare il dominio utilizzato per l'URI SIP. Viene utilizzato per creare l'URI SIP di ogni utente per accedere al server Lync Server 2013 front end server o allo Standard Edition. Può essere diverso dal dominio account.

7.  In **dominio account**Digitare l'accesso al dominio di servizi di dominio Active Directory.

8.  Immettere il numero massimo di endpoint simultanei in **accedi al secondo (per istanza)** per il quale si desidera che lo strumento esegua l'accesso in tutti gli endpoint/utenti. La frequenza consigliata è \< = 2 per secondo/standard SKU Fe.

9.  In **FQDN del proxy di accesso o del pool**Digitare il nome di dominio completo (FQDN) del server a cui si desidera connettere i client. Se gli utenti accedono esternamente, specificare il proxy di accesso. Se gli utenti sono interni, specificare il nome di dominio completo del pool o del server Standard Edition.

10. In **porta**fare clic su o digitare la porta che si desidera venga utilizzata dagli utenti per SIP (il valore predefinito è 5061).

Per le impostazioni del server di rete esterno, specificare il **proxy di accesso o il nome FQDN del pool** e la **porta**. Queste impostazioni vengono utilizzate solo per la simulazione del caricamento degli endpoint esterni.

</div>

<div>

## <a name="general-scenarios"></a>Scenari generali

La scheda **scenari generali** dello strumento di configurazione del carico di Lync Server 2013 è illustrata nella figura seguente.

Configurare i livelli di carico e i parametri per ognuno degli scenari generali che si desidera eseguire oppure lasciare disabilitati.

![Scheda scenari generali.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Scheda scenari generali.")

1.  In **messaggistica istantanea**, che include peer-to-peer e conferenze, specificare il valore appropriato per il livello di carico.
    
    <div>
    

    > [!NOTE]  
    > I valori dei livelli di carico per tutti i campi (eccetto Location Information Services) sono <STRONG>disattivati</STRONG>, <STRONG>basso</STRONG>, <STRONG>medio</STRONG>, <STRONG>alto</STRONG>e <STRONG>personalizzato</STRONG>. Se è selezionata l'opzione basso, medio, alto o personalizzato, verranno generate configurazioni per ogni modalità e client. High provocherà la generazione del carico massimo supportato per il server, il valore medio corrisponde al 60% del carico e basso corrisponde al 30% del carico.

    
    </div>

2.  In audioconferenza, che è solo audioconferenza, specificare il valore appropriato per il **livello di carico**. Le chiamate peer-to-peer sono descritte nella sezione Voice Scenarios più avanti in questo argomento. Per abilitare MultiView, aprire la scheda **Avanzate** per tale modalità.

3.  In **condivisione applicazioni**specificare il valore appropriato per il livello di carico.

4.  In **collaborazione dati**, che include servizi di conferenza dati, specificare il valore appropriato per il livello di carico.

5.  Nell' **espansione della lista di distribuzione**, specificare il valore appropriato per il livello di carico. È inoltre necessario fare clic sul pulsante **Avanzate** e quindi compilare i campi con gli stessi valori configurati nella scheda **elenco di distribuzione** dello strumento di creazione utente di Lync Server (UserProvisioningTool.exe). Per informazioni dettagliate su questi campi, vedere [creare utenti e contatti](create-users-and-contacts.md)

6.  In **query Web**Rubrica, che è il servizio di ricerca rubrica (non il download dei file della rubrica), specificare il valore appropriato per il livello di carico. Per abilitare i download della Rubrica, fare clic sul pulsante **Avanzate** corrispondente e quindi impostare **EnableABSDownload** su true.

7.  In **Response Group Service**specificare il valore appropriato per il livello di carico. È inoltre necessario fare clic sul pulsante **Avanzate** corrispondente e quindi specificare gli URI dei Response Group già creati durante il provisioning degli agenti del servizio Response Group. È necessario specificare almeno un Response Group. Utilizzare il punto e virgola per separare più gruppi di risposta. Aggiornare RGSUriSuffixStartIndex e RGSUriSuffixEndIndex ai valori effettivi.

8.  In **Location Information Services**selezionare il valore appropriato per il livello di carico. Il livello di carico per i servizi di informazioni percorso deve essere **abilitato** o **disabilitato**.

<div>


> [!NOTE]  
> A ognuno degli scenari è associato un pulsante <STRONG>avanzato</STRONG> e un set di caselle di controllo che consentono varianti degli scenari. Strumenti ad <STRONG>hoc</STRONG> per generare una simulazione delle conferenze che verranno create per tutta l'ora. <STRONG>Grande conf</STRONG> significa che verrà simulato uno scenario di conferenza di grandi dimensioni. Mezzi <STRONG>esterni</STRONG> per simulare anche gli utenti esterni.<BR>Questi pulsanti e le caselle di controllo consentono l'accesso ai valori specifici di ogni scenario che modificherà il comportamento dello strumento di verifica dello stress e delle prestazioni di Lync Server 2013 (LyncPerfTool) e renderà possibile la personalizzazione. Per ogni scenario nella scheda <STRONG>scenari generali</STRONG> (ad eccezione di Location Information Services), se il valore del livello di carico è <STRONG>Custom</STRONG>, la frequenza di conversazione viene calcolata utilizzando il campo corrispondente nella finestra di dialogo <STRONG>Avanzate</STRONG> . Il nome del campo è diverso, a seconda dello scenario, ma la descrizione del campo diventerà "Nota: questo numero verrà utilizzato solo se è selezionata l'opzione personalizzato dal menu a discesa". In generale, i valori <STRONG>High</STRONG>, <STRONG>medium</STRONG>e <STRONG>low</STRONG> modificheranno i tassi di conversazione per ogni modalità in linea con il modello utente che rappresenta un bilanciamento di tutti gli scenari. Se è necessario modificare il livello di carico per modalità a causa di una differenza nell'utilizzo previsto, è consigliabile utilizzare un tasso di conversazione <STRONG>personalizzato</STRONG> .<BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a>Scenari vocali

La scheda **scenari vocali** dello strumento di configurazione del carico di Lync Server 2013 è illustrata nella figura seguente.

Utilizzare la scheda **scenari vocali** per configurare tutti gli scenari relativi alla voce.

![Scheda scenari vocali.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Scheda scenari vocali.")

1.  In **VoIP**fare clic sul pulsante **Avanzate** e quindi specificare i valori per i campi **PhoneAreaCode** e **LocationProfile** (dial plan). È inoltre necessario specificare un valore per il **livello di carico**. Se il livello di carico per **VoIP** e **gateway UC/PSTN** è abilitato, verrà sempre generato un file di configurazione della rete PSTN (Public Switched Telephone Network) a Unified Communications (UC) in grado di simulare le chiamate esterne.

2.  Nel **gateway UC/PSTN**, specificare un valore per il livello di carico. Se si seleziona un livello di carico diverso da **disabled**, è necessario specificare un valore per il **codice area PSTN** facendo clic sul pulsante **Aggiungi** in Mediation Server e PSTN. Verificare di disporre di una route configurata per il prefisso.
    
    <div>
    

    > [!NOTE]  
    > È possibile utilizzare il pannello di controllo di Lync Server o Lync Server Management Shell per verificare la configurazione della route vocale.

    
    </div>

3.  In **Operatore Conferenza**specificare un valore per il livello di carico. La selezione di un livello di carico (diverso da **disabled**) consentirà il campo **numero di telefono** . Immettere il numero di telefono dell'operatore automatico che si desidera utilizzare. Fare inoltre clic sul pulsante **Avanzate** e quindi specificare un valore per il campo **LocationProfile** .

4.  In **servizio parcheggio di chiamata**specificare il valore appropriato per il **livello di carico**.

5.  In **Mediation Server e PSTN**, per ogni Mediation Server che si desidera utilizzare, è necessario disporre di un simulatore PSTN separato. Dopo aver determinato il client che si intende utilizzare come simulatore, è necessario configurare il Mediation Server per instradare le chiamate al computer sulla porta del simulatore PSTN configurata. Fare clic su **Aggiungi** per configurare il valore per il Mediation Server.

<div>


> [!NOTE]  
> A ognuno degli scenari è associato un pulsante <STRONG>avanzato</STRONG> . Questi pulsanti consentono l'accesso a valori specifici di ogni scenario in cui verrà modificato il comportamento dello strumento di LyncPerfTool (stress and Performance Tool) di Lync Server 2013 e l'abilitazione della personalizzazione. Per ogni scenario nella scheda <STRONG>scenari vocali</STRONG> , se il valore del <STRONG>livello di carico</STRONG> è <STRONG>Custom</STRONG>, la frequenza di conversazione viene calcolata utilizzando il campo corrispondente nella finestra di dialogo <STRONG>Avanzate</STRONG> . Il nome del campo è diverso, a seconda dello scenario, ma la descrizione del campo diventerà "Nota: questo numero verrà utilizzato solo se è selezionata l'opzione personalizzato dal menu a discesa".



</div>

</div>

<div>

## <a name="reach"></a>Raggiungere

REACH è una nuova esperienza in Lync Server 2013 che supporta gli scenari di conferenza tramite il server Unified Communications Web API (UCWA) installato nel server front-end. La scheda **REACH** dello strumento di configurazione del carico di Lync Server 2013 è illustrata nella figura seguente.

Utilizzare la scheda **portata** per configurare tutti gli scenari relativi a REACH.

![Scheda REACH.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Scheda REACH.")

1.  Fare clic sul pulsante **Avanzate** accanto a **Impostazioni generali di accesso**. Impostare il campo **UcwaTargetServerUrl** sul server IP virtuale (VIP) del pool di server Director o sul VIP del pool Front end.

2.  In **condivisione applicazioni**, **collaborazione dati**e **messaggistica istantanea**selezionare il valore appropriato per il **livello di carico**.

<div>


> [!NOTE]  
> A ognuno degli scenari è associato un pulsante <STRONG>avanzato</STRONG> . Questi pulsanti consentono l'accesso a valori specifici di ogni scenario in cui verrà modificato il comportamento dello strumento di LyncPerfTool (stress and Performance Tool) di Lync Server 2013 e l'abilitazione della personalizzazione. Per ognuno degli scenari di portata, se il <STRONG>livello di carico</STRONG> è <STRONG>personalizzato</STRONG>, viene utilizzato il valore specificato nel campo <STRONG>ConversationsPerHour</STRONG> anziché quello predefinito.



</div>

La scheda **dispositivi mobili** consente di configurare tutti gli scenari relativi alla mobilità.

![Scheda dispositivi mobili.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Scheda dispositivi mobili.")

1.  Fare clic sul pulsante **Avanzate** accanto a **mobilità (UCWA)**. Impostare il campo **UcwaTargetServerUrl** sul server IP virtuale (VIP) del pool di server Director o sul VIP del pool Front end.

2.  In **presenza e \\ audio di messaggistica istantanea P2P**, selezionare il valore appropriato per il **livello di carico** per abilitare la simulazione dello scenario per dispositivi mobili.

<div>


> [!NOTE]  
> A ognuno degli scenari è associato un pulsante <STRONG>avanzato</STRONG> . Questi pulsanti consentono l'accesso a valori specifici di ogni scenario in cui verrà modificato il comportamento dello strumento di LyncPerfTool (stress and Performance Tool) di Lync Server 2013 e l'abilitazione della personalizzazione. Per ognuno degli scenari di portata, se il <STRONG>livello di carico</STRONG> è <STRONG>personalizzato</STRONG>, viene utilizzato il valore specificato nel campo <STRONG>ConversationsPerHour</STRONG> anziché quello predefinito.



</div>

</div>

<div>

## <a name="summary"></a>Riepilogo

La scheda **Riepilogo** dello strumento di configurazione del carico di Lync Server 2013 è illustrata nella figura seguente.

![Scheda Riepilogo.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Scheda Riepilogo.")

La scheda **Riepilogo** indica gli utenti da utilizzare per ogni scenario. È possibile configurare manualmente gli intervalli di numeri utente selezionando la casella di controllo **Abilita generazione di un intervallo di utenti personalizzato** e quindi facendo doppio clic sullo scenario nella tabella che include l' **intervallo di utenti** che si desidera personalizzare. Controllare (RunClient.bat) aggiungere il ritardo di accesso all'avvio, per includere i ritardi nei file batch generati in modo che corrispondano alla frequenza di accesso. Questa operazione è utile per impedire l'overload del server quando si effettua l'accesso a un numero elevato di utenti. Fare clic su **genera file**e selezionare la cartella in cui si desidera generare la configurazione. Una finestra di dialogo simile alla figura seguente comparirà quando i file sono stati creati correttamente.

![Conferma che i file sono stati creati.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Conferma che i file sono stati creati.")

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
