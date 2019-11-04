---
title: Configurazione di Sistema telefonico nella tua organizzazione
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: "Informazioni su come configurare il sistema telefonico (cloud PBX) per l'organizzazione. "
ms.openlocfilehash: 402ae5f92e72cd1bc7ab759d3706108480a27a7e
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925297"
---
# <a name="setting-up-phone-system-in-your-organization"></a>Configurazione di Sistema telefonico nella tua organizzazione

The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Passaggio 1: Verificare che Sistema telefonico sia disponibile nel tuo paese

1.  Innanzitutto passare alla [Disponibilità paese e area geografica per le Audioconferenze e i Piani di chiamata](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)e selezionare il proprio paese dall'elenco nella parte superiore della pagina. 
2.  In **Sistema telefonico**, esaminare l'elenco delle caratteristiche e i dettagli. 
3.  Se il Sistema telefonico è disponibile, andare al passaggio 2. 

**Per ulteriori informazioni sulla disponibilità internazionale del Sistema telefonico e Audioconferenza, vedere [Disponibilità paese e aree geografiche per le Audioconferenze e i Piani di chiamata](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Passaggio 2: acquistare e assegnare licenze relative a Sistema telefonico e Piani di chiamata

Per assegnare un sistema telefonico e una licenza per un piano di chiamata a un singolo utente, la procedura è uguale all'assegnazione di una licenza di Office 365. Vedere [assegnare le licenze di Microsoft teams](assign-teams-licenses.md). Se si vuole assegnare più utenti in blocco, vedere [assegnare licenze di Microsoft teams](assign-teams-licenses.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Passaggio 3: ottenere i numeri di telefono per gli utenti

[] Prima di poter impostare gli utenti nella tua organizzazione per fare e ricevere telefonate, devi recuperare i numeri di telefono.

Sono disponibili tre modi per ottenere i numeri per gli utenti:
- Ottenere nuovi numeri tramite l' interfaccia di amministrazione di Skype for Business.
- Ottenere nuovi numeri che non sono disponibili nell'interfaccia di amministrazione Skype for Business.
- Trasferire i numeri di telefono esistenti dal provider di servizi o gestore di telefonia attuale a Office 365.

You must use the **Add new user numbers** page to see, search, acquire, and reserve those numbers. You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.

### <a name="get-new-user-phone-numbers"></a>Ottenere nuovi numeri di telefono degli utenti 
 
![Icona che mostra il logo](media/sfb-logo-30x30.png) di Skype for business **con l'interfaccia di amministrazione di Skype for business**

1. Accedere a Microsoft 365 con l'account di lavoro o dell'Istituto di istruzione.

2. Accedere all'interfaccia di **Amministrazione** > di Microsoft 365**Skype for business**.
    
3. Nella barra di spostamento sinistra, vai a**numeri di telefono** **vocale** > , fai clic su **Aggiungi nuovo numero** ![al pulsante Aggiungi,](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png)visualizzato come simbolo più, quindi fai clic su **nuovi numeri utente**.
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Ottenere nuovi numeri che non sono disponibili nell'interfaccia di amministrazione Skype for Business
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Trasferire numeri di telefono dal provider di servizi o dal gestore di telefonia
  
- Se sono necessari 999 o meno numeri di telefono per gli utenti, è possibile usare la procedura guidata **nuovo ordine di trasferimento** dei numeri locali nell'interfaccia di amministrazione di Skype for business. Seguire i passaggi descritti in [trasferire i numeri di telefono in teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) per trasferire i numeri di telefono.
    
- Se è necessario trasferire più di 999 numeri di telefono, vedere [gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) in modo da inviare una richiesta di servizio ordini di trasferimento o un ordine per trasferire tutti i numeri di telefono in Office 365. 

**Per informazioni dettagliate sull'acquisizione di nuovi numeri di telefono o il trasferimento di numeri esistenti, consultare [Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Passaggio 4: ottenere numeri di telefono di servizio (audioconferenza, le code di chiamata, gli operatori automatici)

In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.

### <a name="get-new-service-numbers"></a>Ottenere i numeri di servizio

![Icona che mostra il logo](media/sfb-logo-30x30.png) di Skype for business **con l'interfaccia di amministrazione di Skype for business**


1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Accedere all'interfaccia di **Amministrazione** > di Microsoft 365**Skype for business**.

3. Nella barra di spostamento sinistra, vai a**numeri** > di telefono **vocale** > **Aggiungi nuovo numero**e quindi fai clic su **nuovi numeri di servizio**.

    > [!IMPORTANT]
    > Per visualizzare l'opzione **Voice** nella barra di spostamento sinistra nell'interfaccia di amministrazione di Skype for business, è necessario prima acquistare almeno una licenza **Enterprise E5**, una licenza per il componente aggiuntivo per il **sistema telefonico** o una licenza per il componente aggiuntivo per i servizi di **audioconferenza** .

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Ottenere nuovi numeri che non sono disponibili nell'interfaccia di amministrazione Skype for Business
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers. 

### <a name="port-or-transfer-existing-service-numbers"></a>Portabilità o trasferimento dei numeri di servizio

If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Passaggio 5: se si desidera impostare i Piani di chiamata

If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up. Follow the three procedures below to complete the setup of your Calling Plan.

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>Aggiungere indirizzi e posizioni di emergenza per l'organizzazione

1. Nella pagina **Voce**, seleziona **Posizione per gli interventi di emergenza** > **Aggiungi**.

2. Nel riquadro **nuovo indirizzo** immettere un nome per l'indirizzo e quindi completare le caselle rimanenti.
    
     ![Screenshot del nuovo riquadro degli indirizzi](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > Per i clienti di lingua inglese, se il nome della strada è un numero, assicurarsi di includere la desinenza (come "st" o "th") come indicato nella figura sopra.

3. Seleziona **Convalida**.

    Se necessario, ti sarà chiesto di fare correzioni all'indirizzo.

    > [!CAUTION]
    > La convalida di un indirizzo civico o stradale implica la verifica della legittimità e della corretta formattazione dell'indirizzo. È possibile che un indirizzo per gli interventi di emergenza parzialmente corretto, in cui hai ad esempio digitato erroneamente il nome della città, superi comunque la fase di convalida. In caso di convalida nonostante gli errori di ortografia, la combinazione del nome della città errato e delle altre parti corrette dell'indirizzo fornisce informazioni sufficienti per instradare la chiamata al centro di emergenza appropriato.

    > [!TIP]
    > Se l'indirizzo deve essere corretto per un intervento di emergenza, verrà visualizzato un banner verde per indicare che l'indirizzo è stato aggiornato.

4. Dopo la convalida dell'indirizzo, seleziona **Salva**.

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>Assegnare numeri di telefono e indirizzi di emergenza agli utenti

> [!TIP]
> Se aggiungi altre persone alla tua azienda appena prima di questo passaggio, possono passare **diverse ore** prima che compaiano nella pagina **Utenti vocali**. C'è un periodo di latenza.

1. Nella pagina **Utenti vocali**, scegli le persone a cui vuoi assegnare un numero di telefono e un indirizzo per gli interventi di emergenza.

2. Seleziona **Assegna numero**.

3. Nella pagina **Assegna numero**, nel menu a discesa **Seleziona il numero da assegnare** scegli il numero di telefono per l'utente.

4. Per selezionare un indirizzo per gli interventi di emergenza, inserisci il nome della città nella casella **Trova città** e seleziona Cerca.

    > [!IMPORTANT]
    > Se non ti trovi negli Stati Uniti, i tuoi numeri hanno già un indirizzo per gli interventi di emergenza, ma puoi modificarlo in questa fase. Consulta [Assegnare o modificare l'indirizzo per gli interventi di emergenza di un utente](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user). 
  
5. Dopo avere assegnato sia il numero di telefono sia l'indirizzo per gli interventi di emergenza, seleziona **Salva**.

### <a name="tell-your-users-about-their-new-phone-numbers"></a>Informare gli utenti sui nuovi numeri di telefono


Consigliamo di inviare e-mail o usare il metodo di comunicazione standard dell'azienda per comunicare alle persone il nuovo numero di telefono.

Ecco come può vedere il numero di telefono nell'app **Skype for business** :

1. Esegui l'accesso a Skype for Business sul desktop.
    
2. Seleziona **Impostazioni** > **Strumenti** > **Opzioni**. 
    
     ![Screenshot delle opzioni del menu strumenti](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. Poi seleziona **Telefoni**. 
    
    ![Screenshot delle opzioni per il telefono Skype for business](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation. The phone number is shown above the dial pad.

![Screenshot delle opzioni disponibili dopo aver fatto clic su chiamate](media/teams-phone-number.png)

**Per informazioni più dettagliate su tutti i passaggi necessari per la configurazione di un Piano di chiamata, vedere [Impostare piani di chiamate](set-up-calling-plans.md).**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Passaggio 6: Se si desidera impostare Audioconferenze

Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.

You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Per le domande frequenti sui servizi di audioconferenza, vedere [Domande frequenti su Audioconferenze](audio-conferencing-common-questions.md).
    
1. Se sono state acquistate licenze per i componenti aggiuntivi per i servizi di **audioconferenza** e le licenze per i crediti di comunicazione, assegnarle. Per istruzioni, vedere [assegnare licenze di Microsoft teams](assign-teams-licenses.md).

    Decide on your audio conferencing provider. An audio conferencing provider supplies an audio conferencing bridge. The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings. Decide whether to use Microsoft or a third-party audio conferencing provider:

    > [!NOTE]
    > Gli utenti di Microsoft teams non possono usare un provider di servizi di audioconferenza di terze parti.

    - **Microsoft come provider di servizi di audioconferenza**: se desiderate la soluzione più semplice per le Audioconferenze, scegliete Microsoft come provider di servizi di audioconferenza.
    
    - **Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider. To find a provider, go to [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530).
 
2. Assign the audio conferencing provider to people who lead or schedule meetings. See [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

3. Set up meeting invitations. The following steps are optional, but a lot of admins like to do them: 
  
   1. [Personalizzare gli inviti alle riunioni in Skype for business](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations). I numeri di accesso esterno impostati per l'utente verranno aggiunti automaticamente agli inviti alla riunione inviati ai partecipanti. È tuttavia possibile aggiungere una guida e collegamenti legali personalizzati, un messaggio di testo e un elemento grafico aziendale di piccole dimensioni.
    
   2. Impostare i numeri di telefono per i servizi di audioconferenza per gli organizzatori della riunione inclusi negli inviti [in Skype for business](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) o [in Microsoft teams](set-the-phone-numbers-included-on-invites-in-teams.md). Questo è il numero di telefono che verrà visualizzato nella riunione pianificata dall'utente.
    
   3. Impostare le lingue per gli operatori automatici per i servizi di audioconferenza [in Skype for business](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) o [in Microsoft teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) che l'operatore automatico di audioconferenza USA per salutare un chiamante quando effettua la chiamata a un numero di telefono di audioconferenza. Questo passaggio si applica solo se si sta usando Microsoft come provider di audio.
    
   4. Impostare la lunghezza del PIN per le riunioni di audioconferenza [in Microsoft teams](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md).
    
      > [!NOTE]
      > This feature is not yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).

**Per altre informazioni sui servizi di audioconferenza, vedere [configurare le conferenze audio per Microsoft teams](set-up-audio-conferencing-in-teams.md).**

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>Passaggio 7: se si vuole configurare una coda di chiamata cloud

Le code delle chiamate Cloud includono i messaggi di saluto usati quando qualcuno chiama un numero di telefono per l'organizzazione, la possibilità di inserire automaticamente le chiamate in attesa e la possibilità di cercare il successivo agente di chiamata disponibile per gestire la chiamata mentre le persone che chiamano sono ascolto della musica in attesa. È possibile creare code di chiamata singole o multiple per l'organizzazione.

Prima di poter creare e configurare le code di chiamata, è necessario ottenere o trasferire i numeri di servizio a pagamento o a pedaggio esistenti. Dopo aver ottenuto i numeri di telefono del servizio a pagamento o a pedaggio gratuito, verranno visualizzati nei**numeri di telefono**della**voce** > dell'interfaccia di amministrazione > di **Skype for business**e il **tipo di numero** elencato verrà elencato come **servizio a pagamento gratuito **. Per ottenere i numeri di servizio, vedere [ottenere i numeri di servizio per Skype for business e Microsoft teams](/microsoftteams/getting-service-phone-numbers) oppure se si vuole trasferire un numero di servizio esistente, vedere [trasferire i numeri di telefono in teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.

Per creare una nuova coda di chiamata, nell'interfaccia di **amministrazione di Skype for business**, fare clic su **chiama** > **code di chiamata**di routing, fare clic su **Aggiungi nuovo**e quindi seguire le istruzioni del **passaggio 3** di [creare una coda di chiamata cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue).

**Per altre informazioni sulle code di chiamata, vedere [creare una coda di chiamata cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).**

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>Passaggio 8: se si vuole configurare un operatore automatico cloud

Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center.

Per creare un nuovo operatore automatico, nell'interfaccia di amministrazione di Skype for business, fare clic su chiama gli**operatori automatici**di **routing** > , fare clic su **Aggiungi nuovo**e quindi seguire le istruzioni per ogni pagina del **passaggio 2** di [creare un operatore automatico cloud ](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).


**Per altre informazioni sugli operatori automatici del cloud, vedere [configurare un operatore automatico per cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Passaggio 9: assegnare i numeri di telefono di servizio (audioconferenza, code di chiamata, operatori automatici)

Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want. For example, if you want a dedicated service phone number (toll or toll-free), you will need to assign the number to the conferencing bridge.

- Per i servizi di audioconferenza, è possibile assegnare un numero dedicato a un Bridge di conferenza accedendo all'interfaccia**di amministrazione di** >  **Microsoft 365** > per i servizi di**audioconferenza** di**Skype for business** > e facendo clic sul pulsante Bridge di conferenza o vedere [cambiare il numero verde o il numero verde nel Bridge di audioconferenza](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

- Per gli operatori automatici, è possibile assegnare un numero dedicato a un operatore automatico accedendo a **Microsoft 365** > **** > interfaccia di amministrazione dell'interfaccia di amministrazione di**Skype for business** > per gli operatori automatici di**routing** > delle chiamate** **e fai clic sull'operatore automatico. Nella pagina **generale** il numero di servizio già disponibile sarà elencato nell'elenco a discesa **numero di telefono** . Per informazioni dettagliate, vedere [configurare un operatore automatico cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).
- Per le code di chiamata, è possibile assegnare un numero dedicato a una**** > coda di chiamata accedendo alle**Code** delle chiamate di**routing** > delle chiamate di**Skype for business** > per **Microsoft 365** > e fare clic su nella coda di chiamata. Nella pagina **generale** il numero di servizio già disponibile sarà elencato nell'elenco a discesa **numero di telefono** . Per informazioni dettagliate, vedere [creare una coda di chiamata cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue).

**Per informazioni dettagliate su come ottenere nuovi numeri di servizio oppure su come trasferire numeri di servizio esistenti, vedere [Ottenere numeri di telefono di servizio](/microsoftteams/getting-service-phone-numbers).**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Passaggio 10: configurare i crediti per le comunicazioni per l'organizzazione

You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)
  
> [!NOTE]
> Per scoprire quanto costa, [consulta i prezzi qui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).

### <a name="to-set-up-communications-credits"></a>Per configurare i crediti per le comunicazioni

1. Accedere a Microsoft 365 con l'account di lavoro o dell'Istituto di istruzione.

2. Nella barra di spostamento sinistra dell'interfaccia di amministrazione accedere**ai componenti aggiuntivi** > per gli**abbonamenti** > per la **fatturazione** > **acquistare i componenti**aggiuntivi e quindi scegliere **Communications Credits** > **Buy Now**.

3. Nella pagina di sottoscrizione **crediti comunicazioni** immettere le informazioni e quindi fare clic su **Avanti**.

4. Immettere le informazioni di pagamento e scegliere **Esecuzione dell'ordine**.
    >[!IMPORTANT]
    >If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).
    
**Per ulteriori informazioni sulla configurazione del credito per lelcomunicazioni, vedere [configurare il credito per la comunicazione per l'organizzazione](set-up-communications-credits-for-your-organization.md).**
  
### <a name="assign-a-communications-credits-license-to-users"></a>Assegnare una licenza per i crediti di comunicazione agli utenti

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft 365, accedere a utenti**attivi**degli **utenti** > e quindi selezionare un utente o utenti dall'elenco.

3. Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**.

4. Nella pagina **licenze di prodotto** attivare l'opzione **crediti comunicazioni** **su** attivo per assegnare questa licenza e quindi fare clic su **Salva**.

    > [!NOTE]
    > Anche se ad alcuni utenti è assegnata una licenza **Enterprise E5**, è consigliabile comunque procedere in questo modo.

**Per ulteriori informazioni sull'assegnazione delle licenze Credito per la comunicazione, vedere [Configurare il credito per la comunicazione per l'organizzazione](set-up-communications-credits-for-your-organization.md).**

## <a name="related-topics"></a>Argomenti correlati
[Ecco cosa offre il Sistema telefonico in Office 365](here-s-what-you-get-with-phone-system.md)

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
