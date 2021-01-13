---
title: Utilizzo dello strumento di sollecito e prestazioni di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/13/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: Per eseguire lo strumento sollecitazione e prestazioni di Skype for Business Server 2015, è necessario essere in grado di gestire sia gli utenti, i contatti e i profili utente, configurare lo strumento per l'esecuzione e quindi esaminare l'output o i risultati che sono stati prodotti dallo strumento.
ms.openlocfilehash: e008a85d22753a4e649da8501bd387675bb9b536
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814946"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Utilizzo dello strumento di sollecito e prestazioni di Skype for Business Server 2015
 
Per eseguire lo strumento sollecitazione e prestazioni di Skype for Business Server 2015, è necessario essere in grado di gestire sia gli utenti, i contatti e i profili utente, configurare lo strumento per l'esecuzione e quindi esaminare l'output o i risultati che sono stati prodotti dallo strumento.
  
Sono disponibili quattro aree per l'esecuzione dello strumento di stress e prestazioni di Skype for Business Server 2015 (il file eseguibile è LyncPerfTool.exe):
  
- [Creare utenti e contatti](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configurare il profilo utente](using-the-tool.md#BKMK_UserProfile)
    
- [Eseguire LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpretazione dei risultati](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Creare utenti e contatti
<a name="BKMK_CreateUsersAndContacts"> </a>

È necessario utilizzare lo strumento di provisioning degli utenti di Skype for Business Server 2015 (SB 2015) (UserProvisioningTool.exe) per creare utenti e contatti per i test di stress e prestazioni.
  
Si tratta di un elenco di termini utili che potrebbero essere utili durante la lettura degli argomenti:
  
- **Unità organizzativa** -unità organizzativa di servizi di dominio Active Directory (ad DS).
    
- **Federati/pool incrociato** -utenti in grado di comunicare con utenti provenienti da altri servizi di messaggistica istantanea.
    
- **Liste di distribuzione** -o DLS. Si tratta di oggetti in servizi di dominio Active Directory che contengono un elenco di utenti di servizi di dominio Active Directory. Sono utilizzati per facilitare le comunicazioni tra gruppi di persone.
    
- **Service info location** -il servizio Skype for Business Server 2015 che, quando è abilitato e configurato per telefono, consente il recupero del percorso fisico per i servizi Enhanced 911 (E911).
    
- **Numeri di telefono degli Stati Uniti** -numeri di telefono assegnati all'utente oltre all'URI SIP utilizzato per il routing delle chiamate in ingresso e in uscita nella ricerca di numeri inverso (inversa).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Creare utenti e contatti tramite UserProvisioningTool.exe

> [!NOTE]
> Prima di iniziare, accertarsi di aver eseguito l'accesso come membro del gruppo di sicurezza Domain Admins per eseguire questo strumento. È necessario eseguire questa operazione, perché si sta creando utenti di Active Directory. 
  
Per creare utenti e contatti per la simulazione di carico, è necessario utilizzare lo strumento di provisioning utente di Skype for Business Server.
  
Lo **strumento di provisioning degli utenti di Skype for Business Server** viene installato con il pacchetto dello **strumento di stress e prestazioni di Skype for Business Server** . Assicurarsi che il programma di installazione del pacchetto (CapacityPlanningTool.msi) sia stato eseguito nel front end server o nel server Standard Edition che si desidera testare.
  
È possibile avviare lo strumento di provisioning degli utenti di Skype for Business Server eseguendo il file UserProvisioningTool.exe (che si trova in% InstalledDirectory% LyncStressAndPerfTool \ LyncStress) nel front end server o nel server Standard Edition.
  
> [!IMPORTANT]
> Quando si crea un numero elevato di utenti (ad esempio, 10.000 o più), eseguire il UserProvisioningTool.exe. Sarà necessario eseguire questa operazione perché lo strumento sarà la creazione e la configurazione di  *nuovi*  utenti di Active Directory.
  
Quando si apre lo strumento di provisioning dell'utente, fare clic su configurazione e selezionare la configurazione del caricamento. 
  
Per iniziare a configurare utenti e contatti, caricare il file predefinito incluso nel pacchetto, denominato "SampleData.xml". Verranno precompilati i campi con i dati di esempio che dovranno essere modificati per renderli rilevanti per la distribuzione.
  
Se si dispone di un file XML preconfigurato che già contiene le impostazioni personalizzate, è possibile caricare il file. Compilare i campi dello strumento di provisioning degli utenti, come descritto nelle sezioni seguenti.
  
### <a name="to-configure-server-options"></a>Per configurare le opzioni del server:

1. Nel campo **FQDN del pool Front End** Digitare il nome di dominio completo (FQDN) del server Standard Edition o il pool Front end in cui si desidera ospitare gli utenti.
    
2. Nel campo **prefisso nome utente** Digitare un prefisso che si desidera utilizzare per arrestare i nomi utente a scopo di testing, ad esempio "testuser".
    
3. Nel campo **password** , digitare una password che verrà utilizzata in tutti gli account utente di test.
    
4. Nel campo **dominio account** Digitare il nome di dominio del dominio di Active Directory corrente (quello in cui si desidera creare gli utenti di test).
    
5. Nel campo **unità organizzativa** , digitare il nome del dominio di Active Directory in cui si desidera creare gli utenti di test. Se l'unità organizzativa non esiste già, verrà creata per l'utente.
    
6. Nel campo prefisso **telefonico** Digitare il codice area a tre cifre da utilizzare in tutti gli account utente di test. Accertarsi che il prefisso scelto non sia in conflitto con i codici area di altri utenti in Active Directory.
    
7. Fare clic per selezionare la casella di controllo **abilitata** per la voce, se si desidera abilitare gli utenti di test per VoIP aziendale.
    
8. Nel campo **numero di utenti** assegnare il numero totale di utenti di test che si desidera creare.
    
9. Nel campo **inizio indice** , assegnare il numero iniziale che verrà utilizzato come suffisso per il prefisso del nome utente (ad esempio, il prefisso è "testuser" e il primo nome si concluderà con "0" nell'esempio seguente).
    
     ![Strumento di provisioning degli utenti che mostra la scheda Creazione utente.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Pulsante Crea utenti

Quando si fa clic sul pulsante **Crea utenti** , i parametri di input immessi sono convalidati. Se si verificano errori di convalida, verrà richiesto di correggerli. In alternativa, se tutti i valori sono corretti, gli utenti inizieranno a essere visualizzati in Active Directory (nell'unità organizzativa specificata). Verrà visualizzata una barra di avanzamento nella parte inferiore dello strumento durante l'esecuzione. Non chiudere l'applicazione mentre la barra di stato è attiva.
  
La creazione degli utenti richiede tempo, quindi pianificare di conseguenza. Questo processo può richiedere da diversi minuti a pochi utenti, a poche ore, per un numero elevato di utenti.
  
Se non si ha accesso al controller di dominio AD nell'ambiente di testing, è comunque possibile convalidare la creazione dell'utente accedendo come uno degli utenti nell'intervallo di utenti specificati per la creazione. Ricordarsi di usare il prefisso e il suffisso, insieme alla @sipDomain come nome utente. Di seguito è riportato un esempio:  <em>TestUser20@contoso.net</em>  .
  
> [!NOTE]
> Se gli utenti sono già esistenti, facendo clic sul pulsante Crea utenti verranno aggiornate le modifiche apportate alla configurazione. 
  
#### <a name="delete-users-button"></a>Pulsante Elimina utenti

Quando si fa clic sul pulsante **Elimina utenti** , i parametri di input della scheda verranno convalidati. Se sono presenti errori di convalida, viene richiesto di correggerli e se i valori di input sono corretti, gli utenti di test specificati verranno disattivati ed eliminati da Active Directory. Anche in questo caso, nella parte inferiore della scheda viene visualizzata una barra di stato e non è necessario chiudere l'applicazione mentre la barra di avanzamento è attiva.
  
> [!NOTE]
> Sono supportati solo i numeri di telefono formattati negli Stati Uniti. I numeri di telefono sono sempre assegnati agli utenti e tutti gli utenti creati da UserProvisioningTool.exe sono abilitati per impostazione predefinita per VoIP aziendale. Tutti gli scenari che utilizzano il numero di telefono, ad esempio l'operatore automatico di conferenza o le chiamate di UC-PSTN, utilizzano questo numero di telefono per instradare correttamente le chiamate. Per questo motivo,  *ogni utente*  deve disporre di un *numero di telefono univoco*  .
  
> [!NOTE]
> **Se è necessario creare due volte gli utenti, il comando avrà esito negativo a meno che non si utilizzi un codice area diverso o se gli utenti precedenti sono stati disabilitati utilizzando il cmdlet Disable-CsUser.**
  
> [!IMPORTANT]
> Prima di creare contatti, è necessario prima di tutto eseguire la replica utente (operazione eseguita dalla scheda utenti). 
  
> [!IMPORTANT]
> Se gli utenti sono stati appena creati, è necessario attendere il completamento della replica di Skype for Business Server e inserire gli account utente nel database. **Se gli utenti non hanno completato la replica, verrà visualizzato un messaggio di errore.** Se il servizio front end di Skype for Business Server 2015 è stato avviato, è possibile sapere quando gli utenti hanno finito di eseguire la replica oppure eseguendo correttamente il cmdlet Get-CsUser nell'ultimo utente del numero totale specificato.
  
#### <a name="contacts-creation-tab"></a>Scheda creazione contatti

Questa scheda consente di fornire i dettagli dei contatti degli utenti per il testing.
  
![Strumento di provisioning degli utenti che mostra la scheda creazione contenuto.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Per configurare i contatti degli utenti, eseguire le operazioni seguenti:

1. Nel campo **Media contatti per utente** immettere il numero medio di contatti da popolare negli elenchi di contatti per ogni utente.
    
2. Selezionare la casella di controllo **fisso** se si desidera creare un numero uguale di contatti per ogni utente. Se si desidera variare il numero di contatti creati per gli utenti, deselezionare questa casella di controllo.
    
3. Nel campo **media gruppi di contatti per utente** immettere il numero di gruppi di contatti per utente. Questo numero deve essere inferiore ai **contatti medi per utente**.
    
4. Nel campo **percentuale contatti federati/pool incrociato** assegnare un numero compreso tra 0 e 100. Questa percentuale di contatti verrà creata con gli utenti federati.
    
5. In campo **federato/pool incrociato** , assegnare il nome utente per gli utenti federati che verranno aggiunti agli elenchi di contatti degli utenti locali.
    
6. Nel campo **dominio SIP dell'utente federata/pool incrociato** assegnare il nome di dominio SIP degli utenti federati.
    
7. Nella scheda **creazione utente** verificare che le informazioni siano corrette. I contatti verranno creati dai valori nella scheda Creazione utente.
    
8. Fare clic su **Crea contatti** per iniziare la creazione dei contatti. Questo processo può richiedere alcuni minuti. Al termine dell'operazione, verrà visualizzata una finestra di dialogo con il messaggio "Operation completed successfully". È possibile convalidare i contatti creati accedendo come utente creato dalla scheda Creazione utente.
    
    > [!NOTE]
    > Dopo la creazione dei contatti, questo strumento riavvierà tutti i Front End Server nel pool di destinazione. Potrebbe essere necessario più tempo (fino a 2 ore) per l'avvio dei Front End Server, a seconda del numero di contatti creati dall'operazione. 
  
#### <a name="distribution-list"></a>Lista di distribuzione

Lo strumento di sviluppo dello stress e delle prestazioni di Skype for Business Server 2015 è in grado di simulare la funzionalità di espansione della lista di distribuzione (DL) nel client Skype for business 2015. È possibile ignorare questo passaggio se non si intende abilitare l'espansione DL nello strumento di provisioning dell'utente.
  
![Strumento di provisioning degli utenti che mostra la scheda creazione della lista di distribuzione.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
La scheda della lista di distribuzione consente di creare un DLs che lo strumento di stress e prestazioni utilizzerà per la funzionalità di espansione della lista di distribuzione. Prima di creare DLs, è necessario distribuire Skype for Business Server 2015, incluso l'esecuzione di ForestPrep. In caso contrario, gli attributi DL non saranno presenti nello schema di AD, quindi lo strumento non sarà in grado di creare DLs.
  
### <a name="to-configure-distribution-lists"></a>Per configurare le liste di distribuzione:

1. Nel campo **numero di liste di distribuzione** , assegnare il numero totale di DLS che si desidera creare (la raccomandazione è che si inizia con un valore doppio del numero di utenti.).
    
2. Nel campo **prefisso della lista di distribuzione** , immettere un prefisso che tutti i DLS creati avranno, ad esempio *testDL*  . Questo significa che, a 100 DLs, i nomi di DL saranno simili a: testDL0, testDL1, fino a testDL99.
    
3. Nei **membri minimi di un campo dist. list** , immettere il numero minimo di utenti da inserire in ogni DL.
    
4. Nei **membri massimi di un campo dist. list** , immettere il numero massimo di utenti da aggiungere in ogni DL.
    
#### <a name="create-distribution-lists-button"></a>Pulsante Crea liste di distribuzione

Quando si fa clic sul pulsante Crea liste di distribuzione, lo strumento esegue una query in Active Directory per verificare se sono già presenti liste di distribuzione corrispondenti al prefisso e ai numeri. Lo strumento crea un DLs che non esiste già. Quando si aggiungono membri a queste liste di distribuzione appena create, verranno scelti gli utenti dall'intervallo specificato nella scheda Creazione utente.
  
#### <a name="location-info-service-config-tab"></a>Scheda configurazione del servizio informazioni percorso

Lo strumento di gestione dello stress e delle prestazioni di Skype for Business Server 2015 può generare anche file di configurazione fittizi per il servizio informazioni percorso. Si noti che il servizio informazioni percorso in genere non ha un impatto significativo sulle prestazioni nei server. 
  
![Strumento di provisioning degli utenti che mostra la scheda configurazione del servizio informazioni percorso.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Se si sceglie di verificare questa funzionalità, inserire i valori nel modulo e fare clic sul pulsante genera file di configurazione LIS, che verrà creato. File CSV denominati:
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
Per importare questi file nel database LIS, utilizzare i cmdlet di PowerShell seguenti:
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Configurare il profilo utente
<a name="BKMK_UserProfile"> </a>

Dopo aver creato gli utenti (tramite lo strumento di creazione utente), è possibile configurare i profili utente con lo strumento di configurazione del carico di Skype for Business Server 2015 (UserProfileGenerator.exe).
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Esecuzione dello strumento di configurazione del carico di Skype for Business Server 2015

Avviare lo strumento di configurazione del caricamento (UserProfileGenerator.exe) e compilare le schede. Questo strumento consente di creare una directory per ogni computer client che sarà necessario eseguire le simulazioni. Ogni directory client include uno script che consente di avviare lo strumento di gestione dello stress e delle prestazioni di Skype for Business Server 2015 (LyncPerfTool.exe). Nelle sezioni seguenti vengono forniti esempi di come compilare i campi di ogni scheda dello strumento di configurazione del carico di Skype for Business Server 2015.
  
> [!IMPORTANT]
> I valori specifici dell'utente utilizzati nello strumento di configurazione del caricamento (UserProfileGenerator.exe) devono corrispondere ai valori specificati nello strumento di creazione degli utenti di Skype for Business Server 2015 (UserProvisioningTool.exe) per il pool. 
  
#### <a name="common-configuration-tab"></a>Scheda di configurazione comune

Di seguito è riportata la scheda **configurazione comune** dello strumento di configurazione del carico. Compilare i campi della scheda configurazione comune, come descritto nella procedura seguente.
  
![La scheda provisioning degli utenti che mostra la scheda configurazione comune.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. Nel campo **numero di macchine disponibili** , digitare il numero di computer che si desidera utilizzare per eseguire lo strumento stress and Performance (LyncPerfTool.exe). È consigliabile disporre di un solo computer per ogni 4500 utenti da simulare, ma tale numero può variare se si riduce il livello di carico o si utilizza solo un sottoinsieme delle funzionalità disponibili dello strumento (i livelli di carico sono impostati nella scheda scenari generali).
    
2. Nel campo **prefisso per i nomi utente** , immettere un prefisso per il campo nome utente di tutti gli utenti. Per eseguire l'accesso l'URI (Uniform Resource Identifier) sarà: *UserPrefix [Indice inizio utente... (Numero di utenti-1)] @User dominio*  , ad esempio myUser009@Contoso.com.
    
3. Nel campo **password per tutti gli utenti** , immettere la password utilizzata durante la creazione degli utenti. Se si lascia questo campo vuoto, il nome utente verrà impostato come password.
    
4. Nel campo **Indice inizio utente** immettere l'indice del primo utente da configurare. È possibile configurare diversi intervalli per diversi tipi o livelli di carico, ma è necessario eseguire lo strumento di configurazione del caricamento (UserProfileGenerator.exe) una volta per l'intervallo che si desidera configurare.
    
5. Nel campo **numero di utenti** , immettere il numero totale di utenti che si desidera configurare.
    
6. Nel campo **dominio utente** immettere il dominio utilizzato per l'URI SIP. Questa operazione viene utilizzata per creare l'URI SIP di ogni utente per accedere al server front end server o all'endpoint di Skype for Business Server 2015 o Standard Edition e potrebbe essere diverso dal dominio dell'account.
    
7. Nel campo **dominio account** immettere l'accesso al dominio ad DS.
    
8. Nel campo **percentuale di MPOP** (più punti percentuali di presenza) assegnare un valore per la percentuale di utenti che hanno effettuato l'accesso da più computer o dispositivi, ad esempio il 10%.
    
9. Immettere il numero massimo di endpoint contemporanei nel campo **accedi al secondo (per istanza)** . Questo è il numero massimo di log in per gli utenti e la raccomandazione è una velocità inferiore a/uguale a 2 al secondo (<= 2).
    
10. Nel campo **proxy di accesso o FQDN del pool** , immettere il nome di dominio completo (FQDN) del server a cui si desidera connettere i client. Se gli utenti accedono esternamente, è necessario digitare il proxy di accesso. Se gli utenti sono interni, assegnare il nome di dominio completo del pool Enterprise o del server Standard Edition.
    
11. Nel campo **porta** immettere la porta che si desidera venga utilizzata dagli utenti per SIP (il valore predefinito è 5061).
    
12. Per il campo **Impostazioni server di rete esterno** , assegnare il proxy di accesso o il nome FQDN del pool e, ancora una volta, la **porta**. Queste impostazioni vengono utilizzate solo per la simulazione del caricamento degli endpoint esterni.
    
#### <a name="general-scenarios-tab"></a>Scheda scenari generali

![Strumento di configurazione del caricamento che mostra la scheda scenari generali.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
È possibile configurare i livelli di carico e i parametri per ogni scenario generale offerto determinando gli elementi che si desidera eseguire o lasciare disattivati. Di seguito sono elencate le opzioni generali:
  
> [!NOTE]
> I valori dei livelli di carico per tutti i campi, ma i servizi di informazioni locali sono **disabilitati**, **basso**, **medio**, **alto** o **personalizzato**. Se si seleziona qualsiasi impostazione ma disabilitata, vengono generate le configurazioni per ogni client. Risultati elevati nel carico massimo supportato sul server; il medium è 60% del carico elevato; il valore basso è 30%. 
  
- **Messaggistica istantanea-** Sono inclusi peer-to-peer e servizi di conferenza. scegliere il valore appropriato per il livello di carico.
    
- Servizi **di audioconferenza-** Scegliere un livello di carico *solo* per le conferenze audio. Le chiamate peer-to-peer verranno affrontate un po' più avanti nella sezione **Voice Scenarios** . Aprire la scheda **Avanzate** per abilitare MultiView.
    
- **Condivisione applicazioni-** Scegliere un livello di carico per la condivisione di applicazioni.
    
- **Collaborazione dati-** Scegliere un livello di carico per la collaborazione dati, che include i servizi di conferenza dati.
    
- **Espansione della lista di distribuzione-** Fare clic sul pulsante **Avanzate** e compilare il campo con gli stessi valori configurati nella scheda DL dello strumento di creazione utente (UserProvisioningTool.exe). Scegliere un livello di carico.
    
- **Query Web della rubrica-** Questo è il servizio di ricerca della Rubrica anziché il download dei file della Rubrica. Se si desidera abilitare questa opzione per i download dei file della Rubrica, fare clic sul pulsante **Avanzate** e impostare **EnableABSDownload** su true. Assegnare un valore per il livello di carico.
    
- **Response Group Service-** Fare clic sul pulsante **Avanzate** e specificare gli URI dei Response Group già creati quando si esegue il provisioning degli agenti del servizio Response Group. È necessario scegliere almeno un gruppo di risposta. Per utilizzare altre informazioni, separare i Response Group con punti e virgola. Aggiornare **RGSUriSuffixStartIndex** e **RGSUriSuffixEndIndex** ai valori effettivi. Scegliere un livello di carico.
    
- **Servizi informazioni percorso-** Selezionare un livello di carico abilitato o disabilitato.
    
> [!NOTE]
> A ognuno degli scenari è associato un pulsante avanzato e un set di caselle di controllo che consentono varianti all'impostazione predefinita. 
  
- La scelta di  *ad-hoc*  consentirà allo strumento di generare una simulazione delle conferenze che verranno create per tutta l'ora.
    
- La scelta di  *grandi dimensioni*  significa che verrà simulato uno scenario di conferenza di grandi dimensioni.
    
-  *External*  indica allo strumento di simulare anche gli utenti esterni.
    
Questi pulsanti e caselle di controllo sono valori aggiuntivi specifici di ogni scenario e modificano il comportamento dello strumento stress and performance e rendono possibile la personalizzazione.
  
Per ogni scenario nella scheda scenari generali (ad eccezione di Location Information Services), se il valore del livello di carico è **Custom**, la frequenza di conversazione viene calcolata utilizzando il campo corrispondente nella finestra di dialogo avanzate. Il nome del campo può variare a seconda dello scenario, ma la descrizione del campo verrà impostata su:  *Nota Questo numero verrà utilizzato solo se è selezionata l'opzione personalizzato dal menu a discesa*  .
  
I valori **High**, **medium** e **low**, altereranno i tassi di conversazione per modalità in linea con il modello utente che rappresenta un bilanciamento di tutti gli scenari. Se è necessario modificare il livello di carico per modalità a causa di una differenza nell'utilizzo previsto, utilizzare un tasso di conversazione personalizzato.
  
#### <a name="voice-scenarios-tab"></a>Scheda scenari vocali

Questa è la scheda per la configurazione di tutti gli scenari relativi alla voce.
  
![Caricare la scheda scenari vocali dello strumento di configurazione.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Le opzioni disponibili sono:
  
- **VoIP-** Fare clic sul pulsante **Avanzate** e aggiungere i valori per i campi PhoneAreaCode e LocationProfile (dial plan). Verrà inoltre assegnato un valore per il livello di carico. Se si sceglie un livello di carico per il gateway VoIP o UC/PSTN abilitato, verrà generato un file di configurazione PSTN (Public-Switched Telephone Network) a Unified Communications (UC) per simulare le chiamate esterne.
    
- **Gateway UC/PSTN-** È necessario scegliere un valore a livello di carico e, quando si sceglie altro che disabilitato, è inoltre necessario specificare un valore per il codice area PSTN facendo clic sul pulsante **Avanzate** . Fare clic su **Aggiungi** sotto Mediation Server e PSTN. Verificare di disporre di una route configurata per il prefisso.
    
    > [!TIP]
    > È possibile utilizzare il pannello di controllo di Skype for business o Skype for Business Management Shell per verificare la configurazione della route vocale. 
  
- **Operatore Conferenza-** Specificare un valore per il livello di carico. Qualsiasi valore diverso da Disabled consentirà il campo del **numero di telefono** . Immettere il numero di telefono dell'operatore automatico che si desidera utilizzare. Fare clic su **Avanzate** e assegnare un valore per il campo **LocationProfile** .
    
- **Servizio parcheggio di chiamata-** In questo caso, fornire un livello di carico.
    
- **Mediation Server e PSTN-** Ogni Mediation Server che si desidera utilizzare richiede il proprio simulatore PSTN. Dopo aver determinato il client che si intende utilizzare per il simulatore, configurare il Mediation Server per instradare le chiamate al computer sul simulatore PSTN configurato. Fare clic sul pulsante **Aggiungi** per configurare un valore per il Mediation Server.
    
    > [!NOTE]
    > A ogni scenario è posizionato un pulsante avanzato. Le finestre di dialogo avanzate contengono le impostazioni specifiche di ogni scenario che modificano il comportamento dello strumento stress and performance e consentono la personalizzazione. > per ogni scenario nella scheda scenari vocali, se il valore del livello di carico è **Custom**, la frequenza di conversazione viene calcolata utilizzando il campo corrispondente nella finestra di dialogo avanzate. Il nome del campo può variare a seconda dello scenario, ma la descrizione del campo verrà impostata su:  *Nota Questo numero verrà utilizzato solo se è selezionata l'opzione personalizzato dal menu a discesa*  .
  
#### <a name="web-app-tab"></a>Scheda Web App

![Strumento di configurazione del caricamento, scheda Web App.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App supporta gli scenari di conferenza tramite il server Unified Communications Web API (UCWA) installato in un front end server. La scheda Web App consente di configurare tutti gli scenari relativi a Web App. Le opzioni sono:
  
- **Impostazioni generali dell'applicazione Web-** Fare clic sul pulsante **Impostazioni aggiuntive** e impostare **ReachTargetServerUrl** su IP virtuale del pool di directory (VIP) del VIP del pool Front end.
    
- **Condivisione applicazioni-** Selezionare un valore per il livello di carico.
    
- **Collaborazione dati-** Selezionare un valore per il livello di carico.
    
- **Messaggistica istantanea-** Selezionare un valore per il livello di carico.
    
- Servizi **di conferenza vocale-** Selezionare un valore per il livello di carico.
    
> [!NOTE]
> A ognuno degli scenari è associato un pulsante **avanzato** . Le finestre di dialogo avanzate contengono valori specifici per ogni scenario in cui viene modificato il comportamento dello strumento stress and performance e l'abilitazione della personalizzazione. > per ogni scenario di applicazione Web, se il livello di carico è **Custom**, viene utilizzato il valore specificato nel campo **ConversationsPerHour** anziché quello predefinito.
  
#### <a name="mobility-tab"></a>Scheda dispositivi mobili

Utilizzare questa scheda per configurare tutti gli scenari relativi alla mobilità.
  
![Caricare la scheda mobilità dello strumento di configurazione.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Le opzioni seguenti sono:
  
- **Impostazioni generali per la mobilità-** Fare clic su **Impostazioni aggiuntive** e impostare il campo UcwaTargetServerUrl sul server IP virtuale (VIP) del pool di server Director o sul VIP del pool Front end.
    
- **Presenza e messaggistica istantanea P2P/audio-** Selezionare un valore per il livello di carico per abilitare la simulazione di dispositivi mobili.
    
> [!NOTE]
> A ognuno degli scenari è associato un pulsante **avanzato** . Le finestre di dialogo avanzate contengono valori specifici di ogni scenario in cui viene modificato il comportamento dello strumento stress and performance e l'abilitazione della personalizzazione. > per ognuno degli scenari di mobilità, se il livello di carico è **Custom**, viene utilizzato il valore specificato nel campo **ConversationsPerHour** anziché quello predefinito.
  
#### <a name="summary-tab"></a>Scheda Riepilogo

La scheda Riepilogo indica gli utenti da utilizzare per ogni scenario.
  
![Scheda Riepilogo del caricamento dello strumento di configurazione.](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
La scheda Riepilogo indica gli utenti da utilizzare per ogni scenario. 
  
È possibile configurare manualmente gli intervalli di numeri utente selezionando la casella di controllo **Abilita generazione di un intervallo di utenti personalizzato** e quindi facendo doppio clic sullo scenario nella tabella che include l'intervallo di utenti che si desidera personalizzare.
  
Controllare **(RunClient.bat) aggiungere ritardo di accesso all'avvio** per includere i ritardi nei file batch generati in modo che corrispondano alla frequenza di accesso. Questa operazione è utile per impedire l'overload del server quando si effettua l'accesso a un numero elevato di utenti.
  
Fare clic su **genera file** e selezionare la cartella in cui si desidera generare la configurazione. Quando i file sono stati creati correttamente, verrà visualizzata una finestra di dialogo.
  
![La finestra di messaggio "carica file di configurazione generati correttamente". Basta fare clic su OK.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Eseguire LyncPerfTool
<a name="BKMK_RunTool"> </a>

Prima di eseguire lo strumento di gestione dello stress e delle prestazioni di Skype for business 2015 Server (LyncPerfTool.exe), è necessario creare gli utenti, i contatti e gli scenari. Per informazioni dettagliate sull'utilizzo degli strumenti per eseguire queste operazioni, vedere [creare utenti e contatti](using-the-tool.md#BKMK_CreateUsersAndContacts) e [configurare il profilo utente](using-the-tool.md#BKMK_UserProfile) in precedenza in questo articolo. L'esecuzione di questi strumenti genererà anche un file che verrà eseguito con lo strumento stress and performance come parte di un file batch con i parametri necessari inclusi.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Esecuzione dello strumento di sollecito e prestazioni di Skype for Business Server 2015

Lo strumento di configurazione del caricamento (UserProfileGenerator.exe) crea un file batch che consente di eseguire lo strumento stress and performance (LyncPerfTool.exe) registrando i contatori delle prestazioni e caricando il file di configurazione XML. Il file batch esegue un'istanza di LyncPerfTool.exe per ogni file di configurazione. Per eseguire il file batch, attenersi alla seguente procedura:
  
### <a name="run-the-stress-and-performance-test"></a>Eseguire il test di stress e prestazioni

1. Copiare la cartella con le cartelle e i file di configurazione all'interno della directory in cui è LyncPerfTool.exe su ogni computer client. Ad esempio, se i file di configurazione sono stati generati nella cartella denominata 1.28 _ 13.16.16, copiare tale cartella nella cartella con LyncPerfTool.exe. Eseguire questa operazione su ogni client.
    
2. Passare alla cartella client ed eseguire lo script batch di **RunClient** . È possibile fare doppio clic sul file batch in Esplora risorse e verranno eseguiti tutti i file di configurazione per il client. È inoltre possibile eseguire lo script da una cartella client utilizzando la sintassi seguente:
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Per eseguire direttamente lo strumento stress and performance, aprire una finestra del prompt dei comandi e digitare il comando seguente dalla riga di comando e, quando si esegue questa operazione per la prima volta, assicurarsi di registrare i contatori delle prestazioni  `regsvr32 /i /n /s LyncPerfToolPerf.dll` , come illustrato nella nota più avanti in questo argomento:
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

Affinché lo strumento visualizzi i valori nel file di configurazione, includere il  `/displayfile` parametro nel comando precedente, in modo che sia simile al seguente:
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Per  *terminare*  il processo, premere CTRL + C.
  
> [!NOTE]
> Prima di eseguire direttamente lo strumento stress and performance, è necessario registrare i contatori delle prestazioni tramite il seguente comando:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Ogni istanza dello strumento di stress e prestazioni avviato inizierà immediatamente l'accesso agli utenti, generalmente a una velocità di un utente al secondo. 
  
La frequenza di accesso dell'utente di picco per il pool è pari a circa 12 al secondo. Questo significa che non è necessario avviare più di 12 LyncPerfTool.exe istanze contemporaneamente mentre gli utenti continuano a eseguire l'accesso. 1000 gli utenti impiegano circa 20 minuti per accedere completamente a uno al secondo.
  
## <a name="interpreting-the-results"></a>Interpretazione dei risultati
<a name="BKMK_Interpret"> </a>

Lo strumento per lo stress e le prestazioni di Skype for Business Server 2015 è costituito da numerosi contatori che consentono di comprendere il funzionamento del client e l'eventuale presenza di problemi.
  
### <a name="client-counters"></a>Contatori client

Ogni istanza di LyncPerfTool.exe in esecuzione dispone di un'istanza separata dei contatori. Ogni istanza è denominata dal relativo ID di processo. Se i client sono sovraccaricati, possono verificarsi altri problemi. Per evitare questi problemi:
  
- Monitorare l'utilizzo della CPU e della memoria nei computer client. Se la CPU è costantemente al di sopra del 90%, ridurre il numero di utenti.
    
- Quando l'impronta della memoria è elevata, è possibile che si verifichino problemi se il file di paging inizia a esaurire lo spazio. Verificare che la carica di commit non colpisca il limite del computer. Se si eseguono dei limiti di memoria, valutare l'aumento delle dimensioni dei file di paging o la riduzione del numero di utenti.
    
Ecco un elenco dei contatori delle prestazioni chiave:
  
**Informazioni generali**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Tempo impiegato in minuti  <br/> |Tempo trascorso dopo l'avvio del processo.  <br/> |
|Endpoint attivi  <br/> |Numero di endpoint attualmente connessi al server.  <br/> |
|Accessi non riusciti  <br/> |Numero totale di errori di accesso endpoint.  <br/> |
|Tentativi di accesso  <br/> |Numero totale di tentativi di accesso all'endpoint.  <br/> |
|Endpoint disconnessi  <br/> |Numero totale di endpoint che sono stati disconnessi.  <br/> |
   
**Informazioni sulla presenza**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate di sepresenza  <br/> |Numero totale di tentativi di modifica della presenza. Per i diversi tipi di modifiche alla presenza, vedere il contatore delle prestazioni chiamate di tipo sepresence (Presence Type).  <br/> |
|Risposte di NNN per la presenza  <br/> |Numero totale di codici di risposta nnn ricevuti dal server.  <br/> |
|Chiamate GetPresence  <br/> |Numero totale di tentativi di richiesta di presenza per ottenere.  <br/> |
|Risposte di NNN per GetPresence  <br/> |Numero totale di codici di risposta nnn ricevuti dal server.  <br/> |
   
**Informazioni sul servizio Rubrica**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Download di file in ABS Full/Delta tentati  <br/> |Numero totale di richieste di download di file completi o Delta tentate.  <br/> |
|Download di file completi/Delta in ABS con esito positivo  <br/> |Numero totale di richieste di download di file completi o Delta tentate.  <br/> |
|Contatori correlati al servizio query Web della Rubrica  <br/> |Contatori relativi al download di file della Rubrica.  <br/> |
|Tentativi di WS ABS  <br/> |Numero totale di richieste del servizio query Web della rubrica tentate.  <br/> |
|Chiamate in ABS WS con esito positivo  <br/> |Numero totale di richieste del servizio di query Web della rubrica che hanno restituito un codice di risposta corretto.  <br/> |
|Chiamate in ABS WS non riuscite  <br/> |Numero totale di richieste del servizio di query Web della rubrica che hanno restituito un codice di risposta di errore.  <br/> |
   
> [!NOTE]
> In questa categoria sono inclusi i contatori utilizzati per monitorare i download di file in ABS (Address Book Service) e le richieste del servizio query Web della Rubrica. 
  
**Informazioni sulle liste di distribuzione (DL)**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Tentativi di chiamata  <br/> |Numero totale di richieste del servizio Web di espansione della lista di distribuzione (DLX) tentate.  <br/> |
|Chiamate con esito positivo  <br/> |Numero totale di richieste del servizio Web DLX che hanno restituito un codice di risposta corretto.  <br/> |
|Chiamate non riuscite  <br/> |Numero totale di richieste del servizio Web DLX che hanno restituito un codice di risposta di errore.  <br/> |
   

  
> [!NOTE]
> I contatori delle prestazioni elencati di seguito numeri di rapporto per tutte le chiamate VoIP (Voice over IP), incluse le chiamate a Mediation Server, A/V Conferencing Server, Edge Server, Response Group Application e Conference Auto Attendant, quando questi scenari sono abilitati. 
  
**Informazioni di base sul VoIP**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate attive  <br/> |Numero totale di chiamate vocali in ingresso/in uscita attualmente in corso.  <br/> |
|Chiamate terminate  <br/> |Numero totale di chiamate vocali in ingresso/in uscita già terminate.  <br/> |
|Chiamate rifiutate  <br/> |Il numero totale di chiamate vocali in ingresso è stato rifiutato.  <br/> |
|Tentativi di chiamata in arrivo/in uscita  <br/> |Numero totale di chiamate vocali in ingresso/in uscita tentate.  <br/> |
|Chiamate in ingresso/in uscita stabilite  <br/> |Numero totale di chiamate vocali in ingresso/in uscita stabilite.  <br/> |
|Chiamate NNN ricevute  <br/> |Numero totale di codici di risposta nnn ricevuti dal server.  <br/> |
|Velocità di passaggio VoIP (%)  <br/> |Total calls established/Total calls Tented.  <br/> |
   
**Informazioni sulle chiamate di servizio di Response Group**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate attive  <br/> |Numero totale di chiamate attive all'applicazione Response Group.  <br/> |
|Tentativi di chiamata  <br/> |Numero totale di chiamate tentate.  <br/> |
   
**Informazioni sulle chiamate di messaggistica immediata**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate attive  <br/> |Numero totale di chiamate di messaggistica istantanea in arrivo/in uscita.  <br/> |
|Chiamate terminate  <br/> |Numero totale di chiamate di messaggistica istantanea in ingresso/in uscita già terminate.  <br/> |
|Chiamate NNN ricevute  <br/> |Numero totale di codici di risposta nnn ricevuti dal server.  <br/> |
|Messaggi di messaggistica istantanea ricevuti/inviati  <br/> |Numero totale di messaggi ricevuti o inviati per tutte le sessioni.  <br/> |
|Tentativi di chiamata in arrivo/in uscita  <br/> |Numero totale di chiamate di messaggistica istantanea in arrivo/in uscita tentate.  <br/> |
|Chiamate in ingresso/in uscita stabilite  <br/> |Numero totale di chiamate di messaggi istantanei in arrivo/in uscita stabilite.  <br/> |
   
**Informazioni sulle chiamate di condivisione delle app**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate attive  <br/> |Numero totale di chiamate di condivisione delle applicazioni in arrivo/in uscita.  <br/> |
|Chiamate terminate  <br/> |Numero totale di chiamate di condivisione applicazioni in ingresso/in uscita già terminate.  <br/> |
|Chiamate NNN ricevute  <br/> |Numero totale di codici di risposta nnn ricevuti dal server.  <br/> |
|Tentativi di chiamata in arrivo/in uscita  <br/> |Numero totale di chiamate di condivisione applicazioni in ingresso/in uscita tentate.  <br/> |
|Chiamate in ingresso/in uscita stabilite  <br/> |Numero totale di chiamate di condivisione delle applicazioni in ingresso/in uscita stabilite.  <br/> |
   
**Informazioni sulle chiamate CAA**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate attive  <br/> |Numero totale di chiamate PSTN (Public Switched Telephone Network) in ingresso/in uscita attualmente in corso.  <br/> |
|Chiamate terminate  <br/> |Numero totale di chiamate PSTN in ingresso/in uscita già terminate.  <br/> |
|Tentativi di chiamata in arrivo/in uscita  <br/> |Numero totale di chiamate PSTN in ingresso/in uscita tentate.  <br/> |
|Chiamate in ingresso/in uscita stabilite  <br/> |Numero totale di chiamate PSTN in ingresso/in uscita stabilite.  <br/> |
   
**Informazioni sulla conferenza**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Conferenze di messaggistica istantanea attive  <br/> |Numero totale di conferenze di messaggistica istantanea in continuo.  <br/> |
|Conferenze audio/video attive  <br/> |Numero totale di conferenze audio/video (A/V) in uscita.  <br/> |
|Conferenze di condivisione applicazioni attive  <br/> |Numero totale di conferenze di condivisione applicazioni in uscita.  <br/> |
|Numero di partecipanti  <br/> |Numero totale di partecipanti attualmente connessi a conferenze.  <br/> |
|Errore della pianificazione delle conferenze  <br/> |Numero totale di errori durante il tentativo di pianificazione di una conferenza.  <br/> |
|Partecipare a una conferenza non riuscita  <br/> |Numero totale di errori durante il tentativo di connessione a una conferenza.  <br/> |
   
**Contatori client di UCWA**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Numero totale di join IMMCU con esito positivo  <br/> |Numero totale di conferenze di messaggistica istantanea Unite.  <br/> |
|Numero totale di join DMCU con esito positivo  <br/> |Numero totale di conferenze A/V Unite.  <br/> |
   

