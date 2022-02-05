---
title: Installare e testare Skype for Business per Windows Phone
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 'Riepilogo: informazioni su come installare e testare Skype for Business nel Windows Phone.'
---

# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Installare e testare Skype for Business per Windows Phone
 
**Riepilogo:** Informazioni su come installare e testare Skype for Business nella Windows Phone.
  
L Skype for Business per Windows Phone app offre Skype for Business presenza, messaggistica istantanea e chiamate vocali e video Windows dispositivi mobili. Gli utenti con Lync 2013 o riceveranno automaticamente l'app aggiornata o verrà richiesto di aggiornarla manualmente, a seconda delle impostazioni utente. I nuovi utenti possono scaricarlo da [Windows Phone Marketplace](https://go.microsoft.com/fwlink/p/?linkid=231901). L Skype for Business per Windows Phone app è disponibile solo in Windows Phone 8.1 e versioni successive.
  
Prima di indirizzare gli utenti dell'organizzazione a scaricare l'app, è necessario eseguire i test seguenti per verificare che sia correttamente integrata nell'ambiente. 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Installare Skype for Business Windows Phone 8.1

1. Passare a [Windows Phone 8 update central](https://www.windowsphone.com/en-us/how-to/wp8/update-central) per aggiornare il telefono a Windows Phone 8.1.
    
2. Dal telefono, passare a **Store** e **cercare Skype for Business.**
    
3. Toccare **Installa**. 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Accedere a Skype for Business per la prima volta

1. Nella schermata **Start** scorri rapidamente verso sinistra per visualizzare le app installate, cerca Skype for Business per Windows Phone e quindi tocca l'icona per aprire l'app.
    
2. Immetti l'indirizzo di accesso (ad esempio, user@domain.com) e la password, quindi tocca **Fine**.
    
     È possibile che ti vengano richiesti un nome utente che un indirizzo di accesso. Il nome utente è quello utilizzato per accedere alla rete dell'organizzazione, user@domain.com o dominio\nomeutente.
    
3. Nella schermata **Analisi** utilizzo software toccare Partecipa per inviare  a Microsoft dati anonimi relativi a problemi e utilizzo dell'app  oppure No grazie se si preferisce non partecipare.
    
4. Nella schermata **Non perdere mai le chiamate di lavoro** immetti il numero di cellulare con i codici paese e area geografica. Quando Skype for Business per Windows Phone non è possibile usare una rete dati Wi-Fi o cellulare per effettuare una chiamata audio o video, verrà chiamato automaticamente a questo numero e connesso alla parte audio della chiamata.
    
5. Toccare **Avanti ed** esaminare le impostazioni di accesso alle notifiche e alla rubrica:
    
   - **Notifiche push** Ricevere un avviso quando si riceve una nuova messaggistica istantanea o una nuova chiamata. Normalmente **on** (scelta consigliata).
    
     > [!IMPORTANT]
     > Se dissegni questa impostazione, non ti verranno notificati messaggistica unificata, chiamate o altri avvisi Skype for Business per Windows Phone a meno che l'app non sia attiva. 
  
   - **Consentire l'accesso alla rubrica** Cercare i contatti nel telefono cellulare quando si ricercano i contatti in Skype for Business per Windows Phone.
    
6. Toccare **Avanti** per iniziare a usare Skype for Business per Windows Phone.
    
    [Occorrono indicazioni per l'accesso?](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>Verificare l'installazione del client per dispositivi mobili

Dopo aver configurato il client e aver eseguito correttamente l'accesso, usa i test seguenti per verificare che l'installazione di Skype for Business per Windows Phone funzioni correttamente nel dispositivo mobile.
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>Cercare un contatto nella directory aziendale

1. Nell'elenco Contatti toccare **Cerca**.
    
2. Cercare un contatto presente solo nell'elenco indirizzi globale.
    
3. Verificare che il nome del contatto sia incluso nei risultati della ricerca.
    
### <a name="test-instant-messaging-and-presence"></a>Testare la messaggistica istantanea e la presenza

1. Toccare un contatto nell'elenco contatti.
    
2. Nella scheda contatto toccare la messaggistica istantanea ![Icona per la messaggistica istantanea in Skype for Business.](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png).
    
3. Verificare che venga visualizzata una finestra di messaggistica istantanea e che sia possibile digitare e inviare un messaggio istantaneo.
    
### <a name="test-dial-out-conferencing"></a>Testare le funzionalità di conferenza telefonica con accesso esterno

1. In Outlook, pianificare una Skype for Business riunione.
    
2. Nel Windows Phone, aprire l'invito alla riunione.
    
3. Fare clic sul collegamento nell'invito per partecipare alla riunione.
    
4. Rispondere alla chiamata dal servizio di conferenza e verificare di essere connessi all'audio della riunione.
    
### <a name="test-push-notifications"></a>Verificare le notifiche push

1. Selezionare due account utente diversi per questo test. 
    
2. Nella pagina A dell'Windows Phone, accedi a Skype for Business per Windows Phone con l'account dell'utente A.
    
3. Apri un'altra applicazione nel dispositivo.
    
4. In un altro client, ad esempio il client desktop, accedi a Skype for Business con l'account dell'utente B.
    
5. Inviare un messaggio istantaneo dall'utente B all'utente A.
    
6. Verificare che la notifica di messaggistica istantanea venga visualizzata nel dispositivo mobile dell'utente A.
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Rimuovere Skype for Business dalla Windows Phone

Per rimuovere l Skype for Business per Windows Phone app dal dispositivo mobile: 
  
1. Dalla schermata Start scorri rapidamente per visualizzare l'elenco delle applicazioni. 
    
2. Toccare e tenere premuta Skype for Business per Windows Phone'applicazione e quindi selezionare **Disinstalla**.
    


