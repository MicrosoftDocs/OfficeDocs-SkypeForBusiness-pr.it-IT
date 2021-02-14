---
title: Usare l'autenticazione a due fattori con il client Skype for Business e Skype for Business Server
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
description: "Riepilogo: usare l'autenticazione a due fattori con Skype for Business Server e Skype for Business."
ms.openlocfilehash: 72ec3570d632eecefd28ebfd0aa50eb70c54ff99
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806541"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Usare l'autenticazione a due fattori con il client Skype for Business e Skype for Business Server
 
**Riepilogo:** Usare l'autenticazione a due fattori con Skype for Business Server e Skype for Business.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Accedere a Skype for Business per la prima volta

Le informazioni di accesso vengono in genere configurate automaticamente durante l'installazione di Skype for Business. Ma la prima volta che usi Skype for Business, potrebbe essere necessario avviare manualmente il client.
  
### <a name="to-sign-in-for-the-first-time"></a>Per accedere per la prima volta

1. Accedere alla rete dell'organizzazione.
    
2. Selezionare **Avvia**  >  **tutti i programmi** di Skype for  >  **Business.**
    
    Verrà visualizzata la schermata di accesso.
    
    - Se la casella dell'indirizzo di accesso è già stata compilata, verificare che l'indirizzo visualizzato sia corretto.
    
    - Se non è corretto o se la casella è vuota, immettere l'indirizzo di accesso (in genere corrisponde all'indirizzo di posta elettronica).
    
    - Se viene visualizzata una casella della password vuota, aggiungere la password.
    
3. Selezionare **Accedi.**
    
## <a name="sign-out-of-skype-for-business"></a>Disconnettersi da Skype for Business

Quando hai finito di usare Skype for Business, puoi chiudere lo schermo, disconnetterti dalla sessione o uscire dal programma, tutto dal menu File. Nella tabella seguente vengono illustrate le differenze tra le opzioni.
  
|**Opzione**|**Funzione**|**Come eseguirlo**|
|:-----|:-----|:-----|
|Chiudi  <br/> |Chiude lo schermo, ma consente di continuare a eseguire la sessione di Skype for Business identificata con l'ID utente. In questo modo puoi continuare a ricevere notifiche e interagire con altri utenti. <br/> <br/> Puoi ottenere lo schermo in qualsiasi momento facendo clic sull'icona di Skype for Business sulla barra delle applicazioni o nell'area di notifica nella parte inferiore dello schermo.  <br/> | Nella finestra principale di Skype for Business eseguire una delle operazioni seguenti: <br/> 1. Selezionare il **pulsante Opzioni,** quindi selezionare **Chiudi**  >  **file.**  <br/> 2. Fare clic **sul** pulsante Chiudi (X) nell'angolo superiore destro della finestra. <br/> |
|Disconnettersi  <br/> |Termina la sessione associata all'ID utente, ma Skype for Business continua a essere eseguito in background. Quando ci si disconnette, viene visualizzata la finestra di accesso.  <br/> **Suggerimento:** Selezionare **Elimina le informazioni di accesso quando** ci si disconnette per rimuovere il record dell'ID di accesso e della password dal computer. Questa operazione potrebbe facilitare la risoluzione dei problemi di accesso da parte degli utenti del supporto tecnico. Può anche contribuire a garantire che le informazioni di accesso siano più sicure rendendo difficile per gli utenti non autorizzati accedere con le credenziali. <br/> |Nella finestra principale di Skype for Business seleziona il pulsante **Opzioni,** quindi seleziona   >  **Disconnei file.**  <br/> |
|Esci  <br/> |Termina la sessione di Skype for Business e arresta Skype for Business nel computer. After exiting, if you want to restart, select **Start**  >  **All Programs** > Skype for Business. <br/> |Nella finestra principale di Skype for Business seleziona il pulsante **Opzioni,** quindi seleziona **Esci dal**  >  **file.**  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Accedere a Skype for Business con una smart card

Alcune organizzazioni ora utilizzano un processo di accesso a più passaggi, denominato autenticazione a due fattori, per aumentare la sicurezza per gli utenti. Se si prevede di usare questa opzione, è necessaria una "smart card" per accedere a Skype for Business. Le smart card possono essere fisiche o virtuali:
  
- **Fisico** Informazioni sulle dimensioni di una carta di credito. È possibile inserirla in un lettore di smart card quando si esegue l'accesso.
    
- **Virtuale** Non un oggetto fisico, ma un identificatore elettronico che viene scritto in un chip speciale nel computer, che in sostanza crea la smart card nel computer. Disponibile solo per l'uso con computer Windows 8 che contengono il chip TPM (Trusted Platform Module).
    
### <a name="enroll-your-smart-card"></a>Registrare la smart card

Prima di poter accedere con una smart card, la smart card deve essere "iscritta", ovvero le credenziali utente devono essere identificate con la smart card. Questo è il caso se la scheda è fisica o virtuale. Questo processo potrebbe essere già stato eseguito dall'amministratore di Skype for Business Server. Se non si è certi che l'operazione sia stata eseguita, rivolgersi a questi utenti.
  
> [!NOTE]
> Poiché ogni smart card virtuale è associata solo al dispositivo in cui è installata, sarà necessario registrare una scheda separata per ogni computer Windows 8 in uso. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Per registrare manualmente la smart card

1. Accedere al computer su cui si esegue Skype for Business.
    
2. Usando Internet Explorer, passare alla pagina Registrazione Web autorità di certificazione dell'organizzazione. 
    
    Se non si dispone già di questa risorsa, chiedere all'amministratore di Skype for Business Server l'indirizzo Web della risorsa. L'URL sarà simile al seguente: https://MyCA .[ nomeazienda].com/certsrv.
    
    > [!NOTE]
    > Se si usa Internet Explorer 10, potrebbe essere necessario visualizzare questo sito Web in modalità compatibilità. 
  
3. Quando ti viene richiesto di accedere alla pagina di certificazione, accedi usando il tuo account di dominio (anziché come amministratore del computer).
    
4. Nella pagina di benvenuto del sito Web selezionare **Richiedi un certificato.**
    
5. Selezionare **Richiesta avanzata.**
    
6. Selezionare **Crea e invia una richiesta a questa CA,** quindi fare clic su **Avanti.**
    
7. A questo punto verrà visualizzata una pagina denominata Smart Card Enrollment Station. Approvare la richiesta di installazione del ActiveX e quindi completare il modulo richiesta avanzata di certificato come segue:
    
    a. Selezionare **l'utente smart card** nell'elenco a discesa **Modello** di certificato.
    
    b. Selezionare **Crea nuovo set di chiavi.**
    
    c. Trova le informazioni sul produttore nell'etichetta della smart card e seleziona tale produttore nell'elenco a discesa **CSP.**
    
    d. Seleziona **CSP** come formato di richiesta, se non è già selezionato.
    
    e. Seleziona **sha1 nell'elenco** a discesa Hash Algorithm, se non è già selezionato.
    
    f. Assegna al certificato un nome che riconoscerai e fai clic su **Invia.**
    
8. Ora inserisci la smart card vuota nel lettore di schede collegato alla stazione di registrazione e fai clic su **Registra.**
    
9. Quando richiesto, immettere il PIN e quindi fare clic su **OK.**
    
    > [!NOTE]
    > Se l'utente del supporto tecnico non ha fornito un PIN speciale da usare per registrare la smart card, utilizzare il valore predefinito del PIN della smart card, ovvero 12345678. 
  
10. Selezionare l'opzione per forzare l'utente (l'utente) a modificare il PIN al primo utilizzo della smart card.
    
11. Ora inserisci la smart card vuota nel lettore di schede collegato alla stazione di registrazione e fai clic su **Registra.**
    
12. Quando richiesto, immettere il PIN e quindi fare clic su **OK.**
    
    > [!NOTE]
    > Se l'utente del supporto tecnico non ha fornito un PIN speciale da usare per registrare la smart card, utilizzare il valore predefinito del PIN della smart card, ovvero 12345678. 
  
13. Selezionare l'opzione per forzare l'utente (l'utente) a modificare il PIN al primo utilizzo della smart card.
    
14. Fare clic su **OK** per confermare che il certificato visualizzato contiene le informazioni.
    
15. Dopo aver visualizzato l'avviso che il certificato è stato emesso, fare clic su **Installa questo certificato** per completare il processo di registrazione.
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Accedere a Skype for Business con le credenziali della smart card

Prima di usare la smart card per la prima  volta, è consigliabile fare clic su Elimina le informazioni di accesso nella pagina di accesso di Skype for Business. In questo modo vengono eliminate tutte le credenziali di accesso archiviate nel computer ed eliminato una possibile origine di errore.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Per accedere a Skype for Business con le credenziali della smart card

1. Avviare il client Skype for Business.
    
2. Nella schermata Di accesso digitare il nome dell'account utente di accesso nella casella Indirizzo **di** accesso e quindi fare clic **su Accedi.**
    
3. Se si utilizza una smart card virtuale, ignorare questo passaggio.
    
    Se si utilizza una smart card fisica, inserire la smart card nel lettore di smart card e richiederlo, quindi fare clic su **OK** quando viene rilevata la smart card.
    
4. Digitare il numero PIN della smart card e quindi fare clic su **OK.**
    
    > [!NOTE]
    > Se non ti è stato assegnato un numero PIN della smart card dal supporto tecnico, usa il valore predefinito, ovvero 12345678. 
  
## <a name="see-also"></a>Vedere anche

[Gestire l'autenticazione a due fattori in Skype for Business Server](two-factor-authentication.md)
  
[Configurare l'autenticazione a due fattori in Skype for Business Server](configure-two-factor.md)
