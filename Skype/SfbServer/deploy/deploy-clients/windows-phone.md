---
title: Installare e testare Skype for business per Windows Phone
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
description: 'Riepilogo: informazioni su come installare e testare Skype for business nel Windows Phone.'
ms.openlocfilehash: 8323231f67e8aca87d3670cfee1a2137f0dd6c21
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812716"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Installare e testare Skype for business per Windows Phone
 
**Riepilogo:** Informazioni su come installare e testare Skype for business nel Windows Phone.
  
L'app Skype for business per Windows Phone porta la presenza di Skype for business, la messaggistica istantanea e le chiamate vocali e video ai dispositivi Windows Mobile. Gli utenti che dispongono di Lync 2013 avranno l'app aggiornata automaticamente o verranno invitati a aggiornarla manualmente, a seconda delle impostazioni dell'utente. I nuovi utenti possono scaricarlo dal [Marketplace di Windows Phone](https://go.microsoft.com/fwlink/p/?linkid=231901). L'app Skype for business per Windows Phone è disponibile solo su Windows Phone 8,1 e versioni successive.
  
Prima di indirizzare gli utenti all'interno dell'organizzazione per scaricare l'app, è necessario eseguire i test seguenti per assicurarsi che siano integrati correttamente nell'ambiente in uso. 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Installare Skype for Business Windows Phone 8,1

1. Passare a [Windows Phone 8 Update Central](https://www.windowsphone.com/en-us/how-to/wp8/update-central) per aggiornare il telefono a windows phone 8,1.
    
2. Dal telefono, Vai allo **Store** e Cerca **Skype for business**.
    
3. Toccare **Installa**. 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Accedere a Skype for business per la prima volta

1. Nella schermata **Start** Scorri verso sinistra per visualizzare le app installate, Cerca Skype for business per Windows Phone e quindi tocca l'icona per aprire l'app.
    
2. Immettere l'indirizzo di accesso (ad esempio, user@domain.com) e la password, quindi toccare **fine**.
    
     È possibile che ti vengano richiesti un nome utente che un indirizzo di accesso. Il nome utente è ciò che si utilizza per accedere alla rete dell'organizzazione, sia user@domain.com che dominio\nomeutente.
    
3. Nella schermata Analisi utilizzo **software** , toccare **Unisci** per inviare i dati anonimi sui problemi relativi all'app e sull'uso a Microsoft o **No grazie** se si preferisce non partecipare.
    
4. Nella schermata **non perdere mai le chiamate di lavoro** , immettere il proprio numero di cellulare con i codici paese e area geografica. Quando Skype for business per Windows Phone non è in grado di utilizzare una rete di dati Wi-Fi o cellulare per effettuare una chiamata audio o video, verrà automaticamente chiamato a questo numero e connesso alla parte audio della chiamata.
    
5. Toccare **Avanti** ed esaminare le impostazioni di notifica e accesso alla Rubrica:
    
   - **Notifiche push** Ottenere un avviso quando si riceve un nuovo messaggio istantaneo o una nuova chiamata. Normalmente **attiva** (scelta consigliata).
    
     > [!IMPORTANT]
     > Se si disattiva questa impostazione, non si riceverà alcuna notifica dell'IMs, delle chiamate o di altri avvisi di Skype for business per Windows Phone, a meno che l'app non sia attiva. 
  
   - **Consenti accesso alla rubrica** Cerca i contatti sul tuo cellulare quando cerchi contatti in Skype for business per Windows Phone.
    
6. Toccare **Avanti** per iniziare a usare Skype for business per Windows Phone.
    
    [Occorrono indicazioni per l'accesso?](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>Verificare l'installazione del client per dispositivi mobili

Dopo aver configurato il client e aver eseguito l'accesso, utilizzare i test seguenti per verificare che l'installazione di Skype for business per Windows Phone funzioni correttamente sul dispositivo mobile.
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>Cercare un contatto nella directory aziendale

1. Nell'elenco contatti toccare **Cerca**.
    
2. Cercare un contatto presente solo nell'elenco indirizzi globale.
    
3. Verificare che il nome del contatto sia incluso nei risultati della ricerca.
    
### <a name="test-instant-messaging-and-presence"></a>Testare la messaggistica istantanea e la presenza

1. Toccare un contatto nell'elenco contatti.
    
2. Nella scheda contatto toccare la messaggistica istantanea (IM) ![Icona per la messaggistica istantanea in Skype for business](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png).
    
3. Verificare che venga visualizzata una finestra di messaggistica istantanea e che sia possibile digitare e inviare un messaggio istantaneo.
    
### <a name="test-dial-out-conferencing"></a>Testare le funzionalità di conferenza telefonica con accesso esterno

1. In Outlook, pianificare una riunione di Skype for business.
    
2. Nel Windows Phone aprire l'invito alla riunione.
    
3. Fare clic sul collegamento nell'invito per partecipare alla riunione.
    
4. Rispondere alla chiamata dal servizio di conferenza e verificare di essere connessi all'audio della riunione.
    
### <a name="test-push-notifications"></a>Verificare le notifiche push

1. Selezionare due account utente diversi per questo test. 
    
2. Su Windows Phone dell'utente A, accedi a Skype for business per Windows Phone con l'account utente A.
    
3. Aprire un'altra applicazione nel dispositivo.
    
4. In un client diverso, ad esempio il client desktop, accedere a Skype for business con l'account dell'utente B.
    
5. Inviare un messaggio istantaneo dall'utente B all'utente A.
    
6. Verificare che la notifica di messaggistica istantanea venga visualizzata nel dispositivo mobile dell'utente A.
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Rimuovere Skype for business dal Windows Phone

Per rimuovere l'app Skype for business per Windows Phone dal dispositivo mobile: 
  
1. Nella schermata Start scorrere rapidamente per visualizzare l'elenco delle applicazioni. 
    
2. Toccare e tenere premuto l'applicazione Skype for business per Windows Phone e quindi fare clic su **Disinstalla**.
    


