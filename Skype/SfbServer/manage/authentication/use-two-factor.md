---
title: Usare l'autenticazione a due fattori con Skype for Business client e Skype for Business Server
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
description: "Riepilogo: utilizzare l'autenticazione a due fattori con Skype for Business Server e Skype for Business."
ms.openlocfilehash: deb5e3333c3138138a7bb3889ff515cfc1092576c1174082ef6b5553a1ec7540
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315682"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Usare l'autenticazione a due fattori con Skype for Business client e Skype for Business Server
 
**Riepilogo:** Usa l'autenticazione a due fattori con Skype for Business Server e Skype for Business.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Accedere a Skype for Business per la prima volta

Le informazioni di accesso vengono in genere configurate automaticamente quando Skype for Business è installato. Tuttavia, la prima volta che si Skype for Business, potrebbe essere necessario avviare manualmente il client.
  
### <a name="to-sign-in-for-the-first-time"></a>Per accedere per la prima volta

1. Accedere alla rete dell'organizzazione.
    
2. Selezionare **Avvia**  >  **tutti i programmi**  >  **Skype for Business**.
    
    Dovrebbe essere visualizzata la schermata di accesso.
    
    - Se la casella dell'indirizzo di accesso è già stata compilata, verificare che l'indirizzo visualizzato sia corretto.
    
    - Se non è corretto o se la casella è vuota, immettere l'indirizzo di accesso (in genere è lo stesso dell'indirizzo di posta elettronica).
    
    - Se viene visualizzata una casella di password vuota, aggiungere la password.
    
3. Selezionare **Accedi**.
    
## <a name="sign-out-of-skype-for-business"></a>Disconnettersi da Skype for Business

Al termine dell'Skype for Business, è possibile chiudere lo schermo, disconnettersi dalla sessione o uscire dal programma dal menu File. Nella tabella seguente vengono illustrate le differenze tra le opzioni.
  
|**Opzione**|**Funzione**|**Come eseguirlo**|
|:-----|:-----|:-----|
|Chiudi  <br/> |Chiude lo schermo, ma consente Skype for Business sessione identificata con l'ID utente continui a essere eseguita. In questo modo puoi continuare a ricevere notifiche e interagire con altri utenti. <br/> <br/> Puoi recuperare lo schermo in qualsiasi momento facendo clic sull'icona Skype for Business sulla barra delle applicazioni o nell'area di notifica nella parte inferiore dello schermo.  <br/> | Nella finestra Skype for Business principale eseguire una delle operazioni seguenti: <br/> 1. Selezionare il **pulsante Opzioni,** quindi selezionare **Chiudi**  >  **file.**  <br/> 2. Fare clic **sul** pulsante Chiudi (X) nell'angolo superiore destro della finestra. <br/> |
|Disconnettersi  <br/> |Termina la sessione associata all'ID utente, ma Skype for Business continua a essere eseguita in background. Quando ci si disconnette, viene visualizzata la finestra di accesso.  <br/> **Suggerimento:** Selezionare **Elimina le informazioni di accesso quando** ci si disconnette per rimuovere il record dell'ID di accesso e della password dal computer. Questa operazione potrebbe semplificare la risoluzione dei problemi di accesso per gli utenti del supporto. Può anche contribuire a garantire che le informazioni di accesso siano più sicure rendendo difficile per gli utenti non autorizzati accedere con le credenziali. <br/> |Nella finestra Skype for Business principale, selezionare il **pulsante Opzioni,** quindi selezionare **Disconnennei**  >  **file.**  <br/> |
|Esci  <br/> |Termina la Skype for Business sessione e arresta il Skype for Business sul computer. Dopo aver chiuso, se si desidera riavviare, selezionare **Avvia**  >  **tutti i programmi** > Skype for Business. <br/> |Nella finestra Skype for Business principale, selezionare il **pulsante Opzioni,** quindi selezionare **File**  >  **Esci.**  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Accedere a un Skype for Business con una smart card

Alcune organizzazioni ora utilizzano un processo di accesso a più passaggi, denominato autenticazione a due fattori, per aumentare la sicurezza per gli utenti. Se si prevede di utilizzare questa opzione, è necessaria una "smart card" per accedere a Skype for Business. Le smart card possono essere fisiche o virtuali:
  
- **Fisico** Circa le dimensioni di una carta di credito. È possibile inserirla in un lettore di smart card quando si accede.
    
- **Virtuale** Non un oggetto fisico, ma un identificatore elettronico che viene scritto in un chip speciale del computer, che in sostanza crea la smart card nel computer. Disponibile solo per l'Windows 8 computer che contengono il chip TPM (Trusted Platform Module).
    
### <a name="enroll-your-smart-card"></a>Registrare la smart card

Prima di poter accedere con una smart card, è necessario "registrare" la scheda, ovvero le credenziali utente devono essere identificate con la scheda. Questo è il caso se la scheda è fisica o virtuale. Questo processo potrebbe essere già stato eseguito dall'Skype for Business Server amministratore. Verifica con loro se non sei sicuro che sia stato fatto.
  
> [!NOTE]
> Poiché ogni smart card virtuale è associata solo al dispositivo in cui è installata, sarà necessario registrare una scheda separata per ogni computer Windows 8 in uso. 
  
### <a name="to-manually-enroll-your-smart-card"></a>Per registrare manualmente la smart card

1. Accedere al computer in cui verrà eseguito Skype for Business computer.
    
2. Usando Internet Explorer, passare alla pagina Registrazione Web Autorità di certificazione dell'organizzazione. 
    
    Chiedere all Skype for Business Server amministratore dell'organizzazione l'indirizzo Web di questa risorsa, se non è già presente. L'URL avrà un aspetto simile al seguente: https://MyCA .[ nomeazienda].com/certsrv.
    
    > [!NOTE]
    > Se si usa Internet Explorer 10, potrebbe essere necessario visualizzare questo sito Web in modalità compatibilità. 
  
3. Quando viene richiesto di accedere alla pagina di certificazione, accedere utilizzando l'account di dominio (anziché come amministratore del computer).
    
4. Nella pagina di benvenuto del sito Web selezionare **Richiedi un certificato.**
    
5. Selezionare **Richiesta avanzata**.
    
6. Selezionare **Crea e invia una richiesta a questa CA,** quindi fare clic su **Avanti.**
    
7. A questo punto verrà visualizzata una pagina denominata Smart Card Enrollment Station. Approvare la richiesta di installazione ActiveX controllo e quindi completare il modulo Richiesta avanzata di certificati come segue:
    
    a. Selezionare **Utente smart card** nell'elenco a discesa Modello **di** certificato.
    
    b. Selezionare **Crea nuovo set di chiavi**.
    
    c. Trova le informazioni sul produttore sull'etichetta della smart card e seleziona il produttore nell'elenco a discesa **CSP.**
    
    d. Seleziona **CSP** come Formato richiesta, se non è già selezionato.
    
    e. Selezionare **sha1** nell'elenco a discesa Algoritmo hash, se non è già selezionato.
    
    f. Assegna al certificato un nome che riconoscerai e fai clic su **Invia.**
    
8. Inserire ora la smart card vuota nel lettore di schede collegato alla stazione di registrazione e fare clic su **Registra**.
    
9. Quando richiesto, immettere il pin e quindi fare clic su **OK.**
    
    > [!NOTE]
    > Se l'utente del supporto tecnico non ha fornito un PIN speciale da utilizzare per registrare la smart card, utilizzare il valore predefinito del PIN della smart card, che è 12345678. 
  
10. Selezionare l'opzione per forzare l'utente (l'utente) a modificare il PIN al primo utilizzo della smart card.
    
11. Inserire ora la smart card vuota nel lettore di schede collegato alla stazione di registrazione e fare clic su **Registra**.
    
12. Quando richiesto, immettere il pin e quindi fare clic su **OK.**
    
    > [!NOTE]
    > Se l'utente del supporto tecnico non ha fornito un PIN speciale da utilizzare per registrare la smart card, utilizzare il valore predefinito del PIN della smart card, che è 12345678. 
  
13. Selezionare l'opzione per forzare l'utente (l'utente) a modificare il PIN al primo utilizzo della smart card.
    
14. Fare clic su **OK** per confermare che il certificato visualizzato contiene le informazioni.
    
15. Dopo aver visualizzato l'avviso che il certificato è stato emesso, fare clic su **Installa questo certificato** per completare il processo di registrazione.
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Accedere a Skype for Business con le credenziali della smart card

Prima di usare la smart card per la prima  volta, è consigliabile fare clic su Elimina info di accesso nella pagina di Skype for Business di accesso. In questo modo vengono eliminate tutte le credenziali di accesso archiviate nel computer ed elimina una possibile origine di errore.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Per accedere a Skype for Business con le credenziali della smart card

1. Avviare il client Skype for Business client.
    
2. Nella schermata Accedi digitare il nome dell'account utente di accesso nella casella **Indirizzo di** accesso e quindi fare clic **su Accedi**.
    
3. Se si utilizza una smart card virtuale, ignorare questo passaggio.
    
    Se si utilizza una smart card fisica, inserire la smart card nel lettore di smart card e richiederlo, quindi fare clic su **OK** quando viene rilevata la scheda.
    
4. Digitare il numero pin per la smart card e quindi fare clic su **OK.**
    
    > [!NOTE]
    > Se non è stato assegnato un numero PIN della smart card dal supporto tecnico, utilizzare il valore predefinito, ovvero 12345678. 
  
## <a name="see-also"></a>Vedere anche

[Gestire l'autenticazione a due fattori in Skype for Business Server](two-factor-authentication.md)
  
[Configurare l'autenticazione a due fattori in Skype for Business Server](configure-two-factor.md)
