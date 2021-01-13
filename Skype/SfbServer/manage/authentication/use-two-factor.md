---
title: Utilizzare l'autenticazione a due fattori con il client Skype for business e Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: "Riepilogo: utilizzare l'autenticazione a due fattori con Skype for Business Server e Skype for business."
ms.openlocfilehash: 72ec3570d632eecefd28ebfd0aa50eb70c54ff99
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806541"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Utilizzare l'autenticazione a due fattori con il client Skype for business e Skype for Business Server
 
**Riepilogo:** Utilizzare l'autenticazione a due fattori con Skype for Business Server e Skype for business.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Accedere a Skype for business per la prima volta

Le informazioni di accesso vengono generalmente configurate automaticamente quando viene installato Skype for business. Tuttavia, la prima volta che si utilizza Skype for business, potrebbe essere necessario avviare manualmente il client.
  
### <a name="to-sign-in-for-the-first-time"></a>Per accedere per la prima volta

1. Accedere alla rete dell'organizzazione.
    
2. Selezionare **Avvia**  >  **tutti i programmi**  >  **Skype for business**.
    
    Verrà visualizzata la schermata di accesso.
    
    - Se la casella indirizzo di accesso è già stata compilata, verificare che l'indirizzo visualizzato sia corretto.
    
    - Se non è corretto o se la casella è vuota, immettere l'indirizzo di accesso (in genere corrisponde all'indirizzo di posta elettronica).
    
    - Se viene visualizzata una casella password vuota, aggiungere la password.
    
3. Selezionare **accesso**.
    
## <a name="sign-out-of-skype-for-business"></a>Disconnettersi da Skype for business

Al termine dell'utilizzo di Skype for business, è possibile chiudere la visualizzazione, disconnettersi dalla sessione o uscire dal programma, tutto dal menu file. Nella tabella seguente vengono illustrate le differenze tra le opzioni.
  
|**Opzione**|**Funzione**|**Modalità di esecuzione**|
|:-----|:-----|:-----|
|Chiudere  <br/> |Consente di chiudere il monitor ma di continuare a eseguire la sessione di Skype for business identificata con l'ID utente. In questo modo è possibile continuare a ricevere notifiche e interagire con altri utenti. <br/> <br/> È possibile ottenere la visualizzazione in qualsiasi momento facendo clic sull'icona Skype for business nella barra delle applicazioni o nell'area di notifica nella parte inferiore dello schermo.  <br/> | Nella finestra principale di Skype for business, eseguire una delle operazioni seguenti: <br/> 1. Selezionare il pulsante **Opzioni** , quindi selezionare   >  **Chiudi** file.  <br/> 2. fare clic sul pulsante **Chiudi** (X) nell'angolo in alto a destra della finestra. <br/> |
|Disconnessione  <br/> |Termina la sessione associata all'ID utente, ma Skype for business continua a essere eseguito in background. Quando si effettua l'accesso, verrà visualizzata la finestra di accesso.  <br/> **Suggerimento:** Selezionare **Elimina le informazioni** di accesso quando si effettua l'accesso per rimuovere il record dell'ID di accesso e della password dal computer. In questo modo, è possibile facilitare la risoluzione dei problemi di accesso per il supporto alle persone. È inoltre possibile garantire che le informazioni di accesso siano più sicure rendendo difficile per gli utenti non autorizzati l'accesso con le credenziali. <br/> |Nella finestra principale di Skype for business, seleziona il pulsante **Opzioni** , quindi seleziona   >  **Disconnetti** file.  <br/> |
|Uscita  <br/> |Termina la sessione di Skype for business e interrompe Skype for business nel computer. Dopo l'uscita, se si desidera riavviare, selezionare **Avvia**  >  **tutti i programmi** > Skype for business. <br/> |Nella finestra principale di Skype for business, selezionare il pulsante **Opzioni** , quindi selezionare   >  **Esci** file.  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Accedere a Skype for business con una smart card

Alcune organizzazioni ora utilizzano un processo di accesso a più passaggi, denominato autenticazione a due fattori, per aumentare la sicurezza per i propri utenti. Se si prevede di utilizzare questa opzione, sarà necessario disporre di una "smart card" per accedere a Skype for business. Le smart card possono essere fisiche o virtuali:
  
- **Fisica** Circa le dimensioni di una carta di credito. È possibile inserirlo in un lettore di smart card quando si effettua l'accesso.
    
- **Virtuale** Non è un oggetto fisico, ma un identificatore elettronico che viene scritto in un chip speciale sul computer, che in sostanza crea la smart card nel computer in uso. Disponibile solo per l'utilizzo con i computer Windows 8 che contengono il chip TPM (Trusted Platform Module).
    
### <a name="enroll-your-smart-card"></a>Registrare la smart card

Prima di poter accedere con una smart card, è necessario che la scheda sia "registrazione", ovvero che le credenziali utente debbano essere identificate con la scheda. Questo è il caso se la scheda è fisica o virtuale. Questo processo potrebbe essere già stato eseguito dall'amministratore di Skype for Business Server. Verifica se non si è certi che l'operazione sia stata completata.
  
> [!NOTE]
> Poiché ogni smart card virtuale è associata solo al dispositivo in cui è installato, sarà necessario registrare una scheda separata per ogni computer Windows 8 utilizzato. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Per registrare manualmente la smart card

1. Eseguire l'accesso al computer in cui verrà eseguito Skype for business.
    
2. Tramite Internet Explorer, passare alla pagina di registrazione Web dell'autorità di certificazione dell'organizzazione. 
    
    Rivolgersi all'amministratore di Skype for Business Server per l'indirizzo Web di questa risorsa se non è già presente. L'URL avrà un aspetto simile al seguente: https://MyCA . [ YourCompanyName]. com/certsrv.
    
    > [!NOTE]
    > Se si utilizza Internet Explorer 10, potrebbe essere necessario visualizzare questo sito Web in modalità compatibilità. 
  
3. Quando viene richiesto di accedere alla pagina certificazione, eseguire l'accesso utilizzando l'account di dominio (anziché l'amministratore del computer).
    
4. Nella pagina di benvenuto del sito Web, selezionare **Richiedi un certificato**.
    
5. Selezionare **richiesta avanzata**.
    
6. Selezionare **Crea e invia una richiesta all'autorità di certificazione**, quindi fare clic su **Avanti**.
    
7. Verrà visualizzata una pagina denominata stazione di registrazione smart card. Approvare la richiesta di installazione del controllo ActiveX e quindi completare il modulo di richiesta Advanced Certificate come indicato di seguito:
    
    a. Selezionare **utente smartcard** nell'elenco a discesa **modello di certificato** .
    
    b. Selezionare **Crea nuovo set di chiavi**.
    
    c. Trovare le informazioni sul produttore nell'etichetta della smart card e selezionarlo nell'elenco a discesa **CSP** .
    
    d. Selezionare **CSP** come formato di richiesta, se non è già selezionato.
    
    e. Selezionare **SHA1** dall'elenco a discesa dell'algoritmo hash, se non è già selezionato.
    
    f. Assegnare un nome al certificato che si desidera riconoscere e fare clic su **Invia**.
    
8. A questo punto, inserire la smart card vuota nel lettore di schede collegato alla stazione di registrazione e fare clic su **registra**.
    
9. Quando richiesto, immettere il proprio PIN (Personal Identification Number) e quindi fare clic su **OK**.
    
    > [!NOTE]
    > Se la persona del supporto tecnico non ha fornito un PIN speciale da utilizzare per registrare la smart card, utilizzare il valore del PIN della smart card predefinita, che è 12345678. 
  
10. Selezionare l'opzione per imporre all'utente di modificare il PIN al primo utilizzo della smart card.
    
11. A questo punto, inserire la smart card vuota nel lettore di schede collegato alla stazione di registrazione e fare clic su **registra**.
    
12. Quando richiesto, immettere il proprio PIN (Personal Identification Number) e quindi fare clic su **OK**.
    
    > [!NOTE]
    > Se la persona del supporto tecnico non ha fornito un PIN speciale da utilizzare per registrare la smart card, utilizzare il valore del PIN della smart card predefinita, che è 12345678. 
  
13. Selezionare l'opzione per imporre all'utente di modificare il PIN al primo utilizzo della smart card.
    
14. Fare clic su **OK** per confermare che il certificato visualizzato contiene le informazioni su di esso.
    
15. Dopo aver visualizzato l'avviso che il certificato è stato emesso, fare clic su **installa questo certificato** per completare il processo di registrazione.
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Accedere a Skype for business con le credenziali smart card

Prima di utilizzare la smart card per la prima volta, si consiglia di fare clic su **Elimina le informazioni di accesso** nella pagina di accesso di Skype for business. In questo modo vengono cancellate le credenziali di accesso archiviate nel computer e viene eliminata una possibile origine di errore.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Per accedere a Skype for business con le credenziali smart card

1. Avviare il client Skype for business.
    
2. Nella schermata di accesso digitare il nome dell'account utente di accesso nella casella **indirizzo di accesso** e quindi fare clic su **Accedi**.
    
3. Se si utilizza una smart card virtuale, ignorare questo passaggio.
    
    Se si utilizza una smart card fisica, inserire la smart card nel lettore di smart card e quindi fare clic su **OK** quando la scheda viene rilevata.
    
4. Digitare il numero di PIN per la smart card e quindi fare clic su **OK**.
    
    > [!NOTE]
    > Se non è stato assegnato un numero PIN della smart card dalla persona di supporto, utilizzare il valore predefinito, che è 12345678. 
  
## <a name="see-also"></a>Vedere anche

[Gestire l'autenticazione a due fattori in Skype for Business Server](two-factor-authentication.md)
  
[Configurare l'autenticazione a due fattori in Skype for Business Server](configure-two-factor.md)
