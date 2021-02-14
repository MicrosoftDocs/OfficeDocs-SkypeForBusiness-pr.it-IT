---
title: Installare e testare Skype for Business per Windows Phone
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 'Riepilogo: informazioni su come installare e testare Skype for Business in Windows Phone.'
ms.openlocfilehash: 8323231f67e8aca87d3670cfee1a2137f0dd6c21
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812716"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Installare e testare Skype for Business per Windows Phone
 
**Riepilogo:** Scopri come installare e testare Skype for Business in Windows Phone.
  
L'app Skype for Business per Windows Phone porta la presenza di Skype for Business, la messaggistica istantanea e le chiamate vocali e video ai dispositivi mobili Windows. Gli utenti con Lync 2013 o riceveranno automaticamente l'app aggiornata o verrà richiesto di aggiornarla manualmente, a seconda delle impostazioni utente. I nuovi utenti possono scaricarlo da [Windows Phone Marketplace.](https://go.microsoft.com/fwlink/p/?linkid=231901) L'app Skype for Business per Windows Phone è disponibile solo in Windows Phone 8.1 e versioni successive.
  
Prima di indirizzare gli utenti dell'organizzazione a scaricare l'app, è necessario eseguire i test seguenti per verificare che sia integrata correttamente nell'ambiente. 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Installare Skype for Business per Windows Phone 8.1

1. Passare a [Windows Phone 8 Update Central](https://www.windowsphone.com/en-us/how-to/wp8/update-central) per aggiornare il telefono a Windows Phone 8.1.
    
2. Dal telefono, accedere a **Store** e cercare **Skype for Business.**
    
3. Toccare **Installa**. 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Accedere a Skype for Business per la prima volta

1. On the **Start** screen, swipe left to view your installed apps, search for Skype for Business for Windows Phone, and then tap the icon to open the app.
    
2. Immetti l'indirizzo di accesso (ad esempio, user@domain.com) e la password, quindi tocca **Fine.**
    
     È possibile che ti vengano richiesti un nome utente che un indirizzo di accesso. Il nome utente è quello che usi per accedere alla rete dell'organizzazione, user@domain.com o dominio\nomeutente.
    
3. Nella schermata **Analisi** utilizzo software  toccare Partecipa per inviare a Microsoft  dati anonimi sui problemi e l'utilizzo delle app oppure no, se si preferisce non partecipare.
    
4. Nella schermata **Non perdere mai le chiamate di lavoro,** immettere il numero di cellulare con i codici paese e area geografica. Quando Skype for Business per Windows Phone non può usare un Wi-Fi o una rete dati cellulare per effettuare una chiamata audio o video, verrà chiamato automaticamente a questo numero e connesso alla parte audio della chiamata.
    
5. Toccare **Avanti ed** esaminare le impostazioni di accesso alla notifica e alla rubrica:
    
   - **Notifiche push** Ricevere un avviso quando si riceve una nuova messaggistica istantanea o una nuova chiamata. Normalmente **on** (scelta consigliata).
    
     > [!IMPORTANT]
     > Se si disattiva questa impostazione, non si verrà informati di messaggistica unificata, chiamate o altri avvisi di Skype for Business per Windows Phone, a meno che l'app non sia attiva. 
  
   - **Consentire l'accesso alla rubrica** Cercare i contatti sul telefono cellulare quando si ricercano contatti in Skype for Business per Windows Phone.
    
6. Toccare **Avanti** per iniziare a usare Skype for Business per Windows Phone.
    
    [Occorrono indicazioni per l'accesso?](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>Verificare l'installazione dei client mobili

Dopo aver configurato il client e aver eseguito correttamente l'accesso, utilizzare i test seguenti per verificare che l'installazione di Skype for Business per Windows Phone funzioni correttamente nel dispositivo mobile.
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>Cercare un contatto nella directory aziendale

1. Nell'elenco Contatti toccare **Cerca.**
    
2. Cercare un contatto presente solo nell'elenco indirizzi globale.
    
3. Verificare che il nome del contatto sia incluso nei risultati della ricerca.
    
### <a name="test-instant-messaging-and-presence"></a>Testare la messaggistica istantanea e la presenza

1. Toccare un contatto nell'elenco contatti.
    
2. Nella scheda contatto toccare la messaggistica istantanea ![Icona per la messaggistica istantanea in Skype for Business](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png).
    
3. Verificare che venga visualizzata una finestra di messaggistica istantanea e che sia possibile digitare e inviare un messaggio istantaneo.
    
### <a name="test-dial-out-conferencing"></a>Testare le funzionalità di conferenza telefonica con accesso esterno

1. In Outlook, pianificare una riunione Skype for Business.
    
2. In Windows Phone, aprire l'invito alla riunione.
    
3. Fare clic sul collegamento nell'invito per partecipare alla riunione.
    
4. Rispondere alla chiamata dal servizio di conferenza e verificare di essere connessi all'audio della riunione.
    
### <a name="test-push-notifications"></a>Verificare le notifiche push

1. Selezionare due account utente diversi per il test. 
    
2. In Windows Phone dell'utente A, accedere a Skype for Business per Windows Phone con l'account dell'utente A.
    
3. Apri un'altra applicazione nel dispositivo.
    
4. In un client diverso, ad esempio il client desktop, accedere a Skype for Business con l'account dell'utente B.
    
5. Inviare un messaggio istantaneo dall'utente B all'utente A.
    
6. Verificare che la notifica di messaggistica istantanea venga visualizzata nel dispositivo mobile dell'utente A.
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Rimuovere Skype for Business da Windows Phone

Per rimuovere l'app Skype for Business per Windows Phone dal dispositivo mobile: 
  
1. Dalla schermata Start scorri rapidamente per visualizzare l'elenco delle applicazioni. 
    
2. Toccare e tenere premuta l'applicazione Skype for Business per Windows Phone, quindi selezionare **Disinstalla.**
    


