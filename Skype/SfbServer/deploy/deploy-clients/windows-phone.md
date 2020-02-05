---
title: Installare e testare Skype for business per Windows Phone
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 'Riepilogo: informazioni su come installare e testare Skype for business in un Windows Phone.'
ms.openlocfilehash: 63d766a566f131bc58540a13e2a19aa2add0700b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768589"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Installare e testare Skype for business per Windows Phone
 
**Riepilogo:** Informazioni su come installare e testare Skype for business in un Windows Phone.
  
L'app Skype for business per Windows Phone porta la presenza di Skype for business, la messaggistica istantanea (IM) e la chiamata vocale e video ai dispositivi Windows Mobile. Gli utenti con Lync 2013 otterranno automaticamente l'app aggiornata o verrà richiesto di aggiornarla manualmente, a seconda delle impostazioni dell'utente. I nuovi utenti possono scaricarlo da [Windows Phone Marketplace](https://go.microsoft.com/fwlink/p/?linkid=231901). L'app Skype for business per Windows Phone è disponibile solo in Windows Phone 8,1 e versioni successive.
  
Prima di indirizzare gli utenti dell'organizzazione a scaricare l'app, dovrai eseguire i test seguenti per verificare che sia integrata correttamente nell'ambiente. 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Installare Skype for business per Windows Phone 8,1

1. Passare a [Windows Phone 8 Update Central](https://www.windowsphone.com/en-us/how-to/wp8/update-central) per aggiornare il telefono a windows phone 8,1.
    
2. Dal telefono, accedere allo **Store**e cercare **Skype for business**.
    
3. Toccare **Installa**. 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Accedere a Skype for business per la prima volta

1. Nella schermata **Start** scorrere rapidamente verso sinistra per visualizzare le app installate, cercare Skype for business per Windows Phone e quindi toccare l'icona per aprire l'app.
    
2. Immettere l'indirizzo di accesso (ad esempio user@domain.com) e la password, quindi toccare **fine**.
    
     Potrebbe essere richiesto sia un nome utente che un indirizzo di accesso. Il nome utente è quello usato per accedere alla rete dell'organizzazione, sia user@domain.com che dominio\nomeutente.
    
3. Nella schermata del **programma Analisi utilizzo software** toccare **partecipa** per inviare i dati anonimi relativi a problemi di app e l'utilizzo a Microsoft o **No grazie** se si preferisce non partecipare.
    
4. Nella schermata **non perdere le chiamate al lavoro** , immettere il numero di cellulare con i codici paese e area geografica. Quando Skype for business per Windows Phone non può usare una rete Wi-Fi o dati cellulare per effettuare una chiamata audio o video, verrà automaticamente chiamato a questo numero e connesso alla parte audio della chiamata.
    
5. Toccare **Avanti** e rivedere le impostazioni di notifica e accesso alla Rubrica:
    
   - **Notifiche push** Ricevere un avviso quando si riceve un nuovo messaggio istantaneo o una chiamata. Normalmente **attivato** (scelta consigliata).
    
     > [!IMPORTANT]
     > Se si disattiva questa impostazione, non si riceveranno notifiche di messaggi istantanei, chiamate o altri avvisi di Skype for business per Windows Phone, a meno che l'app non sia attiva. 
  
   - **Consentire l'accesso alla rubrica** Cercare i contatti sul cellulare quando si cercano contatti in Skype for business per Windows Phone.
    
6. Toccare **Avanti** per iniziare a usare Skype for business per Windows Phone.
    
    [Serve aiuto per l'accesso?](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>Verificare l'installazione del client mobile

Dopo aver configurato il client e eseguito l'accesso, seguire i seguenti test per verificare che l'installazione di Skype for business per Windows Phone funzioni correttamente nel dispositivo mobile.
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>Cercare un contatto nella directory aziendale

1. Nell'elenco contatti toccare **Cerca**.
    
2. Cercare un contatto esistente solo nell'elenco indirizzi globale.
    
3. Verificare che il nome del contatto venga visualizzato nei risultati della ricerca.
    
### <a name="test-instant-messaging-and-presence"></a>Testare la messaggistica istantanea e la presenza

1. Nell'elenco contatti toccare un contatto.
    
2. Nella scheda contatto toccare la messaggistica istantanea (IM) ![Icona per la messaggistica istantanea in Skype for business](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)icona.
    
3. Verificare che venga visualizzata una finestra di messaggistica istantanea e che sia possibile digitare e inviare un messaggio istantaneo.
    
### <a name="test-dial-out-conferencing"></a>Testare i servizi di conferenza telefonica con accesso esterno

1. In Outlook pianificare una riunione Skype for business.
    
2. In Windows Phone aprire l'invito alla riunione.
    
3. Fare clic sul collegamento nella riunione per partecipare.
    
4. Rispondere alla chiamata dal servizio di conferenza e verificare che l'audio della riunione sia connesso.
    
### <a name="test-push-notifications"></a>Verificare le notifiche push

1. Selezionare due account utente diversi per questo test. 
    
2. In Windows Phone dell'utente, accedere a Skype for business per Windows Phone con l'account dell'utente.
    
3. Aprire un'altra applicazione nel dispositivo.
    
4. In un client diverso, ad esempio il client desktop, accedi a Skype for business con l'account dell'utente B.
    
5. Inviare un messaggio istantaneo dall'utente B all'utente a.
    
6. Verificare che la notifica di messaggistica istantanea venga visualizzata nel dispositivo mobile dell'utente.
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Rimuovere Skype for business dal Windows Phone

Per rimuovere l'app Skype for business per Windows Phone dal dispositivo mobile: 
  
1. Nella schermata Start scorrere rapidamente per visualizzare l'elenco delle applicazioni. 
    
2. Toccare e tenere premuta l'applicazione Skype for business per Windows Phone e quindi selezionare **Disinstalla**.
    


