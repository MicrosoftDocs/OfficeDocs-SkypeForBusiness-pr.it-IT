---
title: Uso dello strumento di stress e prestazioni Skype for Business Server 2015
ms.reviewer: ''
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
description: Per eseguire lo strumento di stress e prestazioni di Skype for Business Server 2015, è necessario essere in grado di gestire sia utenti, contatti che profili utente, configurare lo strumento per l'esecuzione e quindi esaminare l'output o i risultati prodotti dallo strumento.
ms.openlocfilehash: 300da4109ddbdbf06f6dcfbe241cc45c83ec82ca
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675728"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Uso dello strumento di stress e prestazioni Skype for Business Server 2015
 
Per eseguire lo strumento di stress e prestazioni di Skype for Business Server 2015, è necessario essere in grado di gestire sia utenti, contatti che profili utente, configurare lo strumento per l'esecuzione e quindi esaminare l'output o i risultati prodotti dallo strumento.
  
L'esecuzione dello strumento di stress e prestazioni di Skype for Business Server 2015 include quattro aree (l'eseguibile è LyncPerfTool.exe):
  
- [Creare utenti e contatti](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configurare il profilo utente](using-the-tool.md#BKMK_UserProfile)
    
- [Eseguire LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpretazione dei risultati](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Creare utenti e contatti
<a name="BKMK_CreateUsersAndContacts"> </a>

È necessario usare Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) per creare utenti e contatti per i test di stress e prestazioni.
  
Questo è un elenco di termini utili che potrebbero essere utili durante la lettura degli argomenti:
  
- **Unità organizzativa** : unità organizzativa Active Directory Domain Services (AD DS).
    
- **Federated/Cross Pool** : utenti che possono comunicare con gli utenti da altri servizi di messaggistica istantanea.
    
- **Liste di distribuzione** o DLs. Si tratta di oggetti in Servizi di dominio Active Directory che contengono un elenco di utenti di Servizi di dominio Active Directory. Vengono usati per facilitare le comunicazioni tra gruppi di persone.
    
- **Location Info Service** : il servizio Skype for Business Server 2015 che, quando è abilitato e configurato per telefono, consente il recupero della posizione fisica per i servizi Enhanced 911 (E911).
    
- **U.S. Telefono Numbers** : Telefono numeri assegnati all'utente oltre all'URI SIP usato per il routing delle chiamate in ingresso e in uscita in Reverse Number Lookup (RNL).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Creare utenti e contatti usando UserProvisioningTool.exe

> [!NOTE]
> Prima ancora di iniziare, assicurarsi di aver eseguito l'accesso come membro del gruppo di sicurezza Domain Admins per eseguire questo strumento. È necessario eseguire questa operazione, perché si creeranno utenti di Active Directory. 
  
È necessario usare lo strumento di provisioning utenti Skype for Business Server per creare utenti e contatti per la simulazione del carico.
  
Lo **strumento di provisioning utenti Skype for Business Server** viene installato con il pacchetto **dello strumento di stress e prestazioni Skype for Business Server**. Assicurarsi che il programma di installazione del pacchetto (CapacityPlanningTool.msi) sia stato eseguito nel Front End Server o nel server edizione Standard che si intende testare.
  
È possibile avviare lo strumento di provisioning utenti Skype for Business Server eseguendo il file UserProvisioningTool.exe (che si trova in %InstalledDirectory%LyncStressAndPerfTool\LyncStress) nel Front End Server o nel server edizione Standard.
  
> [!IMPORTANT]
> Quando si crea un numero elevato di utenti ,ad esempio 10.000 o più, eseguire il UserProvisioningTool.exe. È necessario eseguire questa operazione perché lo strumento creerà e configurarà  *nuovi*  utenti di ACTIVE Directory.
  
Quando si apre lo strumento di provisioning utenti, fare clic su Configurazione e selezionare Configurazione di carico. 
  
Per iniziare a configurare utenti e contatti, caricare il file predefinito incluso nel pacchetto, denominato "SampleData.xml". In questo modo i campi verranno prepopolati con dati di esempio che sarà necessario modificare per renderli pertinenti per la distribuzione.
  
Se si dispone di un file XML preconfigurato che contiene già le impostazioni personalizzate, è possibile caricarlo. Compilare i campi dello strumento di provisioning utenti, come descritto nelle sezioni seguenti.
  
### <a name="to-configure-server-options"></a>Per configurare le opzioni del server:

1. Nel campo **FQDN del pool Front End** digitare il nome di dominio completo (FQDN) del server edizione Standard o il pool Front End in cui si desidera ospitare gli utenti.
    
2. Nel campo **Prefisso nome utente** digitare un prefisso che si vuole usare per interrompere i nomi utente a scopo di test, ad esempio "TestUser".
    
3. Nel campo **Password** digitare una password che verrà usata in tutti gli account utente di test.
    
4. Nel campo **Account Domain (Dominio account** ) digitare il nome di dominio del dominio AD corrente (quello in cui si desidera creare gli utenti di test).
    
5. Nel campo **Unità organizzativa** digitare il nome del dominio di Active Directory in cui si desidera creare questi utenti di test. Se l'unità organizzativa non esiste già, verrà creata automaticamente.
    
6. Nel campo **Telefono Prefisso** digitare il prefisso a tre cifre da usare in tutti gli account utente di test. Assicurarsi che il prefisso scelto non sia in conflitto con i codici di area di altri utenti in AD.
    
7. Fare clic per selezionare la casella di controllo **Abilitata** per la voce, se si desidera abilitare gli utenti di test per VoIP aziendale.
    
8. Nel campo **Numero di utenti** assegnare il numero totale di utenti di test da creare.
    
9. Nel campo **Indice iniziale** assegnare il numero iniziale che verrà usato come suffisso al prefisso del nome utente( ad esempio, il prefisso è "TestUser" e il nome terminerà con "0" nell'esempio seguente).
    
     ![Strumento di provisioning utente che mostra la scheda di creazione dell'utente.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Pulsante Crea utenti

Quando si fa clic sul pulsante **Crea utenti** , i parametri di input immessi vengono convalidati. In caso di errori di convalida, verrà richiesto di correggerli. In alternativa, se tutti i valori sono corretti, gli utenti inizieranno a essere visualizzati in Active Directory (in qualsiasi unità organizzativa specificata). Verrà visualizzata una barra di stato nella parte inferiore dello strumento durante l'esecuzione. Non chiudere l'applicazione mentre l'indicatore di stato è attivo.
  
La creazione dell'utente richiede tempo, quindi pianificare di conseguenza. Questo processo può richiedere da diversi minuti per alcuni utenti a poche ore per un numero elevato di utenti.
  
Se non si ha accesso al controller di dominio ACTIVE Directory nell'ambiente di test, è comunque possibile convalidare la creazione dell'utente accedendo come uno degli utenti nell'intervallo di utenti specificato per la creazione. Ricordarsi di usare il prefisso e il suffisso, insieme al @sipDomain come nome utente. Ecco un esempio:  <em>TestUser20@contoso.net</em>  .
  
> [!NOTE]
> Se gli utenti esistono già, fare clic sul pulsante Crea utenti per aggiornarli con eventuali modifiche alla configurazione. 
  
#### <a name="delete-users-button"></a>Pulsante Elimina utenti

Quando si fa clic sul pulsante **Elimina utenti** , i parametri di input della scheda verranno convalidati. In caso di errori di convalida, verrà richiesto di correggerli e, se i valori di input sono corretti, gli utenti di test specificati verranno disabilitati ed eliminati da Active Directory. Anche in questo caso, nella parte inferiore di questa scheda verrà visualizzata una barra di stato e non è consigliabile chiudere l'applicazione mentre l'indicatore di stato è attivo.
  
> [!NOTE]
> Sono supportati solo i numeri di telefono formattati negli Stati Uniti. Telefono numeri vengono sempre assegnati agli utenti e tutti gli utenti creati da UserProvisioningTool.exe sono abilitati per VoIP aziendale per impostazione predefinita. Tutti gli scenari che usano il numero di telefono, ad esempio Operatore automatico conferenza o chiamate UC-PSTN, usano questo numero di telefono per instradare correttamente le chiamate. Per questo motivo,  *ogni utente*  deve avere un *numero di telefono univoco*  .
  
> [!NOTE]
> **Se è necessario creare utenti due volte, il comando avrà esito negativo a meno che non si usi un prefisso diverso o se gli utenti precedenti sono stati disabilitati usando il cmdlet Disable-CsUser.**
  
> [!IMPORTANT]
> Prima di creare i contatti, è prima necessario completare la replica utente (operazione eseguita dalla scheda Utenti). 
  
> [!IMPORTANT]
> Se gli utenti sono appena stati creati, sarà necessario attendere il completamento della replica Skype for Business Server e popolare gli account utente nel database. **Se gli utenti non hanno completato la replica, verrà visualizzato un errore.** Si saprà quando gli utenti hanno terminato la replica se il servizio Front End Skype for Business Server 2015 è stato avviato o eseguendo correttamente il cmdlet Get-CsUser nell'ultimo utente del numero totale specificato.
  
#### <a name="contacts-creation-tab"></a>Scheda Creazione contatti

Questa scheda consente di fornire i dettagli dei contatti degli utenti per i test.
  
![Strumento di provisioning utenti che mostra la scheda Creazione contenuto.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Per configurare i contatti degli utenti, eseguire le operazioni seguenti:

1. Nel campo **Contatti medi per utente** immettere il numero medio di contatti da popolare negli elenchi di contatti per ogni utente.
    
2. Selezionare la casella di controllo **Fisso** se si desidera creare un numero uguale di contatti per ogni utente. Se si vuole variare il numero di contatti creati per gli utenti, deselezionare questa casella di controllo.
    
3. Nel campo **Gruppi di contatti medi per utente** immettere il numero di gruppi di contatti per utente. Questo numero deve essere inferiore alla **media dei contatti per utente**.
    
4. Nel campo **Percentuale contatti federati/tra pool** assegnare un numero compreso tra 0 e 100. Questa percentuale di contatti verrà creata con gli utenti federati.
    
5. Nel campo **Prefisso utente federato/multi pool** assegnare il nome utente per gli utenti federati che verranno aggiunti agli elenchi di contatti degli utenti locali.
    
6. Nel campo **Dominio SIP utente federato/multi pool** assegnare il nome di dominio SIP degli utenti federati.
    
7. Nella scheda **Creazione utente** verificare che le informazioni siano corrette. I contatti verranno creati dai valori nella scheda Creazione utente.
    
8. Fare clic su **Crea contatti** per iniziare la creazione del contatto. Questo processo può richiedere alcuni minuti. Al termine, verrà visualizzata una finestra di dialogo con il messaggio "Operazione completata correttamente". È possibile convalidare i contatti creati accedendo come utente creato dalla scheda Creazione utente.
    
    > [!NOTE]
    > Dopo aver creato i contatti, questo strumento riavvierà tutti i Front End Server nel pool di destinazione. L'avvio dei Front End Server può richiedere più tempo (fino a 2 ore), a seconda del numero di contatti creati da questa operazione. 
  
#### <a name="distribution-list"></a>Lista di distribuzione

Lo strumento di stress e prestazioni Skype for Business Server 2015 può simulare la funzionalità di espansione della lista di distribuzione (DL) nel client Skype for Business 2015. È possibile ignorare questo passaggio se non si intende abilitare l'espansione dl nello strumento Di provisioning utenti.
  
![Strumento di provisioning utenti che mostra la scheda Creazione lista di distribuzione.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
La scheda Lista di distribuzione consente di creare DLs che lo strumento Stress and Performance userà per la funzionalità di espansione della lista di distribuzione. Prima di creare elenchi di dominio, è necessario distribuire Skype for Business Server 2015, inclusa l'esecuzione di ForestPrep. Se questa operazione non viene eseguita, gli attributi DL non esisteranno nello schema di Active Directory, quindi lo strumento non sarà in grado di creare DLs.
  
### <a name="to-configure-distribution-lists"></a>Per configurare le liste di distribuzione:

1. Nel campo **Numero di liste di distribuzione** assegnare il numero totale di DLs che si desidera creare. È consigliabile iniziare con un valore che è il doppio del numero di utenti disponibili.
    
2. Nel campo **Prefisso lista di distribuzione** immettere un prefisso che avrà tutte le DLs create, ad esempio *testDL*  . Ciò significa che, a 100 DL, i nomi DL saranno simili a: testDL0, testDL1, fino a testDL99.
    
3. Nel campo **Membri minimi di un elenco dist.** Immettere il numero minimo di utenti da inserire in ogni DL.
    
4. Nel campo **Numero massimo di membri in un elenco dist.** Immettere il numero massimo di utenti da aggiungere in ogni DL.
    
#### <a name="create-distribution-lists-button"></a>Pulsante Crea liste di distribuzione

Quando si fa clic sul pulsante Crea liste di distribuzione, lo strumento esegue una query in Active Directory per verificare se esistono già liste di distribuzione corrispondenti al prefisso e ai numeri. Lo strumento crea tutti gli elenchi di dominio che non esistono già. Quando si aggiungono membri a queste liste di distribuzione appena create, si sceglieranno gli utenti dall'intervallo specificato nella scheda Creazione utente.
  
#### <a name="location-info-service-config-tab"></a>Scheda Configurazione del servizio Informazioni sulla posizione

Lo strumento di stress e prestazioni di Skype for Business Server 2015 può anche generare file di configurazione fittizi per Location Information Service. Si noti che il Servizio Informazioni sulla posizione in genere non ha un impatto significativo sulle prestazioni dei server. 
  
![Strumento di provisioning utenti che mostra la scheda Configurazione servizio Informazioni percorso.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Se si sceglie di testare questa funzionalità, compilare i valori nel modulo e fare clic sul pulsante Genera file di configurazione LIS, che creerà .CSV file denominati:
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
Per importare questi file nel database LIS, usare i cmdlet di PowerShell seguenti:
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Configurare il profilo utente
<a name="BKMK_UserProfile"> </a>

Dopo aver creato gli utenti tramite lo strumento di creazione utenti, è possibile configurare i profili utente con lo strumento di configurazione del carico Skype for Business Server 2015 (UserProfileGenerator.exe).
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Esecuzione dello strumento configurazione del carico di Skype for Business Server 2015

Avviare lo strumento Configurazione del carico (UserProfileGenerator.exe) e compilare le schede. Questo strumento crea una directory per ognuno dei computer client necessari per eseguire le simulazioni. Ogni directory client include uno script per avviare lo strumento di stress e prestazioni Skype for Business Server 2015 (LyncPerfTool.exe). Le sezioni seguenti forniscono esempi di come compilare i campi in ogni scheda dello strumento configurazione del carico Skype for Business Server 2015.
  
> [!IMPORTANT]
> I valori specifici dell'utente usati nello strumento configurazione del carico (UserProfileGenerator.exe) devono corrispondere ai valori specificati nel Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) per il pool. 
  
#### <a name="common-configuration-tab"></a>Scheda Configurazione comune

Di seguito è illustrata la scheda **Configurazione comune** dello strumento configurazione del carico. Compilare i campi della scheda Configurazione comune, come descritto nei passaggi seguenti.
  
![Scheda Provisioning utenti che mostra la scheda Configurazione comune.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. Nel campo **Numero di computer disponibili** digitare il numero di computer da usare per eseguire lo strumento Stress and Performance (LyncPerfTool.exe). È consigliabile avere un computer per ogni 4500 utenti simulati, ma tale numero può variare se si riduce il livello di carico o si usa solo un subset delle funzionalità disponibili dello strumento (i livelli di carico sono impostati nella scheda Scenari generali).
    
2. Nel campo **Prefisso per nomi utente** immettere un prefisso per il campo nome utente di tutti gli utenti. Per accedere all'URI (Uniform Resource Identifier) sarà: *UserPrefix[User Start Index... (Numero di utenti-1)] @User Dominio*  , ad esempio, myUser009@Contoso.com.
    
3. Nel campo **Password per tutti gli utenti** immettere la password usata durante la creazione degli utenti. Se si lascia vuoto questo campo, il nome utente verrà impostato come password.
    
4. Nel campo **Indice iniziale utente** immettere l'indice del primo utente da configurare. È possibile configurare intervalli diversi per tipi o livelli di carico diversi, ma è necessario eseguire lo strumento Configurazione carico (UserProfileGenerator.exe) una volta per ogni intervallo che si vuole configurare.
    
5. Nel campo **Numero di utenti** immettere il numero totale di utenti che si intende configurare.
    
6. Nel campo **Dominio utente** immettere il dominio usato per l'URI SIP. Viene usato per costruire l'URI SIP di ogni utente per accedere al server front-end di Skype for Business Server 2015 o edizione Standard e può essere diverso dal dominio dell'account.
    
7. Nel campo **Dominio account** immettere l'accesso al dominio di Active Directory Domain Services.
    
8. Nel campo **Percentuale MPOP** (percentuale di presenza multipla) assegnare un valore per la percentuale di utenti connessi da più computer o dispositivi, ad esempio il 10%.
    
9. Immettere il numero massimo di endpoint simultanei nel campo **Accedi al secondo (per istanza).** Si tratta del numero massimo di log in per gli utenti e la raccomandazione è una velocità inferiore/uguale a 2 al secondo (<=2).
    
10. Nel campo **Proxy di accesso o FQDN pool** immettere il nome di dominio completo (FQDN) del server a cui si desidera che i client si connettono. Se gli utenti eseguono l'accesso esternamente, è necessario digitare il proxy di accesso. Se gli utenti sono interni, assegnare il nome di dominio completo del pool di Enterprise o del server edizione Standard.
    
11. Nel campo **Porta** immettere la porta che gli utenti devono usare per SIP (il valore predefinito è 5061).
    
12. Per il campo **Impostazioni Server di rete esterno**, assegnare il nome di dominio completo del proxy di accesso o del pool e, di nuovo, la **porta**. Queste impostazioni vengono usate solo per la simulazione del carico degli endpoint esterni.
    
#### <a name="general-scenarios-tab"></a>Scheda Scenari generali

![Strumento di configurazione del carico che mostra la scheda Scenari generali.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
È possibile configurare i livelli di carico e i parametri per ognuno degli scenari generali offerti determinando ciò che si vuole eseguire o lasciare disabilitato. Ecco le opzioni generali:
  
> [!NOTE]
> I valori del livello di carico per tutti i campi, ma Local Information Services sono **disabilitati**, **bassi**, **medi**, **alti** o **personalizzati**. Se si seleziona un'impostazione ma disabilitata, vengono generate configurazioni per ogni client. Risultati elevati nel carico massimo supportato nel server; media è il 60% del carico elevato; bassa è del 30%. 
  
- **Messaggistica istantanea -** Ciò include peer-to-peer e conferenze; scegliere il valore appropriato per Livello di carico.
    
- **Audioconferenza:** scegliere un livello di carico *solo* per le audioconferenze. Le chiamate peer-to-peer verranno affrontate un po' più avanti nella sezione **Scenari vocali** . Aprire la scheda **Avanzate** per abilitare MultiView.
    
- **Condivisione di applicazioni -** Scegliere un livello di carico per la condivisione delle applicazioni.
    
- **Collaborazione dati -** Scegliere un livello di carico per la collaborazione dati, che include le conferenze dati.
    
- **Espansione della lista di distribuzione -** Fare clic sul pulsante **Avanzate** e compilare il campo con gli stessi valori configurati nella scheda DL dello strumento di creazione utente (UserProvisioningTool.exe). Scegliere un livello di carico.
    
- **Query Web rubrica -** Si tratta del servizio di ricerca della rubrica anziché del download del file della rubrica. Se si vuole abilitare questa opzione per il download di file della rubrica, fare clic sul pulsante **Avanzate** e impostare **EnableABSDownload** su True. Assegnare un valore per il livello di carico.
    
- **Response Group Service:** fare clic sul pulsante **Avanzate** e specificare gli URI dei response group già creati durante il provisioning degli agenti Response Group Service. È necessario scegliere almeno un response group. Per usare di più, separare i response group con punti e virgola. Aggiornare **RGSUriSuffixStartIndex** e **RGSUriSuffixEndIndex** ai valori effettivi. Scegliere un livello di carico.
    
- **Location Information Services -** Selezionare un livello di carico abilitato o Disabilitato.
    
> [!NOTE]
> Ognuno degli scenari ha accanto un pulsante Avanzate e un set di caselle di controllo che abilitano le varianti all'impostazione predefinita. 
  
- La scelta  *di Ad-hoc*  consentirà allo strumento di generare la simulazione di conferenze che verranno create durante l'ora.
    
- La scelta di  *Large Conf*  significa che verrà simulato uno scenario di conferenza di grandi dimensioni.
    
-  *Esterno*  indica allo strumento di simulare anche utenti esterni.
    
Questi pulsanti e caselle di controllo sono valori aggiuntivi specifici di ogni scenario e cambieranno il comportamento dello strumento stress e prestazioni e renderanno possibile la personalizzazione.
  
Per ogni scenario nella scheda Scenari generali (ad eccezione di Location Information Services), se il valore di Livello di carico è **Personalizzato**, la frequenza di conversazione verrà calcolata usando il campo corrispondente nella finestra di dialogo Avanzate. Il nome del campo può variare a seconda dello scenario, ma la descrizione del campo indica:  *NOTA Questo numero verrà usato solo se Custom è selezionato dal menu a discesa*  .
  
I valori **High**, **Medium** e **Low** altereranno le frequenze di conversazione per modalità in linea con il modello utente che rappresenta un equilibrio di tutti gli scenari. Se è necessario modificare il livello di carico per modalità a causa di una differenza nell'utilizzo previsto, usare una frequenza di conversazione personalizzata.
  
#### <a name="voice-scenarios-tab"></a>Scheda Scenari vocali

Questa è la scheda per la configurazione di tutti gli scenari correlati alla voce.
  
![Scheda Scenari vocali dello strumento di configurazione di caricamento.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Le opzioni disponibili sono:
  
- **VoIP -** Fare clic sul pulsante **Avanzate** e aggiungere valori per i campi PhoneAreaCode e LocationProfile (dial plan). Si fornirà anche un valore per Livello di carico. Se si sceglie un livello di carico per VoIP o gateway UC/PSTN abilitato, verrà generato un file di configurazione pstn (Public Switched Telephone Network) a unified communications (UC) per simulare chiamate esterne.
    
- **Gateway UC/PSTN -** È necessario scegliere un valore livello di carico e quando si sceglie un valore diverso da Disabilitato, è anche necessario specificare un valore per il prefisso PSTN facendo clic sul pulsante **Avanzate** . Fare clic su **Aggiungi** in Mediation Server e PSTN. Assicurarsi di avere una route configurata per il prefisso.
    
    > [!TIP]
    > È possibile usare Skype for Business Pannello di controllo o Skype for Business Management Shell per verificare la configurazione della route vocale. 
  
- **Operatore conferenza:** specificare un valore per Livello di carico. Qualsiasi valore diverso da Disabilitato abiliterà il campo **Numero di telefono** . Immettere il numero di telefono dell'operatore automatico da usare. Fare clic su **Avanzate** e specificare un valore per il campo **LocationProfile** .
    
- **Servizio parcheggio di chiamata -** In questo caso, specificare un livello di carico.
    
- **Mediation Server e PSTN -** Ogni Mediation Server che si vuole usare richiede un proprio simulatore PSTN. Dopo aver determinato il client che si intende usare per il simulatore, configurare il Mediation Server per instradare le chiamate al computer nel simulatore PSTN configurato. Fare clic sul pulsante **Aggiungi** per configurare un valore per Mediation Server.
    
    > [!NOTE]
    > Accanto a ogni scenario è presente un pulsante Avanzate. Le finestre di dialogo avanzate contengono impostazioni specifiche per ogni scenario che modificano il comportamento dello strumento stress e prestazioni e abilitano la personalizzazione. > Per ogni scenario nella scheda Scenari vocali, se il valore di Livello di carico è **Personalizzato**, la frequenza di conversazione verrà calcolata usando il campo corrispondente nella finestra di dialogo Avanzate. Il nome del campo può variare a seconda dello scenario, ma la descrizione del campo indica:  *NOTA Questo numero verrà usato solo se Custom è selezionato dal menu a discesa*  .
  
#### <a name="web-app-tab"></a>Scheda App Web

![Strumento di configurazione del caricamento, scheda App Web.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
App Web supporta scenari di conferenza tramite il server UCWA (Unified Communications Web API) installato in un server Front End. Usare la scheda App Web per configurare tutti gli scenari correlati alle app Web. Le opzioni sono:
  
- **App Web generale Impostazioni:** fare clic sul pulsante **Impostazioni aggiuntivo** e impostare **ReachTargetServerUrl** sull'INDIRIZZO IP virtuale del pool di directory dell'indirizzo VIP del pool Front End.
    
- **Condivisione di applicazioni -** Selezionare un valore per Livello di carico.
    
- **Collaborazione dati -** Selezionare un valore per Livello di carico.
    
- **Messaggistica istantanea -** Selezionare un valore per Livello di carico.
    
- **Servizi di conferenza vocale -** Selezionare un valore per Livello di carico.
    
> [!NOTE]
> Accanto a ognuno degli scenari è presente un pulsante **Avanzate** . Le finestre di dialogo avanzate contengono valori specifici di ogni scenario che modificano il comportamento dello strumento stress e prestazioni e abilitano la personalizzazione.> Per ognuno degli scenari dell'app Web, se il livello di carico è **personalizzato**, viene usato il valore specificato nel campo **ConversationsPerHour** anziché quello predefinito.
  
#### <a name="mobility-tab"></a>Scheda Mobilità

Usare questa scheda per configurare tutti gli scenari correlati alla mobilità.
  
![Scheda Mobility dello strumento di configurazione del carico.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Di seguito sono riportate le opzioni seguenti:
  
- **Impostazioni di mobilità generale:** fare clic su **Impostazioni aggiuntive** e impostare il campo UcwaTargetServerUrl sull'INDIRIZZO IP virtuale del pool di director o sull'indirizzo VIP del pool Front End.
    
- **Presenza e messaggistica istantanea P2P/audio -** Selezionare un valore per Livello di carico per abilitare la simulazione mobility.
    
> [!NOTE]
> Accanto a ognuno degli scenari è presente un pulsante **Avanzate** . Le finestre di dialogo avanzate contengono valori specifici di ogni scenario che modificano il comportamento dello strumento stress e prestazioni e abilitano la personalizzazione.> Per ognuno degli scenari di mobilità, se il livello di carico è **Personalizzato**, viene usato il valore specificato nel campo **ConversationsPerHour** anziché quello predefinito.
  
#### <a name="summary-tab"></a>Scheda Riepilogo

La scheda Riepilogo indica gli utenti da usare per ognuno degli scenari.
  
![Scheda Riepilogo dello strumento di configurazione di caricamento.](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
La scheda Riepilogo indica gli utenti da usare per ognuno degli scenari. 
  
È possibile configurare manualmente gli intervalli di numeri utente selezionando la casella di controllo **Abilita generazione di intervalli utente personalizzati** e quindi facendo doppio clic sullo scenario nella tabella con l'intervallo utente che si vuole personalizzare.
  
Controllare **(RunClient.bat) Aggiungere un ritardo di accesso all'avvio** per includere ritardi nei file batch generati in modo che corrispondano alla frequenza di accesso. Ciò è utile per evitare l'overload del server quando si accede a un numero elevato di utenti.
  
Fare clic su **Genera file** e selezionare la cartella in cui si vuole generare la configurazione. Una finestra di dialogo verrà visualizzata quando i file sono stati creati correttamente.
  
![Finestra di messaggio "Caricamento dei file di configurazione generati correttamente". Basta fare clic su OK.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Eseguire LyncPerfTool
<a name="BKMK_RunTool"> </a>

È necessario creare utenti, contatti e scenari prima di eseguire lo strumento di stress e prestazioni Skype for Business Server 2015 (LyncPerfTool.exe). Per informazioni dettagliate sull'uso degli strumenti per eseguire queste azioni, vedere [Creare utenti e contatti e](using-the-tool.md#BKMK_CreateUsersAndContacts) [configurare il profilo utente](using-the-tool.md#BKMK_UserProfile) in precedenza in questo articolo. L'esecuzione di questi strumenti genererà anche un file che verrà eseguito con lo strumento Stress and Performance come parte di un file batch con i parametri necessari inclusi.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Esecuzione dello strumento di stress e prestazioni Skype for Business Server 2015

Lo strumento Configurazione carico (UserProfileGenerator.exe) crea un file batch che consente di eseguire lo strumento Stress and Performance (LyncPerfTool.exe) registrando i contatori delle prestazioni e caricando il file di configurazione XML. Il file batch esegue un'istanza di LyncPerfTool.exe per ogni file di configurazione. Per eseguire il file batch, seguire questa procedura:
  
### <a name="run-the-stress-and-performance-test"></a>Eseguire il test di stress e prestazioni

1. Copiare la cartella con le cartelle di configurazione e i file all'interno nella directory con LyncPerfTool.exe in ogni computer client. Ad esempio, se sono stati generati i file di configurazione nella cartella denominata 1.28_13.16.16, copiare la cartella nella cartella con LyncPerfTool.exe. Eseguire questa operazione in ogni client.
    
2. Passare alla cartella client ed eseguire lo script batch **RunClient** . È possibile fare doppio clic sul file batch in Windows Explorer e verranno eseguiti tutti i file di configurazione per il client. È anche possibile eseguire lo script da una cartella client usando la sintassi seguente:
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Per eseguire direttamente lo strumento Stress and Performance, aprire un prompt dei comandi e digitare il comando seguente nella riga di comando (e quando si esegue questa operazione per la prima volta, assicurarsi di registrare i contatori  `regsvr32 /i /n /s LyncPerfToolPerf.dll`delle prestazioni , come illustrato nella nota più avanti in questo argomento):
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

Per fare in modo che lo strumento visualizzi i valori nel file di configurazione, includere il  `/displayfile` parametro nel comando precedente, in modo che sia simile al seguente:
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Per  *terminare*  il processo, premere CTRL+C.
  
> [!NOTE]
> Prima di eseguire direttamente lo strumento Stress and Performance, è necessario registrare i contatori delle prestazioni tramite il comando seguente:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Ogni istanza dello strumento Stress and Performance avviato inizierà immediatamente ad accedere agli utenti, in genere con una frequenza di un utente al secondo. 
  
La frequenza di accesso utente massima per il pool è di circa 12 al secondo. Ciò significa che non è consigliabile avviare più di 12 istanze di LyncPerfTool.exe contemporaneamente mentre gli utenti stanno ancora effettuando l'accesso. Un migliaio di utenti richiederà circa 20 minuti per accedere completamente a uno al secondo.
  
## <a name="interpreting-the-results"></a>Interpretazione dei risultati
<a name="BKMK_Interpret"> </a>

Lo strumento di stress e prestazioni di Skype for Business Server 2015 include molti contatori che consentono di comprendere cosa sta facendo il client e se si verificano problemi.
  
### <a name="client-counters"></a>Contatori client

Ogni istanza di LyncPerfTool.exe in esecuzione ha un'istanza separata dei contatori. Ogni istanza è denominata dal relativo ID processo. Se i client sono sovraccarichi, possono verificarsi altri problemi. Per evitare questi problemi:
  
- Monitorare l'utilizzo della CPU e della memoria nei computer client. Se la CPU è costantemente superiore al 90%, ridurre il numero di utenti.
    
- Quando il footprint di memoria è elevato, è possibile che si verifichino problemi se lo spazio del file di pagina inizia a esaurirsi. Verificare che l'addebito del commit non raggiunga il limite nel computer. Se si verificano limiti di memoria, è consigliabile aumentare le dimensioni del file di pagina o ridurre il numero di utenti.
    
Ecco un elenco di contatori delle prestazioni chiave:
  
**Generalità**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Tempo impiegato in minuti  <br/> |Tempo trascorso dall'avvio del processo.  <br/> |
|Endpoint attivi  <br/> |Numero di endpoint attualmente connessi al server.  <br/> |
|Accessi non riusciti  <br/> |Numero totale di errori di accesso dell'endpoint.  <br/> |
|Tentativi di accesso  <br/> |Numero totale di tentativi di accesso all'endpoint.  <br/> |
|Endpoint disconnessi  <br/> |Numero totale di endpoint disconnessi.  <br/> |
   
**Informazioni sulla presenza**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate SetPresence  <br/> |Numero totale di tentativi di modifica della presenza. Per diversi tipi di modifiche alla presenza, vedere il contatore delle prestazioni chiamate SetPresence (tipo di presenza).  <br/> |
|Risposte NNN per SetPresence  <br/> |Numero totale di codici di risposta nnn ricevuti dal server.  <br/> |
|Chiamate GetPresence  <br/> |Numero totale di tentativi di richiesta di presenza get.  <br/> |
|Risposte NNN per GetPresence  <br/> |Numero totale di codici di risposta nnn ricevuti dal server.  <br/> |
   
**Informazioni sul servizio Rubrica**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Tentativo di download di file abs completi/differenziati  <br/> |Numero totale di richieste di download di file completi o differenziati tentati.  <br/> |
|Download di file ABS completi/differenziati completata  <br/> |Numero totale di richieste di download di file completi o differenziati tentati.  <br/> |
|Contatori correlati al servizio Query Web rubrica  <br/> |Contatori correlati per il download di file della rubrica.  <br/> |
|Tentativo di chiamate WS ABS  <br/> |Numero totale di richieste di servizio Query Web rubrica tentate.  <br/> |
|Chiamate WS ABS completate  <br/> |Numero totale di richieste di servizio Query Web rubrica che hanno restituito un codice di risposta riuscito.  <br/> |
|Chiamate WS ABS non riuscite  <br/> |Numero totale di richieste di servizio Query Web rubrica che hanno restituito un codice di risposta agli errori.  <br/> |
   
> [!NOTE]
> Questa categoria include contatori usati per monitorare i download di file del servizio Rubrica (ABS) e le richieste del servizio Query Web rubrica. 
  
**Informazioni sulla lista di distribuzione (DL)**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate tentate  <br/> |Numero totale di richieste di servizio Web DLX (Distribution List Expansion).  <br/> |
|Chiamate riuscite  <br/> |Numero totale di richieste di servizi Web DLX che hanno restituito un codice di risposta riuscito.  <br/> |
|Chiamate non riuscite  <br/> |Numero totale di richieste di servizi Web DLX che hanno restituito un codice di risposta agli errori.  <br/> |
   

  
> [!NOTE]
> I contatori delle prestazioni elencati di seguito segnalano i numeri per tutte le chiamate VoIP (Voice over IP), incluse le chiamate a Mediation Server, A/V Conferencing Server, Edge Server, applicazione Response Group e Operatore automatico conferenza, quando questi scenari sono abilitati. 
  
**Informazioni di base su VoIP**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate attive  <br/> |Numero totale di chiamate vocali in ingresso/in uscita attualmente in corso.  <br/> |
|Chiamate terminate  <br/> |Numero totale di chiamate vocali in ingresso/in uscita già terminate.  <br/> |
|Chiamate rifiutate  <br/> |Numero totale di chiamate vocali in ingresso rifiutate.  <br/> |
|Tentativo di chiamate in ingresso/in uscita  <br/> |Numero totale di chiamate vocali in ingresso/in uscita tentate.  <br/> |
|Chiamate in ingresso/in uscita stabilite  <br/> |Numero totale di chiamate vocali in ingresso/in uscita stabilite.  <br/> |
|Chiamate NNN ricevute  <br/> |Numero totale di codici di risposta nnn ricevuti dal server.  <br/> |
|VoIP Pass Rate (%)  <br/> |Totale chiamate stabilite/Totale chiamate tentate.  <br/> |
   
**Informazioni sulle chiamate al servizio Response Group**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate attive  <br/> |Numero totale di chiamate attive all'applicazione Response Group.  <br/> |
|Chiamate tentate  <br/> |Numero totale di chiamate tentate.  <br/> |
   
**Informazioni sulla chiamata di messaggistica istantanea**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate attive  <br/> |Numero totale di chiamate di messaggistica istantanea in ingresso/in uscita in corso.  <br/> |
|Chiamate terminate  <br/> |Numero totale di chiamate di messaggistica istantanea in ingresso/in uscita già terminate.  <br/> |
|Chiamate NNN ricevute  <br/> |Numero totale di codici di risposta nnn ricevuti dal server.  <br/> |
|Messaggi di messaggistica istantanea ricevuti/inviati  <br/> |Numero totale di messaggi ricevuti o inviati per tutte le sessioni.  <br/> |
|Tentativo di chiamate in ingresso/in uscita  <br/> |Numero totale di chiamate di messaggistica istantanea in ingresso/in uscita tentate.  <br/> |
|Chiamate in ingresso/in uscita stabilite  <br/> |Numero totale di chiamate istantanee in ingresso/in uscita stabilite.  <br/> |
   
**Informazioni sulla chiamata di condivisione delle app**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate attive  <br/> |Numero totale di chiamate di condivisione di applicazioni in ingresso/in uscita in corso.  <br/> |
|Chiamate terminate  <br/> |Numero totale di chiamate di condivisione di applicazioni in ingresso/in uscita già terminate.  <br/> |
|Chiamate NNN ricevute  <br/> |Numero totale di codici di risposta nnn ricevuti dal server.  <br/> |
|Tentativo di chiamate in ingresso/in uscita  <br/> |Numero totale di chiamate di condivisione di applicazioni in ingresso/in uscita tentate.  <br/> |
|Chiamate in ingresso/in uscita stabilite  <br/> |Numero totale di chiamate di condivisione di applicazioni in ingresso/in uscita stabilite.  <br/> |
   
**Informazioni sulla chiamata CAA**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Chiamate attive  <br/> |Numero totale di chiamate PSTN (Public Switched Telephone Network) in ingresso/in uscita attualmente in corso.  <br/> |
|Chiamate terminate  <br/> |Numero totale di chiamate PSTN in ingresso/in uscita già terminate.  <br/> |
|Tentativo di chiamate in ingresso/in uscita  <br/> |Numero totale di chiamate PSTN in ingresso/in uscita tentate.  <br/> |
|Chiamate in ingresso/in uscita stabilite  <br/> |Numero totale di chiamate PSTN in ingresso/in uscita stabilite.  <br/> |
   
**Informazioni sulla conferenza**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Conferenze di messaggistica istantanea attiva  <br/> |Numero totale di conferenze di messaggistica istantanea in corso.  <br/> |
|Conferenze audio/video attive  <br/> |Numero totale di conferenze audio/video (A/V) in corso.  <br/> |
|Conferenze di condivisione di applicazioni attive  <br/> |Numero totale di conferenze di condivisione delle applicazioni in corso.  <br/> |
|Numero di partecipanti  <br/> |Numero totale di partecipanti attualmente connessi alle conferenze.  <br/> |
|Errore di pianificazione della conferenza  <br/> |Numero totale di errori durante il tentativo di pianificare una conferenza.  <br/> |
|Errore di partecipazione alla conferenza  <br/> |Numero totale di errori durante il tentativo di connessione a una conferenza.  <br/> |
   
**Contatori client UCWA**

|**Contatore delle prestazioni**|**Descrizione**|
|:-----|:-----|
|Numero totale di join IMMCU completati  <br/> |Numero totale di conferenze di messaggistica istantanea aggiunte.  <br/> |
|Numero totale di join DMCU completati  <br/> |Numero totale di conferenze A/V aggiunte.  <br/> |
   

