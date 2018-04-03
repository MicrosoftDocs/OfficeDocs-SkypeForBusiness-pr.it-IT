---
title: Impostazione di sistema telefonico all'interno dell'organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 02/28/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: "Informazioni su come configurare il sistema telefonico (Cloud PBX) per l'organizzazione. "
ms.openlocfilehash: a9715797284f08c3d7f2ecbf3ba45a9269a5e0e0
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2018
---
# <a name="setting-up-phone-system-in-your-organization"></a>Impostazione di sistema telefonico all'interno dell'organizzazione

Di seguito è una Guida passo passo per la configurazione di sistema telefonico in Office 365. Collegamenti a ulteriori informazioni dettagliate sono disponibili alla fine di ogni passaggio.  

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Passaggio 1: Verificare che sistema telefonico è disponibile nel tuo paese

1.  Innanzitutto passare alla [disponibilità paese e alle aree per le conferenze Audio e la chiamata a piani](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)e selezionare il proprio paese dall'elenco nella parte superiore della pagina. 
2.  In **Sistema telefonico**, esaminare l'elenco delle caratteristiche e i dettagli. 
3.  Se il sistema telefonico è disponibile, andare al passaggio 2. 

**Per ulteriori informazioni sulla disponibilità internazionali del sistema telefonico e audioconferenza, vedere [disponibilità paese e alle aree per le conferenze Audio e la chiamata dei piani](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Passaggio 2: Acquistare e assegnare licenze sistema telefonico e pianificare la chiamata

Per assegnare una licenza sistema telefonico e pianificare la chiamata a un singolo utente i passaggi sono gli stessi come assegnare una licenza Office 365. Vedi [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Se si desidera assegnare più utenti in blocco, vedere (.. / skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Passaggio 3: Ottenere i numeri di telefono per gli utenti

[] Prima di poter impostare gli utenti nella tua organizzazione per fare e ricevere telefonate, devi recuperare i numeri di telefono. 

Sono disponibili tre modi di ottenere numeri per gli utenti: 
- È possibile ottenere nuovi numeri utilizzando il Skype per interfaccia di amministrazione di Business.
- È possibile ottenere nuovi numeri che non sono disponibili in Skype per interfaccia di amministrazione di Business.
- Trasferire i numeri di telefono esistenti dal provider di servizi o gestore di telefonia attuale a Office 365.

Devi consultare la pagina **Aggiungi nuovi numeri utente** per visualizzare, eseguire ricerche, acquisire e prenotare quei numeri. Ricerca in base al paese/area geografica, lo stato e città e quindi immettere il numero dei numeri di telefono, che è necessario per gli utenti. 

### <a name="get-new-user-phone-numbers"></a>Ottenere numeri di telefono nuovo utente 
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nel riquadro sinistro passare a **Voice** > **i numeri di telefono**, fare clic su **Aggiungi nuovo numero** ![pulsante Aggiungi](../images/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png), quindi fare clic su **nuovo utente numeri**.
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Ottenere nuovi numeri che non sono disponibili in Skype per interfaccia di amministrazione di Business
  
In alcuni casi (a seconda del paese/area geografica) non sarà in grado di ottenere i nuovi numeri utilizzando il Skype per interfaccia di amministrazione di Business. In questo caso, è necessario scaricare un modulo e inviare nuovamente per noi. Visualizzare i [numeri di telefono di gestione dell'organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per imparare a richiedere nuovi numeri utente.   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Porta o trasferimento numeri di telefono dal provider di servizi o gestore telefonico
  
- Se ti occorrono fino a 999 numeri di telefono per i tuoi utenti, puoi ricorrere alla procedura guidata **Nuovo ordine di portabilità di un numero locale** nell'interfaccia di amministrazione di Skype for Business. Seguire le istruzioni disponibili in [numeri di telefono di trasferimento a Office 365](..//what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) per trasferire i numeri di telefono su Skype Business online.
    
- Se si desidera più di 999 numeri di telefono delle porte, vedere [Manage i numeri di telefono per l'organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per inviare una richiesta di assistenza ordine porta o per poter ottenere tutti i numeri di telefono migrare a Office 365. 

**Per informazioni dettagliate sull'acquisizione nuovi numeri di telefono o il trasferimento di numeri esistenti, vedere [Manage i numeri di telefono per l'organizzazione](../what-are-calling-plans-in-office-365\manage-phone-numbers-for-your-organization\manage-phone-numbers-for-your-organization.md).**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Passaggio 4: Ottenere i numeri di telefono del servizio (audioconferenza, le code di chiamata, gli operatori automatici)

Oltre a ottenere numeri di telefono per gli utenti da Office 365, è possibile cercare e acquisire tariffe o numeri verdi per i servizi, ad esempio audioconferenze con accesso esterno (per i ponti di conferenza), gli operatori automatici e le code di chiamata (denominate anche numeri service). I numeri di servizio hanno una capacità di chiamate contemporanee superiore ai numeri di telefono per utenti o abbonati. Ad esempio, un numero di servizio può gestire 100s delle chiamate contemporaneamente, mentre il numero di telefono dell'utente può gestire solo alcune chiamate contemporaneamente.

### <a name="get-new-service-numbers"></a>Ottenere i numeri di servizio

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nel riquadro sinistro passare a **Voice** > **i numeri di telefono** > **Aggiungi nuovo numero**, quindi fare clic su **nuovi numeri di servizio**.
    
    > [!IMPORTANT] 
    > Per poter visualizzare l'opzione **vocale** nel riquadro di spostamento sinistra in Skype per interfaccia di amministrazione di Business, è necessario acquistare una licenza di componente aggiuntivo **Per conferenze Audio** , una licenza di componente aggiuntivo di **Sistema telefonico** o almeno una **licenza Enterprise E5**.
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Ottenere nuovi numeri che non sono disponibili in Skype per interfaccia di amministrazione di Business
  
In alcuni casi (a seconda del paese/area geografica) non sarà in grado di ottenere i nuovi numeri utilizzando il Skype per interfaccia di amministrazione di Business. In questo caso, è necessario scaricare un modulo e inviare nuovamente per noi. Visualizzare i [numeri di telefono di gestione dell'organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per imparare a richiedere nuovi numeri. 

### <a name="port-or-transfer-existing-service-numbers"></a>Portabilità o trasferimento dei numeri di servizio

Se voi trasferire numeri di servizio esistenti dall'operatore o provider di servizio attuale, devi presentare manualmente un ordine di portabilità a Microsoft. È necessario inviare gli ordini porta separata per ogni tipo di numero del servizio (numero a tariffa rispetto al numero verde) che si verrà trasferire con una lettera di autorizzazione (LOA). Nella lettera di autorizzazione (LOA), è necessario selezionare il tipo di numero di servizio corretto. Quando si contatta il supporto Microsoft, assicurarsi che si specifica che si desidera trasferire un numero di servizio (*e non un numero di utente o di sottoscrizione*) o la capacità di chiamata simultanea potrebbe non essere sufficiente per gestire volumi di chiamate. Se si desidera trasferire i numeri di telefono o eseguire altre operazioni con i numeri di telefono, vedere [Manage i numeri di telefono per l'organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Passaggio 5: Se si desidera impostare le tariffe di chiamate

Se si sono state seguendo i passaggi precedenti, si è già stato acquistato e assegnati sistema telefonico e le licenze e un piano di chiamata (passaggio 2) e acquisito numeri numeri di telefono per gli utenti (passaggio 3), pertanto il piano di chiamata è parzialmente configurato. Seguire le tre procedure seguenti per completare l'installazione del piano di chiamata.

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>Aggiungere gli indirizzi di emergenza e percorsi per l'organizzazione

1. Nella pagina **Voce**, seleziona **Posizione per gli interventi di emergenza** > **Aggiungi**.
    
2. Nel riquadro **Nuovo indirizzo**, immetti un nome per l'indirizzo e poi compila le caselle restanti.
    
     ![When you enter a new emergency address, the formatting of the street name might cause an error.](../images/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > Per i clienti di lingua inglese, se il nome della strada è un numero, assicurarsi di includere la desinenza (come "st" o "th") come indicato nella figura sopra. 
  
3. Seleziona **Convalida**.
    
    Se necessario, ti sarà chiesto di fare correzioni all'indirizzo. 
    
    > [!CAUTION]
    > La convalida di un indirizzo civico o stradale implica la verifica della legittimità e della corretta formattazione dell'indirizzo. È possibile che un indirizzo per gli interventi di emergenza parzialmente corretto, in cui hai ad esempio digitato erroneamente il nome della città, superi comunque la fase di convalida. In caso di convalida nonostante gli errori di ortografia, la combinazione del nome della città errato e delle altre parti corrette dell'indirizzo fornisce informazioni sufficienti per instradare la chiamata al centro di emergenza appropriato. 
  
    > [!TIP]
    > Se l'indirizzo deve essere corretto per un intervento di emergenza, verrà visualizzato un banner verde per indicare che l'indirizzo è stato aggiornato. 
  
4. Dopo la convalida dell'indirizzo, seleziona **Salva**.
    
### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>Assegnare agli utenti i numeri di telefono e gli indirizzi di emergenza

> [!TIP]
> Se aggiungi altre persone alla tua azienda appena prima di questo passaggio, possono passare **diverse ore** prima che compaiano nella pagina **Utenti vocali**. C'è un periodo di latenza.
  
1. Nella pagina **Utenti vocali**, scegli le persone a cui vuoi assegnare un numero di telefono e un indirizzo per gli interventi di emergenza.
    
2. Seleziona **Assegna numero**.
    
3. Nella pagina **Assegna numero**, nel menu a discesa **Seleziona il numero da assegnare** scegli il numero di telefono per l'utente.
    
4. Per selezionare un indirizzo per gli interventi di emergenza, inserisci il nome della città nella casella **Trova città** e seleziona Cerca.
    
    > [!IMPORTANT]
    > Se non ti trovi negli Stati Uniti, i tuoi numeri hanno già un indirizzo per gli interventi di emergenza, ma puoi modificarlo in questa fase. Consulta [Assegnare o modificare l'indirizzo per gli interventi di emergenza di un utente](../what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user.md). 
  
5. Dopo avere assegnato sia il numero di telefono sia l'indirizzo per gli interventi di emergenza, seleziona **Salva**.
    
### <a name="tell-your-users-about-their-new-phone-numbers"></a>Informare gli utenti ai nuovi numeri di telefono


Consigliamo di inviare e-mail o usare il metodo di comunicazione standard dell'azienda per comunicare alle persone il nuovo numero di telefono. 

Ecco come è possibile visualizzare tale numero di telefono nel proprio app **Skype for Business** :
  
1. Esegui l'accesso a Skype for Business sul desktop.
    
2. Seleziona **Impostazioni** > **Strumenti** > **Opzioni**. 
    
     ![To view your phone number, go to Settings > Tools > Options.](../images/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. Poi seleziona **Telefoni**. 
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](../images/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
In **Team Microsoft che**gli utenti possono visualizzare il numero di telefono fare clic sulle **chiamate** nel riquadro di spostamento sinistro. Il numero di telefono viene visualizzato sopra la tastiera.

![Un utente può visualizzare il numero di Microsoft Teams facendo clic sulle chiamate nel riquadro di spostamento sinistro.](../images/teams-phone-number.png)

**Per informazioni più dettagliate su tutti i passaggi necessari per la configurazione di un piano di chiamata, vedere [impostare le tariffe di chiamate](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Passaggio 6: Se si desidera configurare conferenze Audio

A volte le persone all’interno dell'organizzazione devono utilizzare un telefono per accedere a una riunione. Skype per le aziende e Teams Microsoft includono la funzionalità di audioconferenza per solo questa situazione! Le persone possono chiamare Skype per le riunioni aziendali o Microsoft Teams mediante un telefono, anziché utilizzare il Skype per applicazioni aziendali o Microsoft Teams su un dispositivo mobile o PC. 
  
È sufficiente configurare conferenze Audio per gli utenti che prevedono di programmare o condurre riunioni. I partecipanti alla riunione che effettua la chiamata non è necessario alcun licenze assegnate loro o altre impostazioni.
  
Per le domande frequenti sui servizi di conferenza Audio, vedere [domande frequenti di conferenze Audio](../audio-conferencing-in-office-365/audio-conferencing-common-questions.md).
    
1. Se è stato acquistato Communications crediti licenze e le licenze di componente aggiuntivo **Per conferenze Audio** , assegnarli troppo. Per ulteriori informazioni, vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

    Scegliere il provider di servizi di conferenza audio. Un provider di servizi di conferenza audio fornisce un ponte per conferenze audio. Bridge conferenza imposta i numeri di telefono di accesso esterno, pin e gli ID conferenza per le riunioni. Decidere se utilizzare Microsoft o un provider di servizi di conferenza audio di terze parti: 

    > [!NOTE]
    > Gli utenti di Microsoft Teams non utente un provider di servizi di conferenza audio di terze parti. 
  
    - **Microsoft come provider di servizi di conferenza audio**: se si desidera che la soluzione più semplice per le conferenze audio, scegliere Microsoft come provider di servizi di conferenza audio.
    
    - **Terze parti come provider di servizi di conferenza audio**: se si partecipa a un paese dove audioconferenze con accesso esterno in Office 365 non è disponibile, la qualità del servizio non è grande a causa della posizione o si dispone di un contratto esistente, scegliere un audio di terze parti provider di servizi di conferenza. Per trovare un provider, andare a [Individuare Microsoft](http://go.microsoft.com/fwlink/?LinkId=797530).
 
2.  Assegnare il provider di servizi di conferenza audio agli utenti di condurre o pianificare riunioni. Vedere [Assegnare Microsoft come provider di servizi di conferenza audio](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).

3. Impostare le convocazioni di riunione. La procedura seguente è facoltativa, ma una quantità elevata di admins like eseguirle: 
  
    1. [Personalizza convocazioni di riunione](../set-up-skype-for-business-online/customize-meeting-invitations.md). I numeri di accesso impostate per l'utente verranno aggiunta automaticamente per gli inviti alle riunioni inviati ai partecipanti. Tuttavia, è possibile aggiungere Guida personalizzata e collegamenti legali, un messaggio di testo e immagine piccola società.
    
    2. [Set di numeri di telefono per conferenze Audio per inclusi in inviti agli organizzatori della riunione](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md). Questo è il numero di telefono che verrà visualizzata in alle riunioni pianificate dall'utente.
    
    3. [Impostare le lingue di operatore automatico per le conferenze Audio](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) che utilizza l'operatore automatico di audioconferenza per saluti salutare un chiamante quando si effettua la chiamata a un numero di telefono di audioconferenza. Questo passaggio si applica solo se si utilizza Microsoft come provider di audio.
    
    4. [Impostare la lunghezza del PIN per le riunioni di conferenze Audio](../audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings.md).
    
    > [!NOTE]
    > Questa funzionalità non è ancora disponibile per i clienti con Office 365 gestito dal 21Vianet in Cina. Per ulteriori informazioni, vedere [informazioni su Office 365 gestito dal 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE). 

**Per ulteriori informazioni sulle conferenze Audio, vedere [configurazione di conferenze Audio](../audio-conferencing-in-office-365/set-up-audio-conferencing.md).**

## <a name="step-7-if-you-want-to-set-up-a-phone-system-call-queue"></a>Passaggio 7: Se si desidera configurare una coda di chiamata di sistema telefonico

Chiamata al sistema telefonico code includono messaggi di saluto che vengono utilizzati quando si riceve una chiamata a un numero di telefono per l'organizzazione, la possibilità di inserire automaticamente le chiamate in attesa e le funzionalità di ricerca per il successivo agente disponibile chiamata gestire la chiamata mentre gli utenti che chiamata in attesa la musica di attesa. È possibile creare uno o più code di chiamata per l'organizzazione.

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. Dopo aver ottenuto il numero a tariffa o numeri verdi servizio, che verranno visualizzati nella **Skype per Business admin center** > **vocale** > **numeri di telefono**e **tipo di numero** elencato verrà indicato come **servizio - numero verde **. Per ottenere i numeri di servizio, vedere [Getting numeri di telefono del servizio per Skype per le aziende e team Microsoft che](getting-service-phone-numbers.md) oppure se si desidera trasferimento e il numero di servizio esistente, [trasferire i numeri di telefono a Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se si è fuori degli Stati Uniti, è possibile utilizzare Skype per interfaccia di amministrazione di Business per ottenere i numeri di servizio. Vai a [Gestisci i numeri di telefono per l'organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) ma per informazioni su come effettuare di fuori degli Stati Uniti.

Per creare una nuova coda di chiamata, **Skype per interfaccia di amministrazione di Business**, fare clic su **routing delle chiamate** > **code di chiamata**, fare clic su **Aggiungi nuovo**e quindi seguire le istruzioni nel **passaggio 3** di [creare una coda di chiamata di sistema telefonico]( create-a-phone-system-call-queue.md#step-3---create-a-new-call-queue).

**Per ulteriori informazioni sulle code di chiamata, vedere [creare una coda di chiamata di sistema telefonico](create-a-phone-system-call-queue.md).**

## <a name="step-8-if-you-want-to-set-up-a-phone-system-auto-attendant"></a>Passaggio 8: Se si desidera configurare un sistema telefonico l'operatore automatico

Gli operatori automatici di consentono agli utenti che chiamate verso l'organizzazione e passare a un sistema di menu per ottenere informazioni utili per il reparto destro, coda, persona o l'operatore di chiamata. È possibile creare un operatore automatico per l'organizzazione mediante il Skype per l'interfaccia di amministrazione di Business. 

Per creare un nuovo operatore automatico, Skype per interfaccia di amministrazione di Business, fare clic su **routing delle chiamate** > **gli operatori automatici**, fare clic su **Aggiungi nuovo**e quindi seguire le istruzioni per ogni pagina nel **passaggio 2** di [Set up automaticamente un sistema telefonico operatore](set-up-a-phone-system-auto-attendant.md#step-2---create-a-new-auto-attendant).

**Per ulteriori informazioni sugli operatori automatici di sistema telefonico, vedere [configurazione di un operatore automatico di sistema telefonico](set-up-a-phone-system-auto-attendant.md).**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Passaggio 9: Assegnare numeri di telefono del servizio (audioconferenza, le code di chiamata, gli operatori automatici)

Dopo avere creato i numeri di servizio dal **passaggio 4 sopra**, è necessario assegnarli a ogni tipo di servizio che si desidera. Ad esempio, se si desidera che un numero di telefono del servizio dedicato (tariffe o il numero verde), è necessario assegnare il numero di ponte per conferenze.

- Per le conferenze Audio, è possibile assegnare un numero dedicato a un ponte per conferenze accedendo **all'interfaccia di amministrazione di Office 365** > **Admin Center** > **Skype per le aziende** > **le conferenze Audio** e fare clic sul bridge conferenza o visualizzando [modificare il numero a tariffa o numeri verdi il bridge di conferenze Audio](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

- Per gli operatori automatici, è possibile assegnare un numero dedicato a un operatore automatico **all'interfaccia di amministrazione di Office 365** > **Admin Center** > **Skype per le aziende** > **routing delle chiamate** > gli operatori automatici** **e scegliere l'operatore automatico. Nella pagina **Generale** , il numero di servizio è già stato viene indicato il **numero di telefono** a discesa. Per ulteriori informazioni, vedere [configurazione di un operatore automatico di sistema telefonico](set-up-a-phone-system-auto-attendant.md).

- Per chiamare le code, è possibile assegnare un numero dedicato a una coda di chiamata **all'interfaccia di amministrazione di Office 365** > **Admin Center** > **Skype per le aziende** > **routing delle chiamate** > **code delle chiamate** e fare clic su la coda di chiamata. Nella pagina **Generale** , il numero di servizio è già stato viene indicato il **numero di telefono** a discesa. Per ulteriori informazioni, vedere [creare una coda di chiamata di sistema telefonico](create-a-phone-system-call-queue.md).

**Per informazioni dettagliate sui nuovi numeri del servizio di recupero e portabilità i numeri di servizio esistente, vedere [Getting numeri di telefono del servizio](getting-service-phone-numbers.md).**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Passaggio 10: Impostare i titoli di coda di comunicazione per l'organizzazione

[] Per usare i numeri verdi in Skype for Business e Microsoft Teams, sono necessari Crediti comunicazioni. Inoltre, è consigliabile impostare i Crediti comunicazioni per i Piani per chiamate (nazionali e internazionali) e Audioconferenza che hanno necessità di effettuare chiamate in uscita verso **qualsiasi destinazione**. Sono inclusi molti paesi/aree geografiche, ma alcune destinazioni PSTN possono non essere incluse in un dato abbonamento Piano per chiamate e Audioconferenza. Se non vengono impostati i Crediti comunicazioni o assegnata una licenza **Crediti comunicazioni** agli utenti e vengono esauriti i minuti per la propria organizzazione (a seconda del Piano per chiamate e Audioconferenza per lo specifico paese/area geografica), quegli utenti non potranno effettuare chiamate o chiamate in uscita dalle riunioni online in audioconferenza. È possibile ottenere ulteriori informazioni, tra cui consigliato fondi importi, leggendo [che cosa sono i titoli di coda Communications?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)
  
> [!NOTE]
> Per scoprire quanto costa, [consulta i prezzi qui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 

### <a name="to-set-up-communications-credits"></a>Per impostare i titoli di coda di comunicazioni 

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. In the left navigation of the Office 365 admin center, go to **Billing** > **Subscriptions** > **Add-ons** > **Buy add-ons**, and then choose **Communications Credits** > **Buy now**.
    
3. Nella pagina sottoscrizione **Crediti Communications** , immettere le informazioni e quindi fare clic su **Avanti**.
        
4. Immettere le informazioni di pagamento e scegliere **Esecuzione dell'ordine**.
    >[!IMPORTANT]
    >Se si è un cliente di licenze volume, è possibile scegliere il numero di contratto enterprise per il pagamento. Se si dispone di più numeri di enterprise agreement, sarà possibile selezionare il contratto enterprise agreement si desidera utilizzare per il pagamento. Sarà inoltre possibile consente di specificare un numero di ordine di acquisto per associare il numero di contratto enterprise (se applicabile).
    
**Per ulteriori informazioni sull'impostazione dei titoli di coda di comunicazioni, vedere [configurare comunicazioni titoli di coda per l'organizzazione](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).**
  
### <a name="assign-a-communications-credits-license-to-users"></a>Assegnare una licenza Communications crediti agli utenti

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Office 365 accedi a **Utenti** > **Utenti attivi** > e quindi seleziona uno o più utenti dall'elenco.
    
3. Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**.
    
4. On the **Product licenses** page, toggle ** Communications Credits** to **On** to assign this license, and then click **Save**.
    
    > [!NOTE]
    > Anche se ad alcuni utenti è assegnata una licenza **Enterprise E5**, è consigliabile comunque procedere in questo modo.

**Per ulteriori informazioni sull'assegnazione delle licenze crediti Communications, vedere [impostare i titoli di coda di comunicazione per l'organizzazione](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).**

## <a name="related-topics"></a>See also
[Ecco cosa offre il Sistema telefonico in Office 365](here-s-what-you-get-with-phone-system.md)

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 