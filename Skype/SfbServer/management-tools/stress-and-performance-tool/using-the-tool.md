---
title: Utilizzo dello strumento Skype for Business Server 2015 Stress and Performance
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
ms.date: 2/13/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: 'Per eseguire lo strumento stress e prestazioni di Skype for Business Server 2015, è necessario essere in grado di gestire utenti, contatti e profili utente, configurare lo strumento per l''esecuzione e quindi esaminare l''output o i risultati prodotti dallo strumento.'
---

# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Utilizzo dello strumento Skype for Business Server 2015 Stress and Performance
 
Per eseguire lo strumento stress e prestazioni di Skype for Business Server 2015, è necessario essere in grado di gestire utenti, contatti e profili utente, configurare lo strumento per l'esecuzione e quindi esaminare l'output o i risultati prodotti dallo strumento.
  
Esistono quattro aree coinvolte nell'esecuzione dello strumento Skype for Business Server 2015 Stress and Performance Tool (il file eseguibile è LyncPerfTool.exe):
  
- [Creare utenti e contatti](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configurare il profilo utente](using-the-tool.md#BKMK_UserProfile)
    
- [Eseguire LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpretazione dei risultati](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Creare utenti e contatti
<a name="BKMK_CreateUsersAndContacts"> </a>

È necessario utilizzare lo strumento di provisioning degli utenti Skype for Business Server 2015 (SB 2015) UserProvisioningTool.exe per creare utenti e contatti per i test di stress e prestazioni.
  
Questo è un elenco di termini utili che potrebbero essere utili durante la lettura degli argomenti:
  
- **Unità organizzativa** - Unità organizzativa di Servizi di dominio Active Directory( AD DS).
    
- **Federato/Tra pool** - Utenti che possono comunicare con gli utenti da altri servizi di messaggistica istantanea.
    
- **Liste di distribuzione** - O DLL. Si tratta di oggetti in Servizi di dominio Active Directory che contengono un elenco di utenti di Servizi di dominio Active Directory. Vengono utilizzati per facilitare le comunicazioni tra gruppi di persone.
    
- **Location Info Service** - Servizio Skype for Business Server 2015 che, quando viene abilitato e configurato per telefono, consente il recupero della posizione fisica per i servizi Enhanced 911 (E911).
    
- **U.S. Telefono Numbers** - Numeri Telefono assegnati all'utente oltre all'URI SIP utilizzato per il routing delle chiamate in ingresso e in uscita in RNL (Reverse Number Lookup).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Creare utenti e contatti tramite UserProvisioningTool.exe

> [!NOTE]
> Prima di iniziare, assicurati di aver effettuato l'accesso come membro del gruppo di sicurezza Domain Admins per eseguire questo strumento. A tale scopo, è necessario creare utenti di Active Directory. 
  
Devi usare lo strumento di provisioning Skype for Business Server utente per creare utenti e contatti per la simulazione del carico.
  
Lo **Skype for Business Server user provisioning tool** viene installato con il **pacchetto Skype for Business Server Stress and Performance Tool**. Assicurarsi che il programma di installazione del pacchetto (CapacityPlanningTool.msi) sia stato eseguito nel Front End Server o nel server edizione Standard che si intende testare.
  
È possibile avviare lo strumento di provisioning degli utenti di Skype for Business Server eseguendo il file UserProvisioningTool.exe (disponibile in %InstalledDirectory%LyncStressAndPerfTool\LyncStress) nel Front End Server o nel server edizione Standard.
  
> [!IMPORTANT]
> Quando si crea un numero elevato di utenti(ad esempio, 10.000 o più), eseguire il UserProvisioningTool.exe. È necessario eseguire questa operazione perché lo strumento creerà e configurerà  *nuovi utenti*  di Active Directory.
  
Quando si apre lo strumento di provisioning degli utenti, fare clic su Configurazione e selezionare Carica configurazione. 
  
Per iniziare a configurare utenti e contatti, caricare il file predefinito incluso nel pacchetto, denominato "SampleData.xml". In questo modo verranno prepopolati i campi con dati di esempio che sarà necessario modificare per renderli rilevanti per la distribuzione.
  
Se si dispone di un file XML preconfigurato che contiene già le impostazioni personalizzate, è possibile caricare il file. Compilare i campi nello strumento di provisioning degli utenti, come descritto nelle sezioni seguenti.
  
### <a name="to-configure-server-options"></a>Per configurare le opzioni del server:

1. Nel campo **FQDN pool Front End** digitare il nome di dominio completo (FQDN) del server edizione Standard o il pool Front End in cui si desidera ospitare gli utenti.
    
2. Nel campo **Prefisso nome** utente digitare un prefisso che si desidera utilizzare per eseguire il busto dei nomi utente a scopo di test, ad esempio "TestUser".
    
3. Nel campo **Password** digitare una password che verrà utilizzata in tutti gli account utente di test.
    
4. Nel campo **Dominio account** digitare il nome di dominio del dominio ACTIVE corrente (quello in cui si desidera creare gli utenti di test).
    
5. Nel campo **Unità organizzativa** digitare il nome del dominio di Active Directory in cui si desidera creare questi utenti di test. Se l'unità organizzativa non esiste già, verrà creata automaticamente.
    
6. Nel campo **Telefono codice area** digitare il codice di area a tre cifre da utilizzare in tutti gli account utente di test. Assicurarsi che il codice area scelto non sia in conflitto con i codici di area di altri utenti in Active Directory.
    
7. Fare clic per selezionare **la casella di controllo Voice Enabled** se si desidera abilitare gli utenti di test per VoIP aziendale.
    
8. Nel **campo Numero di utenti** assegnare il numero totale di utenti di test che si desidera creare.
    
9. Nel campo **Indice** iniziale, assegnare il numero iniziale che verrà utilizzato come suffisso per il prefisso del nome utente (ad esempio, il prefisso è "TestUser" e il nome termina con "0" nell'esempio seguente).
    
     ![Strumento di provisioning degli utenti che mostra la scheda per la creazione degli utenti.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Pulsante Crea utenti

Quando fai clic sul **pulsante Crea utenti** , i parametri di input immessi vengono convalidati. Se sono presenti errori di convalida, verrà richiesto di correggerli. In caso contrario, se tutti i valori sono corretti, gli utenti inizieranno a comparire in Active Directory (indipendentemente dall'unità organizzativa specificata). Vedrai un indicatore di stato nella parte inferiore dello strumento mentre viene eseguito. Non chiudere l'applicazione mentre l'indicatore di stato è attivo.
  
La creazione degli utenti richiede tempo, quindi pianifica di conseguenza. Questo processo può richiedere da diversi minuti per pochi utenti a poche ore per un numero elevato di utenti.
  
Se non si ha accesso al controller di dominio Active Directory nell'ambiente di testing, è comunque possibile convalidare la creazione degli utenti accedendo come uno degli utenti nell'intervallo di utenti specificato per la creazione. Ricordarsi di usare il prefisso e il suffisso, insieme al @sipDomain come nome utente. Ecco un esempio:  <em>TestUser20@contoso.net</em>  .
  
> [!NOTE]
> Se gli utenti esistono già, facendo clic sul pulsante Crea utenti verranno aggiornati con eventuali modifiche alla configurazione. 
  
#### <a name="delete-users-button"></a>Pulsante Elimina utenti

Quando fai clic sul **pulsante Elimina utenti** , i parametri di input della scheda verranno convalidati. Se sono presenti errori di convalida, verrà richiesto di correggerli e, se i valori di input sono corretti, gli utenti di test specificati verranno disabilitati ed eliminati da Active Directory. Anche in questo caso, nella parte inferiore di questa scheda verrà visualizzata una barra di stato e non è consigliabile chiudere l'applicazione mentre l'indicatore di stato è attivo.
  
> [!NOTE]
> Sono supportati solo i numeri di telefono formattati con gli Stati Uniti. Telefono sono sempre assegnati agli utenti e tutti gli utenti creati da UserProvisioningTool.exe sono abilitati per VoIP aziendale per impostazione predefinita. Tutti gli scenari in cui viene utilizzato il numero di telefono, ad esempio chiamate Operatore automatico conferenza o CHIAMATE UC-PSTN, utilizzano questo numero di telefono per instradare correttamente le chiamate. Per questo motivo,  *ogni utente*  deve avere un *numero di telefono univoco*  .
  
> [!NOTE]
> **Se è necessario creare utenti due volte, il comando avrà esito negativo a meno che non si utilizzi un codice di area diverso o se gli utenti precedenti sono stati disabilitati utilizzando il cmdlet Disable-CsUser.**
  
> [!IMPORTANT]
> Prima di creare i contatti, è innanzitutto necessario completare la replica degli utenti,che viene eseguita dalla scheda Utenti. 
  
> [!IMPORTANT]
> Se gli utenti sono appena stati creati, è necessario attendere il completamento Skype for Business Server e popolare gli account utente nel database. **Se gli utenti non hanno completato la replica, verrà visualizzato un errore.** È possibile sapere quando gli utenti hanno completato la replica se il servizio Front End di Skype for Business Server 2015 è stato avviato o eseguendo correttamente il cmdlet Get-CsUser sull'ultimo utente del numero totale specificato.
  
#### <a name="contacts-creation-tab"></a>Scheda Creazione contatti

Questa scheda consente di fornire i dettagli dei contatti degli utenti per il test.
  
![Strumento di provisioning degli utenti che mostra la scheda Creazione contenuto.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Per configurare i contatti degli utenti, eseguire le operazioni seguenti:

1. Nel campo **Media contatti per utente** immettere il numero medio di contatti da popolare negli elenchi contatti per ogni utente.
    
2. Selezionare la **casella di** controllo Fisso se si desidera creare un numero uguale di contatti per ogni utente. Se si desidera variare il numero di contatti creati per gli utenti, deselezionare questa casella di controllo.
    
3. Nel campo **Media gruppi di contatti per utente** immettere il numero di gruppi di contatti per utente. Questo numero deve essere inferiore alla media **dei contatti per utente**.
    
4. Nel campo **Percentuale contatti federati/tra pool** assegnare un numero compreso tra 0 e 100. Questa percentuale di contatti verrà creata con gli utenti federati.
    
5. Nel campo **Prefisso utente federato/tra pool** assegnare il nome utente per gli utenti federati che verranno aggiunti agli elenchi di contatti degli utenti locali.
    
6. Nel campo **Dominio SIP utente federato/tra pool** assegnare il nome di dominio SIP degli utenti federati.
    
7. Nella **scheda Creazione** utente verificare che le informazioni siano corrette. I contatti verranno creati dai valori della scheda Creazione utente.
    
8. Fare **clic su Crea** contatti per iniziare la creazione del contatto. Questo processo può richiedere diversi minuti. Al termine, verrà visualizzata una finestra di dialogo con il messaggio "Operazione completata correttamente". È possibile convalidare i contatti creati accedendo come utente creato dalla scheda Creazione utente.
    
    > [!NOTE]
    > Dopo aver creato i contatti, questo strumento riavvierà tutti i Front End Server nel pool di destinazione. L'avvio dei Front End Server potrebbe richiedere più tempo (fino a 2 ore), a seconda del numero di contatti creati da questa operazione. 
  
#### <a name="distribution-list"></a>Lista di distribuzione

Lo Skype for Business Server 2015 Stress and Performance Tool può simulare la funzionalità di espansione della lista di distribuzione nel client Skype for Business 2015. Puoi ignorare questo passaggio se non intendi abilitare l'espansione DL nello strumento di provisioning degli utenti.
  
![Strumento di provisioning degli utenti che mostra la scheda Creazione lista di distribuzione.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
La scheda Lista di distribuzione consente di creare dll che verranno utilizzate dallo strumento Stress and Performance per la funzionalità di espansione delle liste di distribuzione. Prima di creare le dll, Skype for Business Server 2015 deve essere distribuito, inclusa l'esecuzione di ForestPrep. In caso contrario, gli attributi DL non saranno presenti nello schema di Active Directory, quindi lo strumento non sarà in grado di creare dll.
  
### <a name="to-configure-distribution-lists"></a>Per configurare le liste di distribuzione:

1. Nel campo **Numero di** liste di distribuzione, assegnare il numero totale di DLL che si desidera creare (è consigliabile iniziare con un valore che è il doppio del numero di utenti di cui si dispone).
    
2. Nel campo **Prefisso lista di** distribuzione immettere un prefisso che avrà tutte le DLL create, ad esempio *testDL*  . Ciò significa che, con 100 DLL, i nomi DL saranno simili: testDL0, testDL1, fino a testDL99.
    
3. Nel campo **Membri minimi in un elenco dist.** immettere il numero minimo di utenti da inserire in ogni DL.
    
4. Nel campo **Numero massimo di membri in un elenco dist.** immettere il numero massimo di utenti da aggiungere in ogni DL.
    
#### <a name="create-distribution-lists-button"></a>Pulsante Crea liste di distribuzione

Quando si fa clic sul pulsante Crea liste di distribuzione, lo strumento esegue una query in Active Directory per verificare se esistono già liste di distribuzione corrispondenti al prefisso e ai numeri. Lo strumento crea tutte le DLL che non esistono già. Quando si aggiungono membri a queste liste di distribuzione appena create, verranno selezionati gli utenti nell'intervallo specificato nella scheda Creazione utente.
  
#### <a name="location-info-service-config-tab"></a>Scheda Configurazione servizio informazioni percorso

Lo Skype for Business Server 2015 Stress and Performance Tool può anche generare file di configurazione fittizi per il servizio informazioni percorso. Tenere presente che il servizio informazioni percorso in genere non ha un impatto significativo sulle prestazioni dei server. 
  
![Strumento di provisioning degli utenti che mostra la scheda Configurazione servizio informazioni percorso.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Se si sceglie di testare questa funzionalità, compilare i valori nel modulo e fare clic sul pulsante Genera file di configurazione LIS, che creerà .CSV file denominati:
  
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

Dopo aver creato gli utenti (tramite lo strumento di creazione utenti), è possibile configurare i profili utente con lo strumento di configurazione del carico di Skype for Business Server 2015 (UserProfileGenerator.exe).
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Esecuzione dello strumento di Skype for Business Server 2015 Load Configuration

Avviare lo strumento Di configurazione del carico (UserProfileGenerator.exe) e compilare le schede. Questo strumento crea una directory per ognuno dei computer client necessari per eseguire le simulazioni. Ogni directory client include uno script per avviare lo strumento Skype for Business Server 2015 Stress and Performance (LyncPerfTool.exe). Nelle sezioni seguenti vengono forniti esempi di come compilare i campi in ogni scheda dello Skype for Business Server 2015 Load Configuration.
  
> [!IMPORTANT]
> I valori specifici dell'utente utilizzati nello strumento di configurazione del carico (UserProfileGenerator.exe) devono corrispondere ai valori specificati nello strumento di creazione utenti di Skype for Business Server 2015 (UserProvisioningTool.exe) per il pool. 
  
#### <a name="common-configuration-tab"></a>Scheda Configurazione comune

La **scheda Configurazione** comune dello strumento di configurazione del carico è illustrata di seguito. Compilare i campi della scheda Configurazione comune, come descritto nei passaggi seguenti.
  
![Scheda Provisioning utenti che mostra la scheda Configurazione comune.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. Nel campo **Numero di computer disponibili** digitare il numero di computer che si desidera utilizzare per eseguire lo strumento Stress and Performance (LyncPerfTool.exe). È consigliabile avere un computer per ogni 4500 utenti da simulare, ma tale numero può variare se si riduce il livello di carico o si utilizza solo un sottoinsieme delle funzionalità disponibili dello strumento (i livelli di carico sono impostati nella scheda Scenari generali).
    
2. Nel campo **Prefisso per i nomi utente** immettere un prefisso per il campo nome utente di tutti gli utenti. Per accedere all'URI (Uniform Resource Identifier) sarà: *UserPrefix[User Start Index... (Numero di utenti-1)] @User Dominio*  , ad esempio, myUser009@Contoso.com.
    
3. Nel campo **Password per tutti gli** utenti immettere la password utilizzata durante la creazione degli utenti. Se si lascia vuoto questo campo, il nome utente verrà impostato come password.
    
4. Nel campo **Indice inizio utente** immettere l'indice del primo utente da configurare. È possibile configurare intervalli diversi per diversi tipi o livelli di carico, ma è necessario eseguire lo strumento di configurazione del carico (UserProfileGenerator.exe) una volta per l'intervallo che si desidera configurare.
    
5. Nel **campo Numero di** utenti immettere il numero totale di utenti che si desidera configurare.
    
6. Nel campo **Dominio utente** immettere il dominio utilizzato per l'URI SIP. Viene utilizzato per creare l'URI SIP di ogni utente per accedere al server Skype for Business Server Front End Server o edizione Standard 2015 e può essere diverso dal Dominio account.
    
7. Nel campo **Dominio account** immettere l'accesso al dominio di Servizi di dominio Active Directory.
    
8. Nel campo **Percentuale MPOP** (percentuale di più punti di presenza) assegnare un valore per la percentuale di utenti connessi da più computer o dispositivi, ad esempio il 10%.
    
9. Immettere il numero massimo di endpoint simultanei nel **campo Accesso al secondo (per** istanza). Questo è il numero massimo di log in per gli utenti e il consiglio è una frequenza inferiore/uguale a 2 al secondo (<=2).
    
10. Nel campo **Proxy di accesso o FQDN** pool immettere il nome di dominio completo (FQDN) del server a cui si desidera che i client si connettano. Se gli utenti eccedono esternamente, è necessario digitare il proxy di accesso. Se gli utenti sono interni, assegnare il nome di dominio completo del Enterprise pool o edizione Standard server.
    
11. Nel campo **Porta** immettere la porta che si desidera che gli utenti utilizzino per SIP (il valore predefinito è 5061).
    
12. Per il **campo Server di rete Impostazioni**, assegnare il proxy di accesso o l'FQDN del pool e, di nuovo, la **porta**. Queste impostazioni vengono utilizzate solo per la simulazione del carico degli endpoint esterni.
    
#### <a name="general-scenarios-tab"></a>Scheda Scenari generali

![Load Configuration Tool che mostra la scheda General Scenarios.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
È possibile configurare i livelli di carico e i parametri per ognuno degli scenari generali offerti determinando gli elementi che si desidera eseguire o lasciare disabilitati. Ecco le opzioni generali:
  
> [!NOTE]
> I valori del livello di carico per tutti i campi, ad esempio Local Information Services, **sono Disabled**, **Low**, **Medium**, **High** o **Custom**. Se si seleziona qualsiasi impostazione, ma Disabilitata, vengono generate configurazioni per ogni client. Risultati elevati nel carico massimo supportato sul server. medio è il 60% del carico elevato; low è 30%. 
  
- **Messaggistica istantanea -** Sono incluse le conferenze e peer-to-peer; scegliere il valore appropriato per Livello di carico.
    
- **Audioconferenza -** Scegliere un livello di carico solo per le *audioconferenze*  . Le chiamate peer-to-peer verranno affrontate più avanti nella **sezione Scenari** vocali. Apri la **scheda Avanzate** per abilitare MultiView.
    
- **Condivisione applicazioni -** Scegliere un livello di carico per la condivisione delle applicazioni.
    
- **Collaborazione dati -** Scegliere un livello di carico per la collaborazione dati, che include le conferenze dati.
    
- **Espansione lista di distribuzione -** Fare clic **sul pulsante** Avanzate e compilare il campo con gli stessi valori configurati nella scheda DL dello Strumento di creazione utente (UserProvisioningTool.exe). Scegliere un livello di carico.
    
- **Query Web rubrica -** Si tratta del servizio di ricerca della rubrica anziché del download del file della rubrica. Se si desidera abilitare questa impostazione per i download di file della rubrica, fare clic sul **pulsante Avanzate e** **impostare EnableABSDownload** su True. Assegnare un valore per il livello di carico.
    
- **Response Group Service -** Fare clic **sul pulsante** Avanzate e specificare gli URI dei Response Group già creati durante il provisioning degli agenti di Response Group Service. È necessario scegliere almeno un Response Group. Per usare altro, separare i Response Group con punti e virgola. Aggiornare **RGSUriSuffixStartIndex** e **RGSUriSuffixEndIndex** ai valori effettivi. Scegliere un livello di carico.
    
- **Location Information Services -** Selezionare un livello di carico abilitato o disabilitato.
    
> [!NOTE]
> Accanto a ognuno degli scenari è presente un pulsante Avanzate e un set di caselle di controllo che consentono di modificare l'impostazione predefinita. 
  
- Scegliendo  *Ad-hoc*  , lo strumento consentirà di generare la simulazione delle conferenze che verranno create durante l'ora.
    
- La  *scelta di Conf di*  grandi dimensioni significa che verrà simulato uno scenario di conferenza di grandi dimensioni.
    
-  *External*  indica a questo strumento di simulare anche gli utenti esterni.
    
Questi pulsanti e caselle di controllo sono valori aggiuntivi specifici per ogni scenario e modificheranno il comportamento dello strumento Stress and Performance e renderanno possibile la personalizzazione.
  
Per ogni scenario nella scheda Scenari generali (ad eccezione di Location Information Services), se il valore di Livello di carico è **Personalizzato**, la frequenza di conversazione verrà calcolata utilizzando il campo corrispondente nella finestra di dialogo Avanzate. Il nome del campo può variare a seconda dello scenario, ma la descrizione del campo indica: NOTA Questo numero verrà utilizzato solo se è selezionato Personalizzato dal  *menu a discesa*  .
  
I valori **High**, **Medium** e **Low** altereranno le frequenze di conversazione per modalità in linea con il modello utente che è un equilibrio di tutti gli scenari. Se è necessario modificare il livello di carico per modalità a causa di una differenza nell'utilizzo previsto, usa una frequenza di conversazione personalizzata.
  
#### <a name="voice-scenarios-tab"></a>Scheda Scenari vocali

Questa è la scheda per la configurazione di tutti gli scenari correlati alla voce.
  
![Scheda Load Configuration Tool Voice Scenarios.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Le opzioni disponibili sono:
  
- **VoIP -** Fare clic **sul pulsante** Avanzate e aggiungere i valori per i campi PhoneAreaCode e LocationProfile (dial plan). Verrà inoltre restituito un valore per Livello di carico. Se si sceglie un livello di carico per VoIP o Gateway UC/PSTN abilitato, verrà generata una rete PSTN (Public Switched Telephone Network) per il file di configurazione delle comunicazioni unificate per simulare le chiamate esterne.
    
- **Gateway UC/PSTN -** È necessario scegliere un valore livello di carico e quando si sceglie un valore diverso da Disabilitato, è anche necessario fornire un valore per il codice di area PSTN facendo clic sul **pulsante** Avanzate. Fare **clic su** Aggiungi in Mediation Server e PSTN. Assicurati di avere una route configurata per il codice di area.
    
    > [!TIP]
    > È possibile utilizzare il Pannello di controllo di Skype for Business o Skype for Business Management Shell per verificare la configurazione della route vocale. 
  
- **Operatore conferenza-** Fornire un valore per Livello di carico. Qualsiasi valore diverso da Disabilitato abiliterà il **campo Numero di** telefono. Immetti il numero di telefono del Operatore automatico che vuoi usare. Fare **clic su** Avanzate e assegnare un valore per **il campo LocationProfile** .
    
- **Servizio parcheggio di chiamata -** In questo caso, specificare un livello di carico.
    
- **Mediation Server e PSTN -** Ogni Mediation Server che si desidera utilizzare necessita del proprio simulatore PSTN. Dopo aver determinato quale client si utilizzerà per il simulatore, configurare il Mediation Server per instradare le chiamate a tale computer nel simulatore PSTN configurato. Fare clic **sul** pulsante Aggiungi per configurare un valore per il Mediation Server.
    
    > [!NOTE]
    > Accanto a ogni scenario è presente un pulsante Avanzate. Le finestre di dialogo avanzate contengono impostazioni specifiche per ogni scenario che modificano il comportamento dello strumento Stress and Performance e abilitano la personalizzazione. > Per ogni scenario nella scheda Scenari vocali, se il valore di Livello di carico è **Personalizzato**, la frequenza di conversazione verrà calcolata utilizzando il campo corrispondente nella finestra di dialogo Avanzate. Il nome del campo può variare a seconda dello scenario, ma la descrizione del campo indica: NOTA Questo numero verrà utilizzato solo se è selezionato Personalizzato dal  *menu a discesa*  .
  
#### <a name="web-app-tab"></a>Scheda App Web

![Carica strumento di configurazione, scheda app Web.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App supporta gli scenari di conferenza tramite il server UCWA (Unified Communications Web API) installato in un front-end server. Utilizzare la scheda App Web per configurare tutti gli scenari correlati all'app Web. Le opzioni sono:
  
- **General Web App Impostazioni -** Fare clic sul pulsante Additional **Impostazioni** e impostare **ReachTargetServerUrl** sull'IP virtuale (VIP) del pool Front End VIP.
    
- **Condivisione applicazioni -** Selezionare un valore per Livello di carico.
    
- **Collaborazione dati -** Selezionare un valore per Livello di carico.
    
- **Messaggistica istantanea -** Selezionare un valore per Livello di carico.
    
- **Servizi di conferenza vocale -** Selezionare un valore per Livello di carico.
    
> [!NOTE]
> Accanto a ognuno degli **scenari è presente** un pulsante Avanzate. Le finestre di dialogo avanzate contengono valori specifici per ogni scenario che modificheranno il comportamento dello strumento Stress and Performance e abiliteranno la personalizzazione.> Per ognuno degli scenari dell'app Web, se il livello di carico è **Personalizzato**, verrà utilizzato il valore specificato nel campo **ConversationsPerHour** anziché il valore predefinito.
  
#### <a name="mobility-tab"></a>Scheda Dispositivi mobili

Utilizzare questa scheda per configurare tutti gli scenari correlati alla mobilità.
  
![Scheda Per dispositivi mobili dello strumento di configurazione del carico.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Di seguito sono disponibili le opzioni seguenti:
  
- **General Mobility Impostazioni -** Fare clic su Impostazioni  e impostare il campo UcwaTargetServerUrl sull'IP virtuale (VIP) del pool di server Director o sul VIP del pool Front End.
    
- **Presenza e messaggistica istantanea P2P/Audio -** Selezionare un valore per Livello di carico per abilitare la simulazione per dispositivi mobili.
    
> [!NOTE]
> Accanto a ognuno degli **scenari è presente** un pulsante Avanzate. Le finestre di dialogo avanzate contengono valori specifici per ogni scenario che modificheranno il comportamento dello strumento Stress and Performance e abiliteranno la personalizzazione.> Per ognuno degli scenari per dispositivi mobili, se il livello di carico è **Personalizzato**, verrà utilizzato il valore specificato nel campo **ConversationsPerHour** anziché il valore predefinito.
  
#### <a name="summary-tab"></a>Scheda Riepilogo

La scheda Riepilogo indica quali utenti utilizzare per ognuno degli scenari.
  
![Scheda Riepilogo dello strumento di configurazione di caricamento.](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
La scheda Riepilogo indica quali utenti utilizzare per ognuno degli scenari. 
  
È possibile configurare manualmente gli intervalli di numeri utente selezionando la casella  di controllo Abilita generazione di intervalli utente personalizzati e quindi facendo doppio clic nello scenario nella tabella contenente l'intervallo di utenti che si desidera personalizzare.
  
Check **(RunClient.bat) Add sign-in delay when starting** in order to include delays in the generated batch files to correspond to the sign-in rate. Ciò è utile per evitare sovraccarichi del server quando si accede a un numero elevato di utenti.
  
Fare **clic su** Genera file e selezionare la cartella in cui si desidera generare la configurazione. Quando i file sono stati creati correttamente, verrà visualizzata una finestra di dialogo.
  
![La finestra di messaggio "Carica file di configurazione generati correttamente". Basta fare clic su OK.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Eseguire LyncPerfTool
<a name="BKMK_RunTool"> </a>

È necessario creare utenti, contatti e scenari prima di eseguire lo strumento Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe). Per informazioni dettagliate sull'utilizzo degli strumenti per eseguire queste azioni, vedere [Creare utenti](using-the-tool.md#BKMK_CreateUsersAndContacts) e contatti e [Configurare il profilo](using-the-tool.md#BKMK_UserProfile) utente in precedenza in questo articolo. L'esecuzione di questi strumenti genererà anche un file che verrà eseguito con lo strumento Stress and Performance come parte di un file batch con i parametri obbligatori inclusi.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Esecuzione dello strumento Skype for Business Server 2015 Stress and Performance

Lo strumento di configurazione del carico (UserProfileGenerator.exe) crea un file batch che consente di eseguire lo strumento Stress and Performance (LyncPerfTool.exe) registrando i contatori delle prestazioni e caricando il file di configurazione XML. Il file batch esegue un'istanza di LyncPerfTool.exe per ogni file di configurazione. Per eseguire il file batch, attenersi alla seguente procedura:
  
### <a name="run-the-stress-and-performance-test"></a>Eseguire il test stress e prestazioni

1. Copiare la cartella con le cartelle di configurazione e i file all'interno della directory che LyncPerfTool.exe in ogni computer client. Ad esempio, se i file di configurazione sono stati generati nella cartella denominata 1.28_13.16.16, copiare tale cartella nella cartella in cui è presente LyncPerfTool.exe. Eseguire questa operazione su ogni client.
    
2. Passare alla cartella del client ed eseguire lo script batch **RunClient** . È possibile fare doppio clic sul file batch in Windows Explorer e verranno eseguiti tutti i file di configurazione per il client. È inoltre possibile eseguire lo script da una cartella client utilizzando la sintassi seguente:
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Per eseguire lo strumento Stress and Performance direttamente, aprire un prompt dei comandi e digitare il comando seguente nella riga di comando (e quando si esegue questa operazione per la prima volta,  `regsvr32 /i /n /s LyncPerfToolPerf.dll`assicurarsi di registrare i contatori delle prestazioni , come illustrato nella nota più avanti in questo argomento):
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

Per fare in modo che lo strumento visualizza i valori nel file di configurazione,  `/displayfile` includi il parametro nel comando precedente, in modo che sia simile al seguente:
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Per  *terminare*  il processo, premere CTRL+C.
  
> [!NOTE]
> Prima di eseguire direttamente lo strumento Stress and Performance, è necessario registrare i contatori delle prestazioni tramite il comando seguente:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Ogni istanza dello strumento Stress and Performance avviata inizierà immediatamente ad accedere agli utenti, in genere con una velocità di un utente al secondo. 
  
La frequenza di accesso utente massima per il pool è di circa 12 al secondo. Ciò significa che non è consigliabile avviare più di 12 istanze LyncPerfTool.exe contemporaneamente mentre gli utenti stanno ancora accedendo. Un migliaio di utenti avrà circa 20 minuti per accedere completamente all'uno al secondo.
  
## <a name="interpreting-the-results"></a>Interpretazione dei risultati
<a name="BKMK_Interpret"> </a>

Lo Skype for Business Server 2015 Stress and Performance Tool include numerosi contatori che consentono di comprendere cosa sta facendo il client e se si verificano problemi.
  
### <a name="client-counters"></a>Contatori client

Ogni istanza di LyncPerfTool.exe in esecuzione dispone di un'istanza separata dei contatori. Ogni istanza è denominata dal relativo ID processo. Se i client sono sovraccarichi possono verificarsi altri problemi. Per evitare questi problemi:
  
- Monitorare l'utilizzo della CPU e della memoria nei computer client. Se la CPU è costantemente superiore al 90%, ridurre il numero di utenti.
    
- Quando il footprint di memoria è elevato, potrebbero verificarsi problemi se lo spazio del file di pagina inizia a essere insufficiente. Verificare che l'addebito commit non sia in grado di raggiungere il limite del computer. Se si verificano limiti di memoria, è consigliabile aumentare le dimensioni del file di pagina o ridurre il numero di utenti.
    
Ecco un elenco dei contatori delle prestazioni chiave:
  
**Informazioni generali**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Tempo impiegato in minuti  <br/> |Tempo trascorso dall'avvio del processo.  <br/> |
|Endpoint attivi  <br/> |Numero di endpoint attualmente connessi al server.  <br/> |
|Accessi non riusciti  <br/> |Numero totale di errori di accesso degli endpoint.  <br/> |
|Tentativi di accesso  <br/> |Numero totale di tentativi di accesso all'endpoint.  <br/> |
|Endpoint disconnessi  <br/> |Numero totale di endpoint disconnessi.  <br/> |
   
**Informazioni sulla presenza**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate SetPresence  <br/> |Numero totale di tentativi di modifica della presenza. Per diversi tipi di modifiche della presenza, vedere il contatore delle prestazioni Chiamate SetPresence (tipo presenza).  <br/> |
|Risposte NNN per SetPresence  <br/> |Numero totale di codici di risposta nnn ricevuti dal server.  <br/> |
|Chiamate GetPresence  <br/> |Numero totale di tentativi di richiesta di presenza get.  <br/> |
|Risposte NNN per GetPresence  <br/> |Numero totale di codici di risposta nnn ricevuti dal server.  <br/> |
   
**Informazioni sul servizio Rubrica**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|ABS Full/Delta File Downloads Attempted  <br/> |Numero totale di richieste di download di file complete o delta tentate.  <br/> |
|Download di file ABS completi/delta riusciti  <br/> |Numero totale di richieste di download di file complete o delta tentate.  <br/> |
|Contatori correlati al servizio Query Web Rubrica  <br/> |Contatori correlati al download del file della rubrica.  <br/> |
|Chiamate WS ABS tentate  <br/> |Numero totale di richieste del servizio Query Web rubrica tentate.  <br/> |
|Chiamate WS ABS riuscite  <br/> |Numero totale di richieste del servizio Query Web Rubrica che hanno restituito un codice di risposta corretto.  <br/> |
|Chiamate WS ABS non riuscite  <br/> |Numero totale di richieste del servizio Query Web Rubrica che hanno restituito un codice di risposta di errore.  <br/> |
   
> [!NOTE]
> Questa categoria include i contatori utilizzati per monitorare i download dei file del servizio Rubrica (ABS) e le richieste del servizio Query Web rubrica. 
  
**Informazioni sulla lista di distribuzione**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate tentate  <br/> |Numero totale di richieste del servizio Web di espansione delle liste di distribuzione (DLX) tentate.  <br/> |
|Chiamate riuscite  <br/> |Numero totale di richieste del servizio Web DLX che hanno restituito un codice di risposta corretto.  <br/> |
|Chiamate non riuscite  <br/> |Numero totale di richieste del servizio Web DLX che hanno restituito un codice di risposta di errore.  <br/> |
   

  
> [!NOTE]
> I contatori delle prestazioni elencati di seguito riportano i numeri per tutte le chiamate VoIP (Voice over IP), incluse le chiamate a Mediation Server, A/V Conferencing Server, Edge Server, applicazione Response Group e Conference Operatore automatico, quando questi scenari sono abilitati. 
  
**Informazioni di base VoIP**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate attive  <br/> |Numero totale di chiamate vocali in ingresso/in uscita attualmente in corso.  <br/> |
|Chiamate terminate  <br/> |Numero totale di chiamate vocali in ingresso/in uscita già terminate.  <br/> |
|Chiamate rifiutate  <br/> |Numero totale di chiamate vocali in arrivo rifiutate.  <br/> |
|Chiamate in ingresso/in uscita tentate  <br/> |Numero totale di chiamate vocali in ingresso/in uscita tentate.  <br/> |
|Chiamate in arrivo/in uscita stabilite  <br/> |Numero totale di chiamate vocali in ingresso/in uscita stabilite.  <br/> |
|Chiamate ricevute NNN  <br/> |Numero totale di codici di risposta nnn ricevuti dal server.  <br/> |
|VoIP Pass Rate (%)  <br/> |Totale chiamate stabilite/Totale chiamate tentate.  <br/> |
   
**Informazioni sulle chiamate al servizio Response Group**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate attive  <br/> |Numero totale di chiamate attive all'applicazione Response Group.  <br/> |
|Chiamate tentate  <br/> |Numero totale di chiamate tentate.  <br/> |
   
**Informazioni sulle chiamate di messaggistica istantanea**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate attive  <br/> |Numero totale di chiamate di messaggistica istantanea in arrivo/in uscita in corso.  <br/> |
|Chiamate terminate  <br/> |Numero totale di chiamate di messaggistica istantanea in ingresso/in uscita già terminate.  <br/> |
|Chiamate ricevute NNN  <br/> |Numero totale di codici di risposta nnn ricevuti dal server.  <br/> |
|Messaggi istantanei ricevuti/inviati  <br/> |Numero totale di messaggi ricevuti o inviati per tutte le sessioni.  <br/> |
|Chiamate in ingresso/in uscita tentate  <br/> |Numero totale di chiamate di messaggistica istantanea in ingresso/in uscita tentate.  <br/> |
|Chiamate in arrivo/in uscita stabilite  <br/> |Numero totale di chiamate ai messaggi istantanei in ingresso/in uscita stabilite.  <br/> |
   
**Informazioni sulle chiamate di condivisione app**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate attive  <br/> |Numero totale di chiamate di condivisione applicazioni in ingresso/in uscita in corso.  <br/> |
|Chiamate terminate  <br/> |Numero totale di chiamate di condivisione applicazioni in ingresso/in uscita già terminate.  <br/> |
|Chiamate ricevute NNN  <br/> |Numero totale di codici di risposta nnn ricevuti dal server.  <br/> |
|Chiamate in ingresso/in uscita tentate  <br/> |Numero totale di chiamate di condivisione applicazioni in ingresso/in uscita tentate.  <br/> |
|Chiamate in arrivo/in uscita stabilite  <br/> |Numero totale di chiamate di condivisione applicazioni in ingresso/in uscita stabilite.  <br/> |
   
**Informazioni sulle chiamate CAA**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate attive  <br/> |Numero totale di chiamate PSTN (Public Switched Telephone Network) in ingresso/in uscita attualmente in corso.  <br/> |
|Chiamate terminate  <br/> |Numero totale di chiamate PSTN in ingresso/in uscita già terminate.  <br/> |
|Chiamate in ingresso/in uscita tentate  <br/> |Numero totale di chiamate PSTN in ingresso/in uscita tentate.  <br/> |
|Chiamate in arrivo/in uscita stabilite  <br/> |Numero totale di chiamate PSTN in ingresso/in uscita stabilite.  <br/> |
   
**Informazioni conferenza**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Conferenze di messaggistica istantanea attive  <br/> |Numero totale di conferenze di messaggistica istantanea in corso.  <br/> |
|Conferenze audio/video attive  <br/> |Numero totale di conferenze audio/video (A/V) in corso.  <br/> |
|Conferenze di condivisione applicazioni attive  <br/> |Numero totale di conferenze di condivisione applicazioni in corso.  <br/> |
|Numero di partecipanti  <br/> |Numero totale di partecipanti attualmente connessi alle conferenze.  <br/> |
|Errore pianificazione conferenze  <br/> |Numero totale di errori durante il tentativo di pianificare una conferenza.  <br/> |
|Errore di partecipazione alla conferenza  <br/> |Numero totale di errori durante il tentativo di connessione a una conferenza.  <br/> |
   
**Contatori client UCWA**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Numero totale di join IMMCU riusciti  <br/> |Numero totale di conferenze di messaggistica istantanea unite.  <br/> |
|Numero totale di join DMCU riusciti  <br/> |Numero totale di conferenze audio/video unite.  <br/> |
   

